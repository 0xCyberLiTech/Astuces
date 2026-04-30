<div align="center">

  <br></br>
  
  <a href="https://github.com/0xCyberLiTech">
    <img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=50&duration=6000&pause=1000000000&color=FF0048&center=true&vCenter=true&width=1100&lines=%3EASTUCES_" alt="Titre dynamique ASTUCES" />
  </a>
  
  <br></br>

  <h2>Laboratoire numérique pour la cybersécurité, Linux & IT.</h2>

  <p align="center">
    <a href="https://0xcyberlitech.github.io/">
      <img src="https://img.shields.io/badge/Portfolio-0xCyberLiTech-181717?logo=github&style=flat-square" alt="🌐 Portfolio" />
    </a>
    <a href="https://github.com/0xCyberLiTech">
      <img src="https://img.shields.io/badge/Profil-GitHub-181717?logo=github&style=flat-square" alt="🔗 Profil GitHub" />
    </a>
    <a href="https://github.com/0xCyberLiTech/Astuces/releases/latest">
      <img src="https://img.shields.io/github/v/release/0xCyberLiTech/Astuces?label=version&style=flat-square&color=blue" alt="📦 Dernière version" />
    </a>
    <a href="https://github.com/0xCyberLiTech/Astuces/blob/main/CHANGELOG.md">
      <img src="https://img.shields.io/badge/📄%20Changelog-Astuces-blue?style=flat-square" alt="📄 CHANGELOG Astuces" />
    </a>
    <a href="https://github.com/0xCyberLiTech?tab=repositories">
      <img src="https://img.shields.io/badge/Dépôts-publics-blue?style=flat-square" alt="📂 Dépôts publics" />
    </a>
    <a href="https://github.com/0xCyberLiTech/Astuces/graphs/contributors">
      <img src="https://img.shields.io/badge/👥%20Contributeurs-cliquez%20ici-007ec6?style=flat-square" alt="👥 Contributeurs Astuces" />
    </a>
  </p>
  
</div>

<div align="center">
  <img src="https://img.icons8.com/fluency/96/000000/cyber-security.png" alt="CyberSec" width="80"/>
</div>

<div align="center">
  <p>
    <strong>Cybersécurité</strong> <img src="https://img.icons8.com/color/24/000000/lock--v1.png"/> • <strong>Linux Debian</strong> <img src="https://img.icons8.com/color/24/000000/linux.png"/> • <strong>Sécurité informatique</strong> <img src="https://img.icons8.com/color/24/000000/shield-security.png"/>
  </p>
</div>

---

<div align="center">
  
## À propos & Objectifs.

</div>

Ce projet propose des solutions innovantes et accessibles en cybersécurité, avec une approche centrée sur la simplicité d’utilisation et l’efficacité. Il vise à accompagner les utilisateurs dans la protection de leurs données et systèmes, tout en favorisant l’apprentissage et le partage des connaissances.

Le contenu est structuré, accessible et optimisé SEO pour répondre aux besoins de :
- 🎓 Étudiants : approfondir les connaissances
- 👨‍💻 Professionnels IT : outils et pratiques
- 🖥️ Administrateurs système : sécuriser l’infrastructure
- 🛡️ Experts cybersécurité : ressources techniques
- 🚀 Passionnés du numérique : explorer les bonnes pratiques

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

<div align="center">

<table>
<tr>
<td align="center"><b>🖥️ Infrastructure &amp; Sécurité</b></td>
<td align="center"><b>💻 Développement &amp; Web</b></td>
<td align="center"><b>🤖 Intelligence Artificielle</b></td>
</tr>
<tr>
<td align="center">
  <a href="https://www.kernel.org/"><img src="https://skillicons.dev/icons?i=linux" width="48" title="Linux" /></a>
  <a href="https://www.debian.org"><img src="https://skillicons.dev/icons?i=debian" width="48" title="Debian" /></a>
  <a href="https://www.gnu.org/software/bash/"><img src="https://skillicons.dev/icons?i=bash" width="48" title="Bash" /></a>
  <br/>
  <a href="https://nginx.org"><img src="https://skillicons.dev/icons?i=nginx" width="48" title="Nginx" /></a>
  <a href="https://www.docker.com"><img src="https://skillicons.dev/icons?i=docker" width="48" title="Docker" /></a>
  <a href="https://git-scm.com"><img src="https://skillicons.dev/icons?i=git" width="48" title="Git" /></a>
</td>
<td align="center">
  <a href="https://www.python.org"><img src="https://skillicons.dev/icons?i=python" width="48" title="Python" /></a>
  <a href="https://flask.palletsprojects.com"><img src="https://skillicons.dev/icons?i=flask" width="48" title="Flask" /></a>
  <a href="https://developer.mozilla.org/docs/Web/HTML"><img src="https://skillicons.dev/icons?i=html" width="48" title="HTML5" /></a>
  <br/>
  <a href="https://developer.mozilla.org/docs/Web/CSS"><img src="https://skillicons.dev/icons?i=css" width="48" title="CSS3" /></a>
  <a href="https://developer.mozilla.org/docs/Web/JavaScript"><img src="https://skillicons.dev/icons?i=js" width="48" title="JavaScript" /></a>
  <a href="https://code.visualstudio.com"><img src="https://skillicons.dev/icons?i=vscode" width="48" title="VS Code" /></a>
</td>
<td align="center">
  <a href="https://pytorch.org"><img src="https://skillicons.dev/icons?i=pytorch" width="48" title="PyTorch" /></a>
  <a href="https://www.tensorflow.org"><img src="https://skillicons.dev/icons?i=tensorflow" width="48" title="TensorFlow" /></a>
  <a href="https://www.raspberrypi.com"><img src="https://skillicons.dev/icons?i=raspberrypi" width="48" title="Raspberry Pi" /></a>
  <br/><br/>
  <a href="https://ollama.com"><img src="https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white" alt="Ollama" /></a>
  &nbsp;
  <a href="https://anthropic.com"><img src="https://img.shields.io/badge/Anthropic-D97757?style=for-the-badge&logo=anthropic&logoColor=white" alt="Anthropic" /></a>
</td>
</tr>
</table>

<br/>
