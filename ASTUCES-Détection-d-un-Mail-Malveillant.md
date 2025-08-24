<div align="center">

  <br></br>
  
  <a href="https://github.com/0xCyberLiTech">
    <img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=50&duration=6000&pause=1000000000&color=FF0048&center=true&vCenter=true&width=1100&lines=%3EASTUCES_" alt="Titre dynamique ASTUCES" />
  </a>
  
  <br></br>

  <p align="center">
    <em>Détection d’un Mail Malveillant.</em><br>
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

### 👨‍💻 **À propos de moi.**

> Bienvenue dans mon **laboratoire numérique personnel** dédié à l’apprentissage et à la vulgarisation de la cybersécurité.  
> Passionné par **Linux**, la **cryptographie** et les **systèmes sécurisés**, je partage ici mes notes, expérimentations et fiches pratiques.  
> Proposer un contenu clair, structuré et accessible pour étudiants, curieux et professionnels de l’IT.  

<p align="center">
  <a href="https://github.com/0xCyberLiTech" target="_blank" rel="noopener">
    <img src="https://skillicons.dev/icons?i=linux,debian,bash,docker,nginx,git,vim,python,markdown" alt="Skills" width="420">
  </a>
</p>

---

# 📧 Détection d’un Mail Malveillant.

## 🎯 Objectif

> - Apprendre à **analyser un e-mail suspect** à travers un **exemple fictif**, en appliquant une **méthodologie simple et claire**. 
> - Ce scénario est un exercice pour s’entraîner à repérer les signes d’un **mail malveillant**.

---

## 🧪 Exemple de mail reçu

```
De : Sécurité PayPal <support-client@secure-paypal.fr>
Objet : URGENT – Votre compte sera suspendu dans 24h

Bonjour,

Nous avons détecté une activité suspecte sur votre compte PayPal. Veuillez vérifier votre identité immédiatement pour éviter la suspension.

Cliquez ici pour confirmer : http://paypal-verif.compte-securise.ru/login

Merci de votre réactivité.
L'équipe sécurité PayPal.
```

---

## 🕵️‍♂️ Analyse étape par étape

### 1. ✅ **Adresse de l’expéditeur**

- **Affichée** : support-client@secure-paypal.fr
- ❌ Ce n’est pas un domaine officiel de PayPal (`paypal.com`)
- 🧠 **Méfiance si le domaine semble imiter une marque connue**

---

### 2. 📛 **Objet du message**

- **Objet** : “URGENT – Votre compte sera suspendu dans 24h”
- ❌ Utilise la peur pour pousser à l’action rapide
- ⚠️ Les escrocs créent un sentiment d’urgence (pression psychologique)

---

### 3. 🔗 **Lien suspect**

- **Affiché** : “Cliquez ici pour confirmer”
- **Cible réelle** (hover souris) : `http://paypal-verif.compte-securise.ru/login`
- ❌ Ne correspond pas au domaine légitime
- ✅ Test : copier le lien dans [https://www.virustotal.com](https://www.virustotal.com)

---

### 4. 📎 **Aucune pièce jointe ici**, mais à surveiller

- Si `.pdf`, `.docm`, `.exe`, `.zip` → extrême prudence
- Ne jamais ouvrir sans analyse préalable (VirusTotal, sandbox, etc.)

---

### 5. 🧪 **Analyse des en-têtes (facultatif mais utile)**

- Afficher les **en-têtes complets** du mail
- Examiner les champs :
  - `Return-Path` → incohérent avec l’expéditeur ?
  - `SPF`, `DKIM`, `DMARC` → signatures absentes ou invalides ?
- Utiliser un outil en ligne :
  - [https://mxtoolbox.com/EmailHeaders.aspx](https://mxtoolbox.com/EmailHeaders.aspx)

---

## ✅ Conclusion

| Élément          | Analyse                                | Verdict        |
|------------------|-----------------------------------------|----------------|
| Expéditeur       | Domaine trompeur                        | ❌ Suspect      |
| Objet            | Urgence, menace                         | ❌ Manipulatif  |
| Lien             | Ne pointe pas vers PayPal               | ❌ Dangereux    |
| Ton du message   | Trop alarmiste                          | ❌ Alarmant     |
| Vérification VT  | (à faire sur le lien)                   | Probablement malveillant |

---

## 🛡️ Recommandations

- **Ne jamais cliquer** sur un lien suspect
- **Ne pas répondre** au message
- **Signaler** le mail comme phishing à votre service informatique ou au fournisseur de messagerie
- **Analyser** via [VirusTotal](https://virustotal.com)

---

## 🧠 Astuce : comment vérifier un lien sans cliquer

- Survoler le lien avec la souris (hover)
- Comparer le lien réel avec le lien affiché
- Si le domaine semble étrange ou contient des variantes (ex: `paypa1`, `-secure`, `.ru`), **ne clique pas**

---

## 📚 À retenir

> Tout e-mail demandant une action urgente, contenant un lien douteux, ou provenant d’un domaine inconnu doit être traité comme **potentiellement malveillant**.

---

<p align="center">
  <b>🔒 Un guide proposé par <a href="https://github.com/0xCyberLiTech">0xCyberLiTech</a> • Pour des tutoriels accessibles à tous. 🔒</b>
</p>
