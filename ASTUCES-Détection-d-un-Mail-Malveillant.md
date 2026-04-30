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

# 📧 Détection d’un Mail Malveillant.

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

<b>🔒 Un projet proposé par <a href="https://github.com/0xCyberLiTech">0xCyberLiTech</a> • Développé en collaboration avec <a href="https://claude.ai">Claude AI</a> (Anthropic) 🔒</b>

</div>
