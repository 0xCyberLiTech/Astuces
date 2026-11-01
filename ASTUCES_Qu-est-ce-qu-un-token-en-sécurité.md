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
- **Livres Blancs &amp; 67 Podcasts Audio R&amp;D :** [Portail 0xCyberLiTech](https://0xcyberlitech.com/) &nbsp;·&nbsp; [Livre Blanc SOC Cockpit v5.5](https://0xcyberlitech.com/soc-rd.html) &nbsp;·&nbsp; [Livre Blanc JARVIS Mark-VII](https://0xcyberlitech.com/jarvis-rd.html) &nbsp;·&nbsp; [Blueprint Logiciel &amp; Matériel RTX 5080](https://0xcyberlitech.com/blueprint-jarvis.html)

</details>
<!-- CIEL-PEDAGOGY-END -->


## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-crypto.svg" width="18" height="18" align="absmiddle" alt="" /> Qu’est-ce qu’un *token* en sécurité ?
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> Objectif du document
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />
Ce document explique **ce qu’est un token**, **son rôle en cybersécurité** et **les bonnes pratiques d’implémentation**.  
Il est conçu pour :  
- **Les étudiants** qui souhaitent comprendre les bases de l’authentification moderne
- **Les professionnels** qui veulent maîtriser les aspects techniques et sécuritaires

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-brain.svg" width="18" height="18" align="absmiddle" alt="" /> Définition pédagogique
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

En cybersécurité, un **token** (ou *jeton*) est une **valeur unique générée automatiquement** permettant à un utilisateur ou un système de prouver son identité **sans envoyer son mot de passe à chaque requête**.

<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> **Exemples d’utilisation :**
- Authentification via API
- Accès sécurisé à des données dans une application web
- Communication sécurisée entre microservices

> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-plan.svg" width="18" height="18" align="absmiddle" alt="" /> **Important :** Un token ne contient pas obligatoirement des informations sensibles, mais il doit être protégé car il donne un accès à des ressources.

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-crypto.svg" width="18" height="18" align="absmiddle" alt="" /> À quoi va servir un token ?
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />
- **Authentifier** un utilisateur une seule fois, puis réutiliser le token pour prouver son identité.
- **Protéger** les communications contre les accès non autorisés.
- **Simplifier** les échanges entre applications ou services.
- **Limiter** la durée d’accès (expiration planifiée).

<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> **Exemple concret (étudiant)** : 
Quand vous vous connectez à un site, un token peut remplacer votre mot de passe pour toutes vos actions pendant un certain temps.

<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> **Exemple technique (pro)** : 
Dans une API REST, un token JWT est envoyé dans chaque requête via l’en-tête :

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```bash
> Authorization: Bearer <TOKEN>
> ```
<!-- CODE-WINDOW-END -->

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-puzzle.svg" width="18" height="18" align="absmiddle" alt="" /> Types courants de tokens
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

| Type de Token           | Usage principal                                | Exemple concret |
|-------------------------|-----------------------------------------------|----------------|
| **JWT** (*JSON Web Token*) | Authentification via APIs REST               | Connexion à un tableau de bord web |
| **OAuth Access Token**  | Accès sécurisé à des ressources tierces       | Connexion via "Se connecter avec Google" |
| **CSRF Token**          | Protection contre les attaques CSRF           | Validation d’un formulaire bancaire |
| **Session Token**       | Gestion des sessions utilisateurs             | Sites e-commerce |

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-plan.svg" width="18" height="18" align="absmiddle" alt="" /> Exemple concret : Authentification avec JWT
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> 1⃣ Connexion utilisateur
L’utilisateur saisit ses identifiants.  
Le serveur vérifie et **génère un JWT signé** contenant :  

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```json
> {
>   "sub": "123456",
>   "name": "Alice",
>   "role": "admin",
>   "exp": 1722527100
> }
> ```
<!-- CODE-WINDOW-END -->

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> 2⃣ Envoi du token au client
Le serveur retourne le token au navigateur, qui peut le stocker dans :
- **Cookie sécurisé (`HttpOnly`, `Secure`)**
- **Mémoire d’application (variable locale)**

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> 3⃣ Utilisation pour accéder à une API
À chaque appel API :  

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```bash
> Authorization: Bearer <TOKEN>
> ```
<!-- CODE-WINDOW-END -->

### <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> 4⃣ Vérification côté serveur
- Vérification **signature** <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-ok.svg" width="42" height="16" align="absmiddle" alt="[OK]" /> 
- Vérification **expiration** <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-rd.svg" width="46" height="16" align="absmiddle" alt="[R&D]" /> 
- Vérification **permissions** <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-crypto.svg" width="18" height="18" align="absmiddle" alt="" /> 

Si tout est OK → accès autorisé.

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-ok.svg" width="42" height="16" align="absmiddle" alt="[OK]" /> Avantages des tokens
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

| Avantage | Explication |
|----------|-------------|
| **Sans état** (*stateless*) | Pas besoin de stocker la session côté serveur |
| **Sécurisé** | Signature et chiffrement possibles |
| **Flexible** | Fonctionne sur web, mobile, API |
| **Scalable** | Idéal pour microservices et environnements distribués |

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-alert.svg" width="18" height="18" align="absmiddle" alt="" /> Bonnes pratiques
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

- Signer et chiffrer les tokens contenant des données sensibles
- Définir une **expiration courte** (ex : 15 minutes)
- Stocker côté client **de manière sécurisée** (éviter `localStorage`)
- Révoquer un token compromis
- Utiliser **HTTPS uniquement** pour éviter l’interception

<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-target.svg" width="18" height="18" align="absmiddle" alt="" /> **Exemple de création sécurisée en Node.js :**

<!-- CODE-WINDOW-START -->
> [!CAUTION]
> <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-code-red.svg" width="100%" alt="TERMINAL // BLOC DE CODE" />
>
> ```bash
> const jwt = require('jsonwebtoken');
> const token = jwt.sign(
>   { userId: 123, role: 'admin' },
>   process.env.JWT_SECRET,
>   { expiresIn: '15m' }
> );
> ```
<!-- CODE-WINDOW-END -->

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-doc.svg" width="18" height="18" align="absmiddle" alt="" /> Conclusion
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

Les tokens sont essentiels pour une **authentification moderne, sécurisée et performante**.  
Bien implémentés, ils permettent :
- D’améliorer la sécurité
- De faciliter les connexions multi-plateformes
- D’offrir une expérience utilisateur fluide

---

## <img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/icons/wire-network.svg" width="18" height="18" align="absmiddle" alt="" /> Références utiles
<img src="https://raw.githubusercontent.com/0xCyberLiTech/0xcyberlitech/main/assets/glow-section-cyan.svg" width="100%" alt="" />

- [JWT.io - Introduction aux JWT](https://jwt.io/introduction)  
- [OAuth 2.0 - RFC 6749](https://datatracker.ietf.org/doc/html/rfc6749)  
- [OWASP - API Security](https://owasp.org/www-project-api-security/)  

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
