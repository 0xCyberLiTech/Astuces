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

# Qu’est-ce qu’un *token* en sécurité ?

## 🧠 Définition pédagogique

> En cybersécurité, un **token** (ou jeton) est une **valeur générée automatiquement** qui permet à un utilisateur ou un système de prouver son identité sans avoir à transmettre un mot de passe à chaque requête.  
>
>Il est souvent utilisé dans les systèmes d'authentification et d'autorisation, notamment dans les API, les applications web et les services distribués.

### 🔐 À quoi sert un token ?
- **Authentifier** un utilisateur une fois connecté.
- **Protéger** les communications contre les accès non autorisés.
- **Simplifier** les échanges entre services ou systèmes.
- **Limiter** la durée d’accès (grâce à une date d’expiration).

---

## 🛠️ Types courants de tokens

| Type de Token        | Usage principal                         |
|----------------------|------------------------------------------|
| **JWT**              | Authentification via APIs REST           |
| **OAuth Access Token** | Accès sécurisé à des ressources tierces |
| **CSRF Token**       | Protection contre les attaques CSRF      |
| **Session Token**    | Sessions utilisateurs dans les applis web|

---

## 💡 Exemple concret : Authentification avec JWT

### 1. 🔐 Connexion utilisateur
L’utilisateur se connecte via un formulaire.  
Le backend vérifie les identifiants, puis **génère un JWT signé** contenant des informations comme :
```json
{
  "sub": "123456",
  "name": "Alice",
  "role": "admin",
  "exp": 1722527100
}
```

### 2. 🎫 Envoi du token
Le backend renvoie le token au frontend, qui le stocke (ex. : dans le `localStorage` ou un cookie sécurisé).

### 3. 📲 Appels API sécurisés
À chaque requête API, le frontend envoie le token dans l’en-tête HTTP :
```
Authorization: Bearer <le_token>
```

### 4. 🛡️ Vérification côté serveur
Le backend vérifie la validité du token :
- Signature correcte ✅
- Expiration non atteinte ⏳
- Permissions adéquates 🔒

Si tout est OK, l’accès est accordé.

---

## ✅ Avantages des tokens

- Stateless (pas besoin de session côté serveur)
- Sécurisé (si bien implémenté)
- Adapté aux microservices et APIs

---

## ⚠️ Bonnes pratiques

- Toujours signer et chiffrer les tokens sensibles
- Définir une expiration courte
- Stocker côté client de manière sécurisée (éviter `localStorage` si possible)
- Révoquer les tokens en cas de compromission

---

## 📚 Conclusion

Les *tokens* sont devenus indispensables en sécurité moderne pour garantir une **authentification fluide et sécurisée**. Leur bon usage permet de protéger les utilisateurs, les données, et les systèmes.

---

<p align="center">
  <b>🔒 Un guide proposé par <a href="https://github.com/0xCyberLiTech">0xCyberLiTech</a> • Pour des tutoriels accessibles à tous. 🔒</b>
</p>
