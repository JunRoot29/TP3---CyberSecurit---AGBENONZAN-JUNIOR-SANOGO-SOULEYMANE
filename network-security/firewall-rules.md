# Sécurité Réseau – Pare-feu

## 1. Scan initial (avant sécurisation)
- Outil : Nmap
- IP cible :
- Ports ouverts :

## 2. Objectifs du filtrage
- Réduire la surface d’attaque
- Autoriser uniquement les services nécessaires

## 3. Règles iptables / nftables
```bash
# Exemple
iptables -P INPUT DROP
iptables -A INPUT -p tcp --dport 80 -j ACCEPT
4. Scan après sécurisation
Ports ouverts :

Ports fermés :

5. Comparaison avant / après
Élément	Avant	Après

---

# 📁 4️⃣ `system-security/`

### 📄 `hardening-linux.md`
```markdown
# Sécurité Système Linux

## 1. Gestion des utilisateurs
- Compte root :
- Utilisateurs standards :
- Principe du moindre privilège :

## 2. Sécurisation SSH
- Port SSH :
- Login root :
- Authentification par mot de passe :
- Bannière légale :

## 3. Permissions fichiers sensibles
- /etc/shadow
- /etc/passwd
- /etc/ssh/sshd_config

## 4. Services désactivés
| Service | Raison |
|-------|--------|

## 5. Justification NIST (Protect)
