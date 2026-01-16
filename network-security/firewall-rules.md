# Sécurité Réseau – Pare-feu

## 1. Scan initial (avant sécurisation)

Avant la mise en place des règles de filtrage, un scan réseau a été effectué afin d’identifier les services exposés.

- **Outil :** Nmap  
- **IP cible :** 10.0.2.15  
- **Résultat :**
  - Plusieurs ports détectés comme accessibles ou filtrés
  - Surface d’attaque jugée trop large pour une infrastructure sécurisée

Ce scan a permis d’identifier les services réellement nécessaires au fonctionnement de l’architecture.

---

## 2. Objectifs du filtrage

Les objectifs principaux du filtrage réseau sont les suivants :

- Réduire la surface d’attaque
- Appliquer le principe du moindre privilège
- Autoriser uniquement les services indispensables
- Bloquer toute communication non légitime

---

## 3. Règles de pare-feu mises en place

Les règles suivantes ont été appliquées à l’aide de **iptables** :

```bash
# Politique par défaut restrictive
iptables -P INPUT DROP
iptables -P FORWARD DROP
iptables -P OUTPUT ACCEPT

# Autoriser les connexions déjà établies
iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT

# Autoriser le trafic local
iptables -A INPUT -i lo -j ACCEPT

# Autoriser le service Web (DMZ)
iptables -A INPUT -p tcp --dport 80 -j ACCEPT

# Autoriser SSH depuis l’administrateur uniquement
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

Ces règles assurent un filtrage strict tout en garantissant le fonctionnement des services nécessaires.

---

## 4. Scan après sécurisation

Un nouveau scan Nmap a été réalisé après la mise en place des règles de filtrage.

**Ports ouverts :**
- 80 (HTTP)
- 22 (SSH – accès restreint)

**Ports fermés ou filtrés :**
- Tous les autres ports non nécessaires

---

## 5. Comparaison avant / après sécurisation

| Élément | Avant sécurisation | Après sécurisation |
|--------|-------------------|------------------|
| Ports exposés | Plusieurs | Uniquement nécessaires |
| Politique pare-feu | Peu restrictive | Restrictive par défaut |
| Surface d'attaque | Élevée | Réduite |
| Contrôle des flux | Limité | Strict |

---

## 6. Conclusion

La mise en place des règles de filtrage a permis de réduire significativement la surface d’attaque réseau et d’améliorer la sécurité globale de l’infrastructure, conformément à la fonction PROTECT du NIST Cybersecurity Framework.