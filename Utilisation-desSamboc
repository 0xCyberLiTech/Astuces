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

