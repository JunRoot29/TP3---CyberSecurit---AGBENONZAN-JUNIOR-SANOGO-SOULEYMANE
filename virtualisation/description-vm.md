# Virtualisation & Isolation

## 1. Environnement hôte
- **Système hôte** : Windows 11  
- **Hyperviseur utilisé** : VirtualBox  
- **Raison du choix** : Facile à utiliser, installation rapide et outils gratuits  

## 2. Machine virtuelle
- **OS** : Ubuntu Server 22.04 LTS  
- **Raison du choix** : La version LTS d’Ubuntu Server est privilégiée pour sa stabilité, son support à long terme et son adoption en environnement professionnel.  

### Ressources allouées
| Ressource          | Valeur     |
|--------------------|------------|
| CPU                | 3          |
| RAM                | 4096 MB    |
| Interfaces réseau  | NAT, Accès par pont, FastEthernet |

## 3. Intérêt sécurité de la virtualisation
- **Isolation** : Séparation entre l’hôte et la VM  
- **Cloisonnement** : Limitation des interactions entre environnements  
- **Réduction d’impact** : Contenir les menaces dans un espace restreint  
- **Snapshots** : Sauvegarde/restauration rapide de l’état de la VM  

## 4. Schéma hôte / hyperviseur / VM
*(Insérer ici un schéma illustrant la relation entre l’hôte, l’hyperviseur et la machine virtuelle)*  
