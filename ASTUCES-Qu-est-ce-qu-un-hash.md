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

---

### 👨‍💻 **À propos de moi**

> Bienvenue sur le dépôt <strong>0xCyberLiTech</strong>, votre laboratoire numérique pour l'<strong>apprentissage</strong> et la <strong>vulgarisation</strong> de la <strong>cybersécurité</strong>, de l'<strong>administration Linux Debian</strong> et de la <strong>sécurité informatique</strong>.
> Passionné par <strong>Linux</strong>, la <strong>cryptographie</strong>, la <strong>supervision réseau</strong> et les <strong>systèmes sécurisés</strong>, je partage ici des <strong>tutoriels</strong>, <strong>guides pratiques</strong>, <strong>fiches techniques</strong> et <strong>retours d'expérience</strong> pour renforcer vos compétences IT.
>
> 🎯 <strong>Objectif :</strong> Offrir un contenu structuré, accessible et optimisé pour le référencement naturel, destiné aux étudiants, professionnels, administrateurs système, experts en sécurité et curieux du monde numérique.

<p align="center">
  <a href="https://github.com/0xCyberLiTech" target="_blank" rel="noopener">
    <img src="https://skillicons.dev/icons?i=linux,debian,bash,docker,nginx,git,vim,python,markdown" alt="Skills" width="420">
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
