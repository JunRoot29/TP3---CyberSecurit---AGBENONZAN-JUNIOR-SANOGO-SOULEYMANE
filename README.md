```markdown
# 🔐 Projet Fil Rouge — Cybersécurité, Virtualisation & Cloud

## 📌 Présentation générale

Ce projet s’inscrit dans le cadre du **Projet Fil Rouge – Licence 3 Cybersécurité**.  
Il consiste à **concevoir, déployer, sécuriser et auditer** une plateforme Web critique hébergée dans un **environnement virtualisé**, puis exposée via un **cloud simulé**.

L’approche adoptée repose sur :
- la **virtualisation** (VM Linux),
- la **segmentation réseau** (LAN / DMZ / Internet),
- l’utilisation de **Docker** pour simuler le cloud,
- l’application du **NIST Cybersecurity Framework** de bout en bout.

---

## 🎯 Objectifs du projet

- Comprendre le rôle de la virtualisation en cybersécurité  
- Mettre en place une architecture réseau segmentée et sécurisée  
- Réduire la surface d’attaque réseau et système  
- Identifier et corriger des vulnérabilités Web  
- Analyser des logs de sécurité et produire une timeline forensic  
- Proposer une réponse à incident et des améliorations de sécurité  

---

## 🧱 Architecture globale

L’architecture imposée est respectée et repose sur les zones suivantes :

- **LAN interne** : services non exposés
- **DMZ** : services accessibles depuis Internet (Web, Proxy)
- **Internet** : accès externe simulé
- **Pare-feu** : filtrage des flux entre les zones

📌 La virtualisation est obligatoire  
📌 Le cloud est simulé via **Docker à l’intérieur de la VM**

---

## 🖥 Environnement technique

### Virtualisation
- Hyperviseur : VirtualBox / VMware / KVM
- VM : Ubuntu Server 22.04 LTS

### Cloud simulé
- Docker
- Docker Compose
- Réseaux Docker segmentés :
  - `lan_net`
  - `dmz_net`
  - `public_net`

### Services déployés
- Serveur Web (DMZ)
- Proxy (DMZ)
- Services internes (LAN)
- Accès SSH sécurisé

---

## 🧭 Méthodologie — NIST Cybersecurity Framework

| Fonction NIST | Actions réalisées |
|--------------|------------------|
| Identify | Virtualisation, architecture, actifs, flux |
| Protect | Pare-feu, durcissement Linux, sécurité Web |
| Detect | Logs, corrélation d’événements |
| Respond | Plan de réponse à incident |
| Recover | Recommandations et améliorations |

---

## 📁 Structure du dépôt

```

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

- Docker / Docker Compose  
- iptables / nftables  
- Nmap  
- Nikto  
- curl  
- SSH  
- Journaux Linux  

---

## 👥 Organisation du travail (Binôme)

- **AGBENONZAN KOSSIVI JACQUES JUNIOR**  
  - Blue Team  
  - Architecture & virtualisation  
  - Sécurité réseau et système  
  - Logs et forensic  

- **SANOGO SOULEYMANE**  
  - Red Team  
  - Analyse d’exposition réseau  
  - Attaques contrôlées  
  - Audit Web  

---

## 📄 Livrables finaux

- Dépôt GitHub complet
- Rapport PDF (10–15 pages)
- Soutenance orale (10 minutes)

---

## 🏁 Auteurs

- **AGBENONZAN KOSSIVI JACQUES JUNIOR**
- **SANOGO SOULEYMANE**

Licence 3 Cybersécurité  
Année académique : 2024–2025
```
