<div align="center">

  <a href="https://github.com/0xCyberLiTech">
    <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=32&pause=1000&color=D14A4A&center=true&vCenter=true&width=800&lines=ASTUCES+SÉCURITÉ+LINUX;Pare-feu+•+Permissions+•+Surveillance;Scripts+•+Audit+•+Bonnes+Pratiques" alt="Typing SVG" />
  </a>


  <p align="center">
    <em>Introduction à l'utilisation des Sandbox en Cybersécurité.</em><br>
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

### 🎯 **Objectif de ce dépôt.**

> Ce dépôt a pour vocation de centraliser un ensemble de bonnes pratiques, d'astuces et de notions clés autour de la sécurité sous Linux.
> Il s’adresse aux passionnés, étudiants et professionnels souhaitant renforcer leurs compétences en sécurisation des systèmes GNU/Linux.
> L’objectif est de fournir des conseils concrets pour durcir un système, comprendre les risques courants, et maîtriser les outils essentiels pour auditer, surveiller et sécuriser efficacement son environnement Linux, que ce soit en poste de travail, serveur ou infrastructure cloud.

---

# 🧪 Introduction à l'utilisation des Sandbox en Cybersécurité

## 🎯 Objectif

Comprendre ce qu’est une **sandbox** (bac à sable) en cybersécurité, comment elle fonctionne et **comment l’utiliser de manière pédagogique** pour analyser des fichiers ou des programmes suspects **en toute sécurité**.

---

## 🧰 Qu’est-ce qu’une Sandbox ?

Une **sandbox** est un **environnement isolé**, sécurisé, conçu pour **exécuter du code ou ouvrir des fichiers** sans risque pour le système principal.

➡️ Elle agit comme une **zone tampon** : même si le fichier contient un virus, il ne peut pas sortir de cet environnement contrôlé.

---

## 🛡️ Pourquoi utiliser une sandbox ?

| Usage principal               | Explication                                  |
|------------------------------|----------------------------------------------|
| Analyse de fichiers suspects | Ouvrir un `.exe`, `.pdf`, `.docm` à risque   |
| Étude de malware             | Observer le comportement d’un virus          |
| Formation et tests           | Tester des scripts ou outils en toute sécurité |
| Développement sécurisé       | Tester du code sans impact sur l’OS principal |

---

## 🎮 Exemple simple d'utilisation

### 🧪 Scénario : On t'envoie un fichier nommé `facture_client.exe`

Tu as un doute. Voici **comment tu peux analyser le fichier sans risque** :

### Étapes :
1. Ouvre ta **sandbox** (ex : machine virtuelle, Firejail, Cuckoo, ou outil cloud)
2. Copie le fichier dans la sandbox (jamais sur ton poste principal)
3. Ouvre le fichier dans l’environnement isolé
4. Observe :
   - Lancement de processus inconnus ?
   - Connexions réseau étranges ?
   - Création de fichiers ou modification système ?
5. Si le fichier est malveillant, **il n’impactera que la sandbox**

---

## 💻 Outils populaires pour sandboxing

| Outil / Service      | Description rapide                            |
|----------------------|-----------------------------------------------|
| 🖥️ **Cuckoo Sandbox** | Sandbox open-source pour l’analyse de malware |
| 🔒 **Firejail (Linux)** | Isoler des programmes individuellement        |
| 💻 **VM VirtualBox / VMware** | Machines virtuelles (Windows, Linux, etc.)    |
| ☁️ **Any.Run**         | Sandbox interactive en ligne (freemium)       |
| ☁️ **Joe Sandbox**      | Analyse cloud poussée (version gratuite dispo) |

---

## 📦 Exemple sous Linux avec Firejail

```bash
sudo apt install firejail

# Isoler Firefox
firejail firefox

# Isoler l'ouverture d'un PDF
firejail evince fichier-suspect.pdf
```

---

## 🧠 Conseils pratiques

- ❌ **Ne jamais ouvrir un fichier suspect directement sur ton poste principal**
- ✅ **Toujours copier les fichiers dans la sandbox AVANT exécution**
- 🧪 Combine avec **VirusTotal** avant/après pour plus d’informations
- 🔌 Si ta sandbox est connectée à Internet, surveille le trafic réseau

---

## 🧱 Sandbox ≠ Solution miracle

- ⚠️ Certains malwares détectent qu’ils sont dans une sandbox et **n’activent pas leur charge utile**
- 🔍 Complète l’analyse avec des outils comme :
  - Wireshark (réseau)
  - Procmon (processus)
  - Regshot (registre, fichiers)

---

## 📚 Résumé pédagogique

| Élément             | Rôle / But                                      |
|---------------------|-------------------------------------------------|
| Sandbox             | Environnement isolé pour tests sécurisés        |
| Utilisation         | Analyse de fichiers douteux ou malwares         |
| Exécution           | Dans VM, Firejail, Cuckoo, ou en ligne          |
| Avantage            | Risque limité, aucun impact système réel        |
| Limite              | Certains malwares contournent les sandbox       |

---

## 🏁 Conclusion

Une **sandbox est un outil fondamental** pour tout étudiant, analyste ou passionné de cybersécurité. Elle permet d’apprendre, de tester et d’enquêter **sans risquer de compromettre sa machine principale**.

---

<p align="center">
  <b>🔒 Un guide proposé par <a href="https://github.com/0xCyberLiTech">0xCyberLiTech</a> • Pour des tutoriels accessibles à tous. 🔒</b>
</p>

| 05  | Introduction à l'utilisation des Sandbox en Cybersécurité       | [![Voir](https://img.shields.io/badge/Voir-01-blue)](ASTUCES-Introduction-à-l-utilisation-des-Sandbox-en-Cybersécurité.md) |
