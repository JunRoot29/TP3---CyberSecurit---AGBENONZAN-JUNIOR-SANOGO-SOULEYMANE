# Architecture Réseau & Cloud

## 1. Description globale
L’architecture repose sur une segmentation en trois zones :
- LAN
- DMZ
- Internet

## 2. Réseaux Docker
| Réseau | Type | Rôle |
|------|------|------|
| lan_net | Docker bridge | Réseau interne |
| dmz_net | Docker bridge | Zone exposée |
| public_net | Docker bridge | Accès externe |

## 3. Flux autorisés
| Source | Destination | Port | Autorisé | Justification |
|-------|------------|------|----------|---------------|

## 4. Flux interdits
- DMZ → LAN
- Internet → LAN

## 5. Schéma réseau
*(Image de l’architecture finale)*
