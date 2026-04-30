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

## 🍪 Qu'est-ce qu'un cookie et comment ça fonctionne ?

## 🎯 Objectif du document
Ce document explique **ce qu’est un cookie**, **son rôle dans le web** et **les bonnes pratiques de sécurité**.  
Il s’adresse **à la fois** :
- Aux **étudiants** qui souhaitent comprendre les bases
- Aux **professionnels** qui veulent maîtriser les aspects techniques et réglementaires

---

## 🔹 1. Définition d’un cookie

Un **cookie** (ou *témoin de connexion*) est un **petit fichier texte** stocké par le navigateur lorsqu’un utilisateur visite un site web.  
Il permet au site de **mémoriser des informations** et de **reconnaître l’utilisateur** lors de visites ultérieures.

> **💡 Important** : Un cookie **n’est pas** un programme exécutable.  
> Il ne peut pas infecter un ordinateur directement et ne donne pas accès à d’autres fichiers.

📌 **Exemple concret (étudiant)** :  
Si vous cochez *"Se souvenir de moi"* sur un site de réseau social, un cookie est créé pour éviter que vous ne vous reconnectiez à chaque visite.

📌 **Exemple technique (pro)** :  
Un serveur envoie l’en-tête :
```http
Set-Cookie: user_id=12345; HttpOnly; Secure; SameSite=Strict
```
Cela crée un cookie côté navigateur avec la valeur `12345` qui :
- Ne peut être lu par JavaScript (`HttpOnly`)
- Est transmis uniquement en HTTPS (`Secure`)
- N’est envoyé que si la requête provient du même site (`SameSite=Strict`)

---

## 🔹 2. Pourquoi les cookies existent-ils ?

Les cookies facilitent **l’expérience utilisateur** et permettent certaines fonctionnalités clés du web.

| Usage | Exemple concret |
|-------|----------------|
| **Session** | Rester connecté à un site sans ressaisir son mot de passe |
| **Préférences** | Sauvegarder la langue d’affichage ou le thème clair/sombre |
| **Panier d’achat** | Mémoriser les articles ajoutés sans être connecté |
| **Analyse d’audience** | Compter les visites sur un site web |
| **Publicité ciblée** | Afficher des pubs liées à vos recherches précédentes |

---

## 🔹 3. Cycle de vie d’un cookie

### 🧭 Schéma simplifié
```
[Visite du site] → [Réponse serveur : Set-Cookie] → [Stockage navigateur]
→ [Requêtes suivantes : Cookie envoyé] → [Serveur lit le cookie]
```

### 📦 Exemple HTTP
```http
HTTP/1.1 200 OK
Set-Cookie: session_id=abc123; Expires=Wed, 01 Jan 2026 00:00:00 GMT; Path=/; Secure; HttpOnly
```
- `session_id` = nom du cookie  
- `abc123` = valeur stockée  
- `Expires` = date d’expiration  
- `Secure` = uniquement via HTTPS  
- `HttpOnly` = inaccessible en JavaScript

---

## 🔹 4. Types de cookies

| Type | Description | Exemple |
|------|-------------|---------|
| **Session** | Disparaît à la fermeture du navigateur | Connexion temporaire à un site |
| **Persistant** | Expire à une date précise | Sauvegarde d’un panier d’achat |
| **Propriétaire** | Déposé par le site visité | `example.com` |
| **Tiers** | Déposé par un autre domaine | Publicité, tracking |
| **Fonctionnel** | Indispensable au site | Authentification |
| **Analytique** | Mesure l’audience | Google Analytics |
| **Publicitaire** | Ciblage publicitaire | Bannière pub personnalisée |

---

## 🔹 5. Où sont stockés les cookies ?

Chaque navigateur (Chrome, Firefox, Edge, Safari…) stocke les cookies dans **un fichier interne sécurisé**.  
Ils sont classés **par nom de domaine** pour éviter que deux sites différents ne puissent lire les cookies l’un de l’autre.

---

## 🔹 6. Sécurité et vie privée

### ⚠️ Risques potentiels
- **Vol de session** (*Session Hijacking*) via attaques XSS si `HttpOnly` n’est pas utilisé
- **Tracking publicitaire** à travers plusieurs sites
- **Fingerprinting** : profilage détaillé de l’utilisateur

### ✅ Bonnes pratiques développeur
- **Toujours utiliser** `Secure`, `HttpOnly` et `SameSite`
- **Limiter la durée de vie** des cookies
- **Ne jamais stocker d’informations sensibles** en clair

📌 Exemple sécurisé :
```http
Set-Cookie: token=xyz789; Max-Age=1800; HttpOnly; Secure; SameSite=Strict
```

---

## 🔹 7. Gestion des cookies en JavaScript

**Création**
```javascript
document.cookie = "theme=dark; path=/; max-age=3600;";
```

**Lecture**
```javascript
console.log(document.cookie);
```

**Suppression**
```javascript
document.cookie = "theme=; Max-Age=0";
```

---

## 🔹 8. Gestion des cookies côté utilisateur

- Supprimer via **Paramètres du navigateur**
- Utiliser la **navigation privée**
- Installer un **bloqueur de traqueurs** :  
  - [uBlock Origin](https://ublockorigin.com/)  
  - [Privacy Badger](https://privacybadger.org/)

---

## 🔹 9. Alternatives aux cookies

| Alternative | Avantages | Limites |
|-------------|-----------|---------|
| **LocalStorage** | Grande capacité, persistant | Accessible en JS (moins sécurisé) |
| **SessionStorage** | Disparaît à la fermeture de l’onglet | Non partagé entre onglets |
| **IndexedDB** | Base de données locale | Complexité d’utilisation |
| **Fingerprinting** | Pas besoin de cookies | Très intrusif, réglementé |

---

## ✅ Résumé

| Élément | Description |
|---------|-------------|
| **Définition** | Petit fichier texte stocké par le navigateur |
| **Utilité** | Sessions, préférences, analyse |
| **Types** | Session, persistant, tiers… |
| **Sécurité** | `Secure`, `HttpOnly`, `SameSite` |
| **Vie privée** | RGPD, CNIL, consentement utilisateur |

---

## 📚 Références
- [Mozilla - Cookies (MDN)](https://developer.mozilla.org/fr/docs/Web/HTTP/Cookies)  
- [CNIL - Guide cookies & traceurs](https://www.cnil.fr/fr/cookies-et-autres-traceurs)  
- [OWASP - Secure Cookie Attributes](https://owasp.org/www-community/controls/SecureCookieAttribute)

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

