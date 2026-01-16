# Sécurité Web – Audit

## 1. Service Web analysé

- **Type :** Serveur Web Nginx
- **Emplacement :** DMZ
- **Accès :** HTTP (port 80)

Le service Web est volontairement exposé afin de simuler une plateforme accessible depuis Internet.

---

## 2. Outils utilisés

Les outils suivants ont été utilisés pour réaliser l’audit de sécurité Web :

- **Nikto** : scan automatisé des vulnérabilités Web
- **curl** : analyse manuelle des en-têtes HTTP
- **Navigateur Web** : vérification de l’accès au service

---

## 3. Vulnérabilités identifiées

| Faille | Preuve | Impact | Correctif | Référence NIST |
|------|--------|--------|-----------|---------------|
| Headers HTTP absents | Résultat Nikto / curl | Risque de XSS et clickjacking | Ajouter headers de sécurité | PR.DS |
| Information serveur exposée | Header `Server: nginx` | Facilite la reconnaissance | Masquer version serveur | PR.IP |
| Absence de HTTPS | Accès HTTP | Interception des données | Activer TLS / HTTPS | PR.DS |
| Configuration par défaut | Scan Nikto | Attaque facilitée | Durcissement Nginx | PR.AC |

---

## 4. Analyse des headers HTTP

L’analyse des en-têtes HTTP a révélé l’absence ou la faiblesse des protections suivantes :

- **X-Frame-Options** : absent  
- **Content-Security-Policy** : absent  
- **Server** : expose le type de serveur Web  

Ces éléments constituent des failles de configuration courantes sur les serveurs Web non durcis.

---

## 5. Conclusion de l’audit

L’audit de sécurité Web a mis en évidence plusieurs vulnérabilités liées à la configuration par défaut du serveur Web.  
Bien que le service soit fonctionnel, l’absence de mécanismes de protection applicative et de chiffrement augmente les risques d’exploitation.

Un durcissement du serveur Web et l’activation du HTTPS sont nécessaires afin d’améliorer la sécurité globale du service, conformément à la fonction **PROTECT** du NIST Cybersecurity Framework.
