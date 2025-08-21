<div align="center">

  <br></br>
  
  <a href="https://github.com/0xCyberLiTech">
    <img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=50&duration=6000&pause=1000000000&color=FF0048&center=true&vCenter=true&width=1100&lines=%3EASTUCES_" alt="Titre dynamique ASTUCES" />
  </a>
  
  <br></br>

  <p align="center">
    <em>Sécurisation des mots de passe dans les scripts Bash sous Linux.</em><br>
    <b>🌐 Web – 🔐 Sécurité – 🚀 Performance</b>
  </p>

  [![🔗 Profil GitHub](https://img.shields.io/badge/Profil-GitHub-181717?logo=github&style=flat-square)](https://github.com/0xCyberLiTech)
  [![📦 Dernière version](https://img.shields.io/github/v/release/0xCyberLiTech/Apache2?label=version&style=flat-square&color=blue)](https://github.com/0xCyberLiTech/Apache2/releases/latest)
  [![📄 CHANGELOG](https://img.shields.io/badge/📄%20Changelog-Apache2-blue?style=flat-square)](https://github.com/0xCyberLiTech/Apache2/blob/main/CHANGELOG.md)
  [![📂 Dépôts publics](https://img.shields.io/badge/Dépôts-publics-blue?style=flat-square)](https://github.com/0xCyberLiTech?tab=repositories)
  [![👥 Contributeurs](https://img.shields.io/badge/👥%20Contributeurs-cliquez%20ici-007ec6?style=flat-square)](https://github.com/0xCyberLiTech/Apache2/graphs/contributors)

</div>

---

### 👨‍💻 **À propos de moi.**

> Bienvenue dans mon **laboratoire numérique personnel** dédié à l’apprentissage et à la vulgarisation de la cybersécurité.  
> Passionné par **Linux**, la **cryptographie** et les **systèmes sécurisés**, je partage ici mes notes, expérimentations et fiches pratiques.  
>  
> Pproposer un contenu clair, structuré et accessible pour étudiants, curieux et professionnels de l’IT.  

<p align="center">
  <a href="https://github.com/0xCyberLiTech" target="_blank" rel="noopener">
    <img src="https://skillicons.dev/icons?i=linux,debian,bash,docker,nginx,git,vim" alt="Skills" alt="Logo techno" width="300">
  </a>
</p>

---

### 🎯 **Objectif de ce dépôt.**

> Ce dépôt a pour vocation de centraliser un ensemble de bonnes pratiques, d'astuces et de notions clés autour de la sécurité sous Linux.
> Il s’adresse aux passionnés, étudiants et professionnels souhaitant renforcer leurs compétences en sécurisation des systèmes GNU/Linux.
> L’objectif est de fournir des conseils concrets pour durcir un système, comprendre les risques courants, et maîtriser les outils essentiels pour auditer, surveiller et sécuriser efficacement son environnement Linux, que ce soit en poste de travail, serveur ou infrastructure cloud.

---

# 🔐 Sécurisation des mots de passe dans les scripts Bash sous Linux.

- Comprendre les risques liés au stockage de mots de passe dans les scripts.
- Apprendre différentes méthodes pour sécuriser un mot de passe en Bash.
- Mettre en pratique ces méthodes à travers un TP guidé.

---

## 1. ⚠️ Les mauvaises pratiques à éviter

**Ne jamais stocker un mot de passe en clair dans un script Bash !**

```bash
#!/bin/bash
PASSWORD="motdepasse"
mysql -u root -p$PASSWORD
```

**Risque :** N'importe quel utilisateur avec accès au fichier ou à l'historique peut voir le mot de passe.

---

## 2. ✅ Lecture sécurisée avec `read -s` (mode interactif)

```bash
#!/bin/bash
read -s -p "Mot de passe : " PASSWORD
echo ""
mysql -u root -p"$PASSWORD"
```

🔍 Le mot de passe est saisi sans être affiché à l'écran.

---

## 3. ✅ Utiliser une variable d'environnement temporaire

### Dans le terminal :
```bash
export DB_PASS="motdepasse"
./mon_script.sh
unset DB_PASS
```

### Dans `mon_script.sh` :
```bash
#!/bin/bash
mysql -u root -p"$DB_PASS"
```

⚠️ Attention : Les variables d'environnement peuvent être visibles par d'autres utilisateurs (`ps`, `env`, etc.).

---

## 4. ✅ Fichier de configuration avec permissions restreintes

### Exemple avec MySQL (~/.my.cnf) :
```ini
[client]
user=root
password=motdepasse
```

```bash
chmod 600 ~/.my.cnf
mysql
```

👍 Recommandé pour les scripts MySQL automatisés.

---

## 5. ✅ Utilisation de `pass` (gestionnaire de mots de passe en ligne de commande)

### Installation :
```bash
sudo apt install pass
gpg --full-generate-key
pass init "NomDeVotreCléGPG"
```

### Ajout d’un mot de passe :
```bash
pass insert db/mysql
```

### Utilisation dans un script :
```bash
#!/bin/bash
PASSWORD=$(pass db/mysql)
mysql -u root -p"$PASSWORD"
```

---

## 6. ✅ Utilisation de GPG pour chiffrer un mot de passe

### Création d’un fichier chiffré :
```bash
echo "motdepasse" | gpg --symmetric -o passwd.gpg
```

### Script de déchiffrement :
```bash
#!/bin/bash
PASSWORD=$(gpg --quiet --batch --yes --decrypt passwd.gpg)
mysql -u root -p"$PASSWORD"
```

---

## 🧪 TP : Sécuriser un mot de passe MySQL avec `read -s` et `pass`

### Objectif :
Créer un script qui exécute une commande MySQL sans stocker le mot de passe en clair.

### Étape 1 : Créer le script interactif (read -s)
```bash
nano secure_mysql_read.sh
```

Contenu :
```bash
#!/bin/bash
read -s -p "Entrez le mot de passe MySQL : " PASSWORD
echo ""
mysql -u root -p"$PASSWORD" -e "SHOW DATABASES;"
```

```bash
chmod +x secure_mysql_read.sh
./secure_mysql_read.sh
```

### Étape 2 : Utiliser `pass`
```bash
pass insert db/mysql
```

Script : `secure_mysql_pass.sh`
```bash
#!/bin/bash
PASSWORD=$(pass db/mysql)
mysql -u root -p"$PASSWORD" -e "SHOW DATABASES;"
```

```bash
chmod +x secure_mysql_pass.sh
./secure_mysql_pass.sh
```

---

## ✅ Bonnes pratiques à retenir

| Méthode               | Sécurité | Facilité | À privilégier pour…              |
|------------------------|----------|----------|----------------------------------|
| Mot de passe en clair | ❌        | ✅        | Jamais                           |
| `read -s`             | ✅        | ✅        | Scripts interactifs              |
| Env temporaire        | ⚠️        | ✅        | Scripts ponctuels, non critiques |
| Fichier `.my.cnf`     | ✅        | ✅        | Automatisation MySQL             |
| `pass` / `gpg`        | ✅✅       | ⚠️        | Scripts automatisés sécurisés    |

---

## 📚 Références

- https://www.passwordstore.org/
- https://gnupg.org/
- `man gpg`, `man pass`, `man bash`

---

<p align="center">
  <b>🔒 Un guide proposé par <a href="https://github.com/0xCyberLiTech">0xCyberLiTech</a> • Pour des tutoriels accessibles à tous. 🔒</b>
</p>
