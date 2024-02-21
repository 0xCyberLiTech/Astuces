<!-- MASTER-HEADER-START -->
<div align="center">

<a href="https://0xcyberlitech.com/">
  <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/headers/header-astuces.svg" alt="ATELIER ASTUCES & RUNBOOKS // LINUX" width="100%" />
</a>

<p align="center">
  <a href="https://0xcyberlitech.com/"><img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/btn-portal.svg" alt="Portail 0xCyberLiTech.com" width="24%" /></a>
  <a href="https://0xcyberlitech.com/soc-rd.html"><img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/btn-soc-rd.svg" alt="Livre Blanc SOC Cockpit" width="24%" /></a>
  <a href="https://0xcyberlitech.com/jarvis-rd.html"><img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/btn-jarvis-rd.svg" alt="Livre Blanc JARVIS IA" width="24%" /></a>
  <a href="https://github.com/0xCyberLiTech?tab=repositories"><img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/btn-github.svg" alt="Catalogue des 23 Dépôts" width="24%" /></a>
</p>
<p align="center">
  <a href="README.md"><img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/btn-back-readme.svg" alt="Retour au sommaire du dépôt" width="340" /></a>
</p>

<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/divider-hud.svg" alt="" width="100%" />
</div>
<!-- MASTER-HEADER-END -->

