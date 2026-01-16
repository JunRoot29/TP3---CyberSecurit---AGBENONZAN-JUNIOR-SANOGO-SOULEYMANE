# Logs & Analyse Forensic

## 1. Logs analysés

Les journaux suivants ont été analysés dans le cadre de la phase de détection et d’analyse forensic :

- `/var/log/auth.log` : journal des tentatives d’authentification SSH
- Logs du serveur Web (Nginx) :
  - `access.log`
  - `error.log`

Ces journaux permettent d’identifier les tentatives d’accès, les scans de reconnaissance et les requêtes HTTP adressées au service Web exposé.

---

## 2. Événement de sécurité détecté

- **Type d’événement :** Activités de reconnaissance suivies de tentatives d’accès
- **Adresse IP source :** 10.0.2.15
- **Période observée :** 16h14 – 16h17

Les événements détectés correspondent à une phase de reconnaissance réseau, suivie de scans applicatifs et d’une tentative d’accès SSH.

---

## 3. Corrélation des événements

L’analyse des journaux permet d’établir la corrélation suivante :

**Scan réseau (Nmap) → Scan Web (Nikto) → Tentative d’accès SSH → Accès Web autorisé**

Cette séquence illustre un scénario classique de reconnaissance progressive d’une infrastructure exposée.

---

## 4. Timeline de l’incident

| Heure | Événement | Détails |
|------|----------|--------|
| 16h14 | Scan Nmap | Scan des ports de la VM (10.0.2.15), ports filtrés |
| 16h14 | Installation Nikto | Installation des paquets nécessaires aux scans Web |
| 16h15 | Scan Nikto | Envoi de requêtes HTTP multiples vers le serveur Web |
| 16h16 | Tentative SSH | Accès refusé suite aux restrictions SSH |
| 16h17 | Requête HTTP | Accès autorisé à la page Nginx (Web DMZ) |

---

## 5. Analyse

L’analyse des événements montre que les mécanismes de sécurité mis en place ont permis de limiter efficacement l’impact des activités détectées.  
Les scans réseau et Web ont été identifiés, la tentative d’accès SSH a été rejetée conformément à la politique de sécurité, tandis que l’accès au service Web exposé a été autorisé, conformément à l’architecture DMZ définie.

Cette timeline démontre l’efficacité de la journalisation et de la segmentation réseau pour détecter, analyser et comprendre les événements de sécurité, en conformité avec la fonction **DETECT** du NIST Cybersecurity Framework.
