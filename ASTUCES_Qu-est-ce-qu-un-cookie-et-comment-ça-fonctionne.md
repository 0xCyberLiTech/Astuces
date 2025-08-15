<div align="center">

  <br></br>
  
  <a href="https://github.com/0xCyberLiTech">
    <img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=50&duration=6000&pause=1000000000&color=FF0048&center=true&vCenter=true&width=1100&lines=%3EASTUCES_" alt="Titre dynamique ASTUCES" />
  </a>
  
  <br></br>

  <p align="center">
    <em>Qu'est-ce qu'un cookie et comment ça fonctionne ?</em><br>
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
> 🔗 [Mon GitHub principal](https://github.com/0xCyberLiTech)

<p align="center">
  <a href="https://github.com/0xCyberLiTech" target="_blank" rel="noopener">
    <img src="https://skillicons.dev/icons?i=linux,debian,bash,docker,nginx,git,vim" alt="Skills" alt="Logo techno" width="300">
  </a>
</p>

---

# 🍪 Qu'est-ce qu'un cookie et comment ça fonctionne ?

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

<p align="center">
  <b>🔒 Un guide proposé par <a href="https://github.com/0xCyberLiTech">0xCyberLiTech</a> • Pour des tutoriels accessibles à tous. 🔒</b>
</p>
