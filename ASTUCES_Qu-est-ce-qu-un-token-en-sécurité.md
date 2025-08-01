<div align="center">

  <br></br>
  <a href="https://github.com/0xCyberLiTech">
    <img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=50&duration=6000&pause=1000000000&color=FF0048&center=true&vCenter=true&width=1100&lines=%3EASTUCES_" alt="Titre dynamique ASTUCES" />
  </a>
  <br></br>

  <p align="center">
    <em>Qu’est-ce qu’un *token* en sécurité.</em><br>
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

# 🔑 Qu’est-ce qu’un *token* en sécurité ?

## 🎯 Objectif du document
Ce document explique **ce qu’est un token**, **son rôle en cybersécurité** et **les bonnes pratiques d’implémentation**.  
Il est conçu pour :  
- **Les étudiants** qui souhaitent comprendre les bases de l’authentification moderne
- **Les professionnels** qui veulent maîtriser les aspects techniques et sécuritaires

---

## 🧠 Définition pédagogique

En cybersécurité, un **token** (ou *jeton*) est une **valeur unique générée automatiquement** permettant à un utilisateur ou un système de prouver son identité **sans envoyer son mot de passe à chaque requête**.

📌 **Exemples d’utilisation :**
- Authentification via API
- Accès sécurisé à des données dans une application web
- Communication sécurisée entre microservices

> 💡 **Important :** Un token ne contient pas obligatoirement des informations sensibles, mais il doit être protégé car il donne un accès à des ressources.

---

## 🔐 À quoi sert un token ?
- **Authentifier** un utilisateur une seule fois, puis réutiliser le token pour prouver son identité.
- **Protéger** les communications contre les accès non autorisés.
- **Simplifier** les échanges entre applications ou services.
- **Limiter** la durée d’accès (expiration planifiée).

📌 **Exemple concret (étudiant)** :  
Quand vous vous connectez à un site, un token peut remplacer votre mot de passe pour toutes vos actions pendant un certain temps.

📌 **Exemple technique (pro)** :  
Dans une API REST, un token JWT est envoyé dans chaque requête via l’en-tête :
```
Authorization: Bearer <TOKEN>
```

---

## 🛠️ Types courants de tokens

| Type de Token           | Usage principal                                | Exemple concret |
|-------------------------|-----------------------------------------------|----------------|
| **JWT** (*JSON Web Token*) | Authentification via APIs REST               | Connexion à un tableau de bord web |
| **OAuth Access Token**  | Accès sécurisé à des ressources tierces       | Connexion via "Se connecter avec Google" |
| **CSRF Token**          | Protection contre les attaques CSRF           | Validation d’un formulaire bancaire |
| **Session Token**       | Gestion des sessions utilisateurs             | Sites e-commerce |

---

## 💡 Exemple concret : Authentification avec JWT

### 1️⃣ Connexion utilisateur
L’utilisateur saisit ses identifiants.  
Le serveur vérifie et **génère un JWT signé** contenant :  
```json
{
  "sub": "123456",
  "name": "Alice",
  "role": "admin",
  "exp": 1722527100
}
```

### 2️⃣ Envoi du token au client
Le serveur retourne le token au navigateur, qui peut le stocker dans :
- **Cookie sécurisé (`HttpOnly`, `Secure`)**
- **Mémoire d’application (variable locale)**

### 3️⃣ Utilisation pour accéder à une API
À chaque appel API :  
```
Authorization: Bearer <TOKEN>
```

### 4️⃣ Vérification côté serveur
- Vérification **signature** ✅
- Vérification **expiration** ⏳
- Vérification **permissions** 🔒

Si tout est OK → accès autorisé.

---

## ✅ Avantages des tokens

| Avantage | Explication |
|----------|-------------|
| **Sans état** (*stateless*) | Pas besoin de stocker la session côté serveur |
| **Sécurisé** | Signature et chiffrement possibles |
| **Flexible** | Fonctionne sur web, mobile, API |
| **Scalable** | Idéal pour microservices et environnements distribués |

---

## ⚠️ Bonnes pratiques

- Signer et chiffrer les tokens contenant des données sensibles
- Définir une **expiration courte** (ex : 15 minutes)
- Stocker côté client **de manière sécurisée** (éviter `localStorage`)
- Révoquer un token compromis
- Utiliser **HTTPS uniquement** pour éviter l’interception

📌 **Exemple de création sécurisée en Node.js :**
```javascript
const jwt = require('jsonwebtoken');
const token = jwt.sign(
  { userId: 123, role: 'admin' },
  process.env.JWT_SECRET,
  { expiresIn: '15m' }
);
```

---

## 📚 Conclusion

Les tokens sont essentiels pour une **authentification moderne, sécurisée et performante**.  
Bien implémentés, ils permettent :
- D’améliorer la sécurité
- De faciliter les connexions multi-plateformes
- D’offrir une expérience utilisateur fluide

---

## 🔗 Références utiles

- [JWT.io - Introduction aux JWT](https://jwt.io/introduction)  
- [OAuth 2.0 - RFC 6749](https://datatracker.ietf.org/doc/html/rfc6749)  
- [OWASP - API Security](https://owasp.org/www-project-api-security/)  

---

<p align="center">
  <b>🔒 Un guide proposé par <a href="https://github.com/0xCyberLiTech">0xCyberLiTech</a> • Pour des tutoriels accessibles à tous. 🔒</b>
</p>
