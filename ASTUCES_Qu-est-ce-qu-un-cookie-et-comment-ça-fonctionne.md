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


## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Qu'est-ce qu'un cookie et comment ça fonctionne ?
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> Objectif du document
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />
Ce document explique **ce qu’est un cookie**, **son rôle dans le web** et **les bonnes pratiques de sécurité**.  
Il s’adresse **à la fois** :
- Aux **étudiants** qui souhaitent comprendre les bases
- Aux **professionnels** qui veulent maîtriser les aspects techniques et réglementaires

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> 1. Définition d’un cookie
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

Un **cookie** (ou *témoin de connexion*) est un **petit fichier texte** stocké par le navigateur lorsqu’un utilisateur visite un site web.  
Il permet au site de **mémoriser des informations** et de **reconnaître l’utilisateur** lors de visites ultérieures.

> **<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-plan.svg" width="18" height="18" align="absmiddle" alt="" /> Important** : Un cookie **n’est pas** un programme exécutable. 
> Il ne peut pas infecter un ordinateur directement et ne donne pas accès à d’autres fichiers.

<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> **Exemple concret (étudiant)** : 
Si vous cochez *"Se souvenir de moi"* sur un site de réseau social, un cookie est créé pour éviter que vous ne vous reconnectiez à chaque visite.

<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> **Exemple technique (pro)** : 
Un serveur envoie l’en-tête :

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```bash
> Set-Cookie: user_id=12345; HttpOnly; Secure; SameSite=Strict
> ```
<!-- CODE-WINDOW-END -->

Cela crée un cookie côté navigateur avec la valeur `12345` qui :
- Ne peut être lu par JavaScript (`HttpOnly`)
- Est transmis uniquement en HTTPS (`Secure`)
- N’est envoyé que si la requête provient du même site (`SameSite=Strict`)

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> 2. Pourquoi les cookies existent-ils ?
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

Les cookies facilitent **l’expérience utilisateur** et permettent certaines fonctionnalités clés du web.

| Usage | Exemple concret |
|-------|----------------|
| **Session** | Rester connecté à un site sans ressaisir son mot de passe |
| **Préférences** | Sauvegarder la langue d’affichage ou le thème clair/sombre |
| **Panier d’achat** | Mémoriser les articles ajoutés sans être connecté |
| **Analyse d’audience** | Compter les visites sur un site web |
| **Publicité ciblée** | Afficher des pubs liées à vos recherches précédentes |

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> 3. Cycle de vie d’un cookie
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> Schéma simplifié

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```bash
> [Visite du site] → [Réponse serveur : Set-Cookie] → [Stockage navigateur]
> → [Requêtes suivantes : Cookie envoyé] → [Serveur lit le cookie]
> ```
<!-- CODE-WINDOW-END -->

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-puzzle.svg" width="18" height="18" align="absmiddle" alt="" /> Exemple HTTP

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```bash
> HTTP/1.1 200 OK
> Set-Cookie: session_id=abc123; Expires=Wed, 01 Jan 2026 00:00:00 GMT; Path=/; Secure; HttpOnly
> ```
<!-- CODE-WINDOW-END -->

- `session_id` = nom du cookie  
- `abc123` = valeur stockée  
- `Expires` = date d’expiration  
- `Secure` = uniquement via HTTPS  
- `HttpOnly` = inaccessible en JavaScript

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> 4. Types de cookies
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

| Type | Description | Exemple |
|------|-------------|---------|
| **Session** | Disparaît à la fermeture du navigateur | Connexion temporaire à un site |
| **Persistant** | Expire à une date précise | Sauvegarde d’un panier d’achat |
| **Propriétaire** | Déposé par le site visité | `example.com` |
| **Tiers** | Déposé par un autre domaine | Publicité, tracking |
| **Fonctionnel** | Indispensable au site | Authentification |
| **Analytique** | Mesure l’audience | Google Analytics |
| **Publicitaire** | Ciblage publicitaire | Bannière pub personnalisée |

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> 5. Où sont stockés les cookies ?
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

Chaque navigateur (Chrome, Firefox, Edge, Safari…) stocke les cookies dans **un fichier interne sécurisé**.  
Ils sont classés **par nom de domaine** pour éviter que deux sites différents ne puissent lire les cookies l’un de l’autre.

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> 6. Sécurité et vie privée
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-alert.svg" width="18" height="18" align="absmiddle" alt="" /> Risques potentiels
- **Vol de session** (*Session Hijacking*) via attaques XSS si `HttpOnly` n’est pas utilisé
- **Tracking publicitaire** à travers plusieurs sites
- **Fingerprinting** : profilage détaillé de l’utilisateur

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-ok.svg" width="42" height="16" align="absmiddle" alt="[OK]" /> Bonnes pratiques développeur
- **Toujours utiliser** `Secure`, `HttpOnly` et `SameSite`
- **Limiter la durée de vie** des cookies
- **Ne jamais stocker d’informations sensibles** en clair

<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> Exemple sécurisé :

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```bash
> Set-Cookie: token=xyz789; Max-Age=1800; HttpOnly; Secure; SameSite=Strict
> ```
<!-- CODE-WINDOW-END -->

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> 7. Gestion des cookies en JavaScript
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

**Création**

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```bash
> document.cookie = "theme=dark; path=/; max-age=3600;";
> ```
<!-- CODE-WINDOW-END -->

**Lecture**

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```bash
> console.log(document.cookie);
> ```
<!-- CODE-WINDOW-END -->

**Suppression**

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```bash
> document.cookie = "theme=; Max-Age=0";
> ```
<!-- CODE-WINDOW-END -->

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> 8. Gestion des cookies côté utilisateur
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

- Supprimer via **Paramètres du navigateur**
- Utiliser la **navigation privée**
- Installer un **bloqueur de traqueurs** :  
  - [uBlock Origin](https://ublockorigin.com/)  
  - [Privacy Badger](https://privacybadger.org/)

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> 9. Alternatives aux cookies
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

| Alternative | Avantages | Limites |
|-------------|-----------|---------|
| **LocalStorage** | Grande capacité, persistant | Accessible en JS (moins sécurisé) |
| **SessionStorage** | Disparaît à la fermeture de l’onglet | Non partagé entre onglets |
| **IndexedDB** | Base de données locale | Complexité d’utilisation |
| **Fingerprinting** | Pas besoin de cookies | Très intrusif, réglementé |

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-ok.svg" width="42" height="16" align="absmiddle" alt="[OK]" /> Résumé
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

| Élément | Description |
|---------|-------------|
| **Définition** | Petit fichier texte stocké par le navigateur |
| **Utilité** | Sessions, préférences, analyse |
| **Types** | Session, persistant, tiers… |
| **Sécurité** | `Secure`, `HttpOnly`, `SameSite` |
| **Vie privée** | RGPD, CNIL, consentement utilisateur |

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Références
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />
- [Mozilla - Cookies (MDN)](https://developer.mozilla.org/fr/docs/Web/HTTP/Cookies)  
- [CNIL - Guide cookies & traceurs](https://www.cnil.fr/fr/cookies-et-autres-traceurs)  
- [OWASP - Secure Cookie Attributes](https://owasp.org/www-community/controls/SecureCookieAttribute)

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
