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

## 🔹 1. Définition d’un cookie

Un **cookie** (ou témoin de connexion) est un **petit fichier texte** qu’un **site web envoie et stocke dans le navigateur** de l’utilisateur lorsqu’il visite ce site. Il contient des **informations** que le site peut récupérer lors des visites ultérieures.

> Un cookie n'est **pas un programme** : il ne peut pas s’exécuter, ne contient pas de virus, ni d’accès à d’autres données du système.

---

## 🔹 2. Pourquoi les cookies existent-ils ?

Les cookies servent à **mémoriser des informations** utiles entre les sessions ou pendant la navigation. Par exemple :

- Garder un utilisateur connecté
- Mémoriser les préférences (langue, thème, etc.)
- Sauvegarder le contenu d’un panier d’achat
- Suivre les actions de l’utilisateur à des fins d’analyse ou de publicité

---

## 🔹 3. Comment fonctionne un cookie ?

### 🧭 Cycle de vie typique d’un cookie :

1. L’utilisateur visite un site (`example.com`)
2. Le site envoie une **réponse HTTP** contenant un en-tête `Set-Cookie`
3. Le navigateur **enregistre le cookie**
4. À chaque requête suivante vers `example.com`, le navigateur **renvoie le cookie** dans l’en-tête `Cookie`
5. Le serveur peut lire les données du cookie et agir en conséquence

### 📦 Exemple HTTP :

```
HTTP/1.1 200 OK
Set-Cookie: user_id=12345; Expires=Wed, 01 Jan 2026 00:00:00 GMT; Path=/; Secure; HttpOnly
```

Ce cookie :

- s'appelle `user_id`
- contient la valeur `12345`
- expire le 1er janvier 2026
- est envoyé uniquement en HTTPS (`Secure`)
- n’est pas accessible via JavaScript (`HttpOnly`)

---

## 🔹 4. Types de cookies

| Type de cookie             | Description |
|---------------------------|-------------|
| **Cookies de session**     | Temporaires, supprimés à la fermeture du navigateur |
| **Cookies persistants**    | Stockés jusqu’à une date d’expiration |
| **Cookies propriétaires**  | Placés par le site visité (ex: `example.com`) |
| **Cookies tiers**          | Placés par un domaine tiers (ex: pub, analytics) |
| **Cookies fonctionnels**   | Nécessaires au fonctionnement du site |
| **Cookies analytiques**    | Permettent de mesurer l’audience |
| **Cookies publicitaires**  | Suivent l’utilisateur pour du ciblage |

---

## 🔹 5. Où sont stockés les cookies ?

Les cookies sont **gérés par le navigateur** (Chrome, Firefox, Safari, etc.), chacun dispose d’un **espace de stockage sécurisé** dans lequel il conserve les cookies **par domaine**.

---

## 🔹 6. Sécurité et vie privée

### 🛡️ Risques potentiels :

- **Vol de session** via des attaques XSS si le cookie n’est pas `HttpOnly`
- **Tracking** de l’utilisateur à travers plusieurs sites
- **Empreinte numérique** : création d’un profil détaillé de l'utilisateur

### ✅ Bonnes pratiques :

- Utiliser `Secure` pour obliger le HTTPS
- Activer `HttpOnly` pour éviter l'accès par JavaScript
- Utiliser `SameSite=Strict` ou `Lax` pour limiter l’envoi aux requêtes du même site
- Respecter les règles du **RGPD** ou d’autres lois (ex: bannière d’acceptation des cookies)

---

## 🔹 7. Gérer les cookies côté développeur

### En JavaScript :

```javascript
document.cookie = "theme=dark; path=/; max-age=3600;";
```

### Lire les cookies :

```javascript
console.log(document.cookie); // "theme=dark; session_id=xyz"
```

---

## 🔹 8. Gérer les cookies côté utilisateur

### Dans le navigateur :

- Supprimer les cookies via les paramètres
- Utiliser la navigation privée
- Installer des bloqueurs de traqueurs (ex: uBlock Origin, Privacy Badger)

---

## 🔹 9. Alternatives aux cookies

- **LocalStorage / SessionStorage** (accessible uniquement en JavaScript)
- **IndexedDB** : base de données locale du navigateur
- **Fingerprinting** : identification via les caractéristiques du navigateur (plus intrusif)

---

## ✅ Résumé

| Élément                  | Description rapide                         |
|--------------------------|--------------------------------------------|
| Définition               | Petit fichier texte stocké par le navigateur |
| Utilisation              | Suivi, session, préférences, paniers       |
| Types                    | Session, persistant, tiers, pub, etc.      |
| Sécurité                 | `Secure`, `HttpOnly`, `SameSite`          |
| Vie privée               | Règlementée par RGPD, CNIL                 |

---

## 📚 Références utiles

- [Mozilla - Cookies (MDN)](https://developer.mozilla.org/fr/docs/Web/HTTP/Cookies)
- [CNIL - Guide cookies & traceurs](https://www.cnil.fr/fr/cookies-et-autres-traceurs)
- [OWASP - Secure Cookie Attributes](https://owasp.org/www-community/controls/SecureCookieAttribute)

---

<p align="center">
  <b>🔒 Un guide proposé par <a href="https://github.com/0xCyberLiTech">0xCyberLiTech</a> • Pour des tutoriels accessibles à tous. 🔒</b>
</p>
