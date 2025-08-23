<div align="center">

  <br></br>
  
  <a href="https://github.com/0xCyberLiTech">
    <img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=50&duration=6000&pause=1000000000&color=FF0048&center=true&vCenter=true&width=1100&lines=%3EASTUCES_" alt="Titre dynamique ASTUCES" />
  </a>
  
  <br></br>
  
  <p align="center">
    <em> Qu’est-ce qu’un Hash ?</em><br>
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
 > Proposer un contenu clair, structuré et accessible pour étudiants, curieux et professionnels de l’IT.  

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

# 🔐 Qu’est-ce qu’un Hash ?

## 📘 Définition

Un **hash** (ou empreinte numérique) est le résultat d’une fonction mathématique qui transforme **une donnée quelconque** (texte, fichier, mot de passe, etc.) en **une suite de caractères fixe**, souvent en format **hexadécimal**.

---

## 🧠 À quoi sert un hash ?

- ✅ Vérifier l’intégrité d’un fichier
- ✅ Stocker un mot de passe de façon sécurisée
- ✅ Identifier un fichier de manière unique
- ❌ Impossible de retrouver la donnée originale (fonction irréversible)

---

## 🎯 Caractéristiques d’un bon hash

1. **Taille fixe** (ex: 64 caractères pour SHA-256)
2. **Unique (quasi)** : deux contenus différents → deux hash différents
3. **Irréversible** : impossible de retrouver le contenu d'origine
4. **Rapide** à calculer

---

## 🔍 Exemple concret

### 📄 Message d’origine :
```
Bonjour le monde !
```

### 🔑 Hash SHA-256 :
```
c76a50197e2bfc330b6c9759b2ce922ea3913f7bd11e9636cf9608972dd1e4d3
```

➡️ Ce hash est **unique** au message. Si tu changes ne serait-ce qu’une lettre, le hash sera **complètement différent**.

---

## 🛡️ Cas d’usage : mot de passe

1. L’utilisateur crée un mot de passe : `MonSuperMotDePasse123!`
2. Le site calcule le hash et **n’enregistre que le hash**
3. Lors de la connexion, le mot de passe tapé est **haché et comparé au hash enregistré**

➡️ Cela améliore la sécurité : en cas de fuite, le mot de passe **n’est pas visible**.

---

## 🧪 Tester un hash

Tu peux tester par toi-même ici :
🔗 https://emn178.github.io/online-tools/sha256.html

Tape un mot, observe le hash. Change un seul caractère : le hash change totalement.

---

## 📌 Résumé rapide

| Élément         | Description                               |
|-----------------|-------------------------------------------|
| Hash            | Empreinte numérique                       |
| Taille fixe     | Toujours la même longueur                 |
| Irréversible    | Impossible de retrouver l’original        |
| Usage courant   | Sécurité, intégrité, signatures numériques |

---

<p align="center">
  <b>🔒 Un guide proposé par <a href="https://github.com/0xCyberLiTech">0xCyberLiTech</a> • Pour des tutoriels accessibles à tous. 🔒</b>
</p>
