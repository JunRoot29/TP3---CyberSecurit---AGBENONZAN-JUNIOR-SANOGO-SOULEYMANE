```markdown
# 🔐 Projet Fil Rouge — Cybersécurité, Virtualisation & Cloud

## 📌 Présentation générale

Ce projet s’inscrit dans le cadre du **Projet Fil Rouge – Licence 3 Cybersécurité**.  
Il a pour objectif de **concevoir, déployer, sécuriser et auditer** une plateforme Web critique hébergée dans un **environnement virtualisé**, puis exposée via un **cloud simulé**.

L’ensemble du projet repose sur une approche méthodique inspirée des bonnes pratiques de la cybersécurité et s’appuie sur le **NIST Cybersecurity Framework**.

---

## ⚙️ Approche adoptée

- **Virtualisation** d’une infrastructure Linux  
- **Segmentation réseau** (LAN / DMZ / Internet)  
- **Cloud simulé** à l’aide de Docker  
- Mise en œuvre des fonctions du **NIST Cybersecurity Framework**

---

## 🎯 Objectifs du projet

- Comprendre le rôle de la virtualisation en cybersécurité  
- Concevoir une architecture réseau segmentée et sécurisée  
- Réduire la surface d’attaque réseau et système  
- Identifier des vulnérabilités Web courantes  
- Analyser les journaux de sécurité et construire une timeline forensic  
- Proposer une réponse à incident et des axes d’amélioration  

---

## 🧱 Architecture globale

L’architecture mise en place repose sur une segmentation claire des zones réseau :

- **LAN interne** : services non exposés  
- **DMZ** : services accessibles depuis Internet (serveur Web, proxy)  
- **Internet** : accès externe simulé  
- **Pare-feu** : contrôle et filtrage des flux entre les zones  

📌 La virtualisation constitue le socle de l’infrastructure  
📌 Le cloud est simulé via **Docker à l’intérieur de la machine virtuelle**

---

## 🖥️ Environnement technique

### Virtualisation
- Hyperviseur : VirtualBox / VMware / KVM  
- Système invité : Ubuntu Server 22.04 LTS  

### Cloud simulé
- Docker & Docker Compose  
- Réseaux Docker segmentés :
  - `internal_lan`  
  - `web_dmz`  
  - `public_net`
  - `lan_app`  
  - `edge_transport_server_role`
  - `proxy_dmz`  

### Services déployés
- Serveur Web (DMZ)  
- Proxy (DMZ)  
- Services internes (LAN)  
- Accès SSH sécurisé  

---

## 🧭 Méthodologie — NIST Cybersecurity Framework

| Fonction NIST | Actions réalisées |
|--------------|------------------|
| Identify     | Virtualisation, architecture, actifs, flux |
| Protect      | Pare-feu, durcissement Linux, sécurité Web |
| Detect       | Analyse des logs et corrélation d’événements |
| Respond      | Plan de réponse à incident |
| Recover      | Recommandations et amélioration continue |

---

## 📂 Structure du dépôt

```bash
.
├── virtualisation/
├── architecture-cloud/
├── network-security/
├── system-security/
├── web-security/
├── forensic/
├── nist-mapping/
└── report/
```

---

## 🔎 Outils utilisés

* Docker / Docker Compose
* iptables / nftables
* Nmap
* Nikto
* curl
* SSH
* Journaux Linux

---

## 👥 Organisation du travail (Binôme)

### 👤 AGBENONZAN KOSSIVI JACQUES JUNIOR — *Blue Team*

* Architecture & virtualisation
* Sécurité réseau et système
* Analyse des logs & forensic

### 👤 SANOGO SOULEYMANE — *Red Team*

* Analyse d’exposition réseau
* Tests d’attaque contrôlés
* Audit de sécurité Web

---

## 📄 Livrables finaux

* Dépôt GitHub complet
* Rapport final (PDF / DOCX)
* Soutenance orale

---

## 🏁 Auteurs

* **AGBENONZAN KOSSIVI JACQUES JUNIOR**
* **SANOGO SOULEYMANE**

🎓 Licence 3 Cybersécurité  
📅 Année académique : 2025–2026
```
