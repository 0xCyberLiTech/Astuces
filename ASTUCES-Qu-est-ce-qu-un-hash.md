








# 🔐 Qu’est-ce qu’un Hash ? (Cours pédagogique)

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