<!-- DEBIAN-TRUTH-START -->
> [!IMPORTANT]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-shield.svg" width="18" height="18" align="absmiddle" alt="" /> ** Matrice Officielle Debian — `Debian 12 (Bookworm)` · `Debian 13 (Trixie)` · `Debian 14 (Forky)`**
> - **Sources Officielles Debian.org (`systemd`) :** `Bookworm (12)` : **`252.39-1~deb12u2`** &nbsp;·&nbsp; `Trixie (13 — Stable)` : **`257.13-1~deb13u1`** &nbsp;·&nbsp; `Forky (14 — Next-Gen)` : **`262-1`**
> - **Références Officielles :** [Paquet Debian Trixie (`systemd`)](https://packages.debian.org/trixie/systemd) &nbsp;·&nbsp; [Paquet Debian Forky (`systemd`)](https://packages.debian.org/forky/systemd) &nbsp;·&nbsp; [Documentation Officielle Debian](https://www.debian.org/releases/trixie/release-notes/)
> - **Note d'Ingénierie (Divergence 13 vs 14) :** Depuis Debian 13 (Trixie) et généralisé sous Debian 14 (Forky), `/tmp` est monté en RAM (`tmpfs`) par défaut et `rsyslog` est remplacé par `systemd-journald` (`journalctl`).

<details>
<summary><img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> <b>Afficher les Encarts Ligne de Commande : Debian 13 (Trixie — Stable) vs Debian 14 (Forky — Next-Gen)</b></summary>

#### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-ok.svg" width="42" height="16" align="absmiddle" alt="[OK]" /> Profil Production Stable — Commandes pour `Debian 13 (Trixie)`
```bash
# Verification de la version Debian & des services en echec (Debian 13 Trixie) :
cat /etc/debian_version && hostnamectl
systemctl --failed && journalctl -p 3 -xb
```

#### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-rd.svg" width="46" height="16" align="absmiddle" alt="[R&D]" /> Profil Anticipation Next-Gen — Commandes pour `Debian 14 (Forky)`
```bash
# Debian 14 (Forky) — Audit APT 3.0 (Solver3) & verification du montage /tmp en RAM (tmpfs) :
apt --version && df -hT /tmp
systemd-analyze security
```

</details>
<!-- DEBIAN-TRUTH-END -->

<!-- CIEL-PEDAGOGY-START -->
<details>
<summary><img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-puzzle.svg" width="18" height="18" align="absmiddle" alt="" /> <b>Synthèse d'Architecture, Standards Officiels &amp; Diagnostic (Niveau 1 : Fondamentaux · Niveau 2 : Repères · Niveau 3 : Diagnostic)</b></summary>

- **Niveau 1 — Fondamentaux &amp; Principe d'Architecture :** L'**Ingénierie Système & Exploitation Linux (Debian 12, 13 & 14)** regroupe les procédures fondamentales d'administration : gestion des permissions POSIX, pilotage des unités `systemd`, diagnostic réseau (`iproute2`), inspection des journaux structurés (`journald`) et automatisation Bash robuste.
- **Niveau 2 — Repères Officiels (Ports IANA, Fichiers Debian &amp; Commandes de Validation) :** **Commandes de référence :** `ip -c a` & `ip -c r` (Réseau) · `ss -tulnp` (Sockets actifs) · `systemctl status <unite>` · `journalctl -xeu <unite>` · `df -hT` & `lsblk -f` (Stockage).
- **Niveau 3 — Diagnostic d'Incidents &amp; Ingénierie Avancée :** **Diagnostic & Architecture :** Avant toute modification d'un fichier de configuration en production, créez systématiquement une sauvegarde horodatée, utilisez un éditeur ou un testeur syntaxique natif, et privilégiez l'élévation nominative **`sudo`** (tracée dans les journaux d'audit) plutôt qu'une session directe sous le compte `root`.
- **Sources de Vérité Officielles Éditeurs &amp; Standards :** [Manuel Officiel de l'Administrateur Debian](https://www.debian.org/doc/manuals/debian-handbook/) &nbsp;·&nbsp; [Documentation Officielle Systemd](https://systemd.io/)

</details>
<!-- CIEL-PEDAGOGY-END -->


## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-shield.svg" width="18" height="18" align="absmiddle" alt="" /> À quoi sert VirusTotal ?
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Introduction
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

Maintenant que tu sais ce qu’est un **hash** (empreinte numérique d’un fichier ou d’un texte), voyons comment cette notion est **très utile dans la cybersécurité**, notamment avec un outil bien connu : **VirusTotal**.

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> Qu’est-ce que VirusTotal ?
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

**VirusTotal** est un service en ligne gratuit (https://www.virustotal.com) qui permet d’analyser :
- Des **fichiers**
- Des **liens (URL)**
- Des **adresses IP** ou **domaines**
- Des **hashs**

Il utilise **plus de 70 antivirus** et moteurs de détection pour vérifier si un fichier ou un site est **potentiellement malveillant**.

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> À quoi ça sert concrètement ?
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

1. **Analyser un fichier inconnu** (ex. : une pièce jointe suspecte)
2. **Vérifier la réputation d’un site web**
3. **Voir si un hash correspond à un malware connu**
4. **Inspecter une adresse IP ou un domaine (ex. : lien reçu par mail)**

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-plan.svg" width="18" height="18" align="absmiddle" alt="" /> Exemples concrets
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-ok.svg" width="42" height="16" align="absmiddle" alt="[OK]" /> Exemple 1 : Analyser un fichier

Tu télécharges un fichier étrange : `setup.exe`  
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Tu vas sur VirusTotal, tu le glisses-déposes 
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Tu vois les résultats de dizaines d’antivirus 
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Si plusieurs moteurs indiquent "trojan" ou "malware" → **danger !**

---

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-ok.svg" width="42" height="16" align="absmiddle" alt="[OK]" /> Exemple 2 : Vérifier un lien

Tu reçois ce lien par email : `http://truc-bizarre.biz/offre`  
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Tu colles l’URL sur VirusTotal 
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Il te montre si le domaine est connu comme **phishing**, **hameçonnage**, etc.

---

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-ok.svg" width="42" height="16" align="absmiddle" alt="[OK]" /> Exemple 3 : Utiliser un hash

Tu n’as pas le fichier, mais tu as un **hash SHA-256** :  
`c76a50197e2bfc330b6c9759b2ce922ea3913f7bd11e9636cf9608972dd1e4d3`  
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Tu le recherches sur VirusTotal 
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Tu obtiens les infos : nom du fichier, détection, source, etc.

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> TP simple à faire
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

1. Va sur https://www.virustotal.com
2. Téléverse un petit fichier inoffensif (ex : `.txt`) pour voir comment ça marche
3. Essaie de chercher un hash d’exemple
4. Colle une URL ou une IP pour analyser sa réputation

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> Résumé pédagogique
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

| Élément         | Description claire                        |
|-----------------|--------------------------------------------|
| VirusTotal      | Outil en ligne d’analyse de sécurité       |
| Analyse         | Fichiers, URLs, IPs, domaines, hashs       |
| Utilité         | Détecter virus, phishing, malware          |
| Fonctionnement  | Utilise des dizaines de moteurs antivirus  |
| Pratique        | Rapide, gratuit, efficace pour enquêter    |

---

VirusTotal est un **outil précieux pour tout analyste**, pentester, administrateur système ou curieux de la cybersécurité. Il permet de **vérifier rapidement** si quelque chose est suspect ou non, **sans exécuter le fichier**.

<!-- MASTER-FOOTER-START -->
<div align="center">
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/divider-hud.svg" alt="" width="100%" />

<a href="https://0xcyberlitech.com/">
  <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/footer-master.svg" alt="0xCyberLiTech — Architecture Cyberdéfense, Ingénierie Déterministe & IA Souveraine" width="100%" />
</a>

<p align="center"><a href="https://0xcyberlitech.com/"><img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/badge-antigravity.svg" alt="Architecturé par Marc & Antigravity (Google DeepMind)" width="520" /></a></p>

<sub><b>Architecturé &amp; Forgé par Marc &amp; Antigravity (Google DeepMind)</b> &nbsp;·&nbsp; <a href="https://0xcyberlitech.com/"><b>0xcyberlitech.com</b></a> &nbsp;·&nbsp; <a href="https://0xcyberlitech.com/soc-rd.html">Architecture SOC Cockpit v5.5</a> &nbsp;·&nbsp; <a href="https://0xcyberlitech.com/jarvis-rd.html">Architecture JARVIS Mark-VII</a> &nbsp;·&nbsp; <a href="https://0xcyberlitech.com/blueprint-jarvis.html">Blueprint Matériel RTX 5080</a></sub>

</div>
<!-- MASTER-FOOTER-END -->
