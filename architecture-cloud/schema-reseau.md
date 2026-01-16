# Architecture Réseau & Cloud

## 1. Description globale

L’architecture mise en place repose sur une **segmentation réseau stricte** afin de limiter la surface d’attaque et de contrôler les flux entre les différentes zones.  
Trois zones principales ont été définies :

- 🏠 **LAN (Local Area Network)** : réseau interne destiné aux services non exposés
- 🛡️ **DMZ (Demilitarized Zone)** : zone intermédiaire hébergeant les services accessibles depuis l’extérieur
- 🌍 **Internet** : réseau public simulant l’accès externe

Cette segmentation permet de renforcer l’isolation des services critiques et de limiter la propagation d’éventuelles attaques.

---

## 2. Réseaux Docker

Le cloud est simulé à l’aide de **Docker**, avec des réseaux distincts correspondant aux différentes zones de l’architecture.

| Réseau | Type | Rôle |
|------|------|------|
| `lan_net` | Docker bridge | Réseau interne isolé |
| `dmz_net` | Docker bridge | Zone exposée (services Web) |
| `public_net` | Docker bridge | Accès externe simulé |

Chaque service est connecté uniquement au réseau nécessaire à son fonctionnement, conformément au principe du moindre privilège.

---

## 3. Flux autorisés

Les flux réseau autorisés ont été définis de manière restrictive afin de réduire la surface d’attaque.

| Source | Destination | Port | Autorisé | Justification |
|-------|------------|------|----------|---------------|
| Internet | DMZ (Web) | 80 | Oui | Accès public au service Web |
| LAN | DMZ (Web) | 80 | Oui | Accès interne aux services exposés |
| Administrateur | VM | 22 | Oui | Administration sécurisée (SSH) |

---

## 4. Flux interdits

Les flux suivants sont explicitement bloqués :

- Internet → LAN  
- DMZ → LAN  
- Internet → Services internes  
- Accès direct non autorisé entre conteneurs  

Ces restrictions empêchent les accès directs aux ressources internes et limitent les déplacements latéraux en cas de compromission.

---

## 5. Schéma réseau

Le schéma réseau illustre :
- La segmentation LAN / DMZ / Internet
- Les réseaux Docker associés
- Le rôle du pare-feu dans le filtrage des flux

📌 *(Insérer ici l’image de l’architecture finale)*

---

## 6. Objectifs de sécurité

- Réduction de la surface d’attaque
- Isolation des services critiques
- Contrôle strict des flux réseau
- Application du principe du moindre privilège
