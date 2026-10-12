# Portail Personnel & Projets — bizid.fr

Ce dossier contient le code source du site principal **`bizid.fr`**, conçu pour remplacer l'ancien blog Tumblr par un portail personnel moderne, sobre, ultra-rapide et hébergé gratuitement sur **GitHub Pages**.

---

## 🌟 Caractéristiques du site

- **Design épuré et moderne** (inspiré des standards Vercel / Apple / Linear).
- **Thème sombre & clair** avec basculement automatique et mémorisation du choix.
- **Hub de projets** :
  - Accès direct à l'application **Roulement SNCF 2027** (`https://roulement.bizid.fr`).
  - Section Lab pour vos scripts Pine Script, automatisations et projets futurs.
- **Section Contact** : lien e-mail direct vers `riadh@bizid.fr` avec bouton de copie en un clic.
- **100% autonome et léger** (< 25 Ko, aucun framework lourd, zéro traceur ni cookie).

---

## 🚀 Déploiement sur GitHub Pages (en 3 étapes)

### Étape 1 : Créer le dépôt sur GitHub
1. Rendez-vous sur votre compte [GitHub](https://github.com/ribayza).
2. Créez un nouveau dépôt public (ex: **`ribayza.github.io`** ou **`bizid-portal`**).
3. Poussez les fichiers de ce dossier (`index.html` et `CNAME`) sur ce dépôt.

### Étape 2 : Activer GitHub Pages
1. Dans le dépôt GitHub, allez dans **Settings** > **Pages**.
2. Source : sélectionnez la branche `main` (ou `master`) et le dossier `/ (root)`.
3. Sous **Custom domain**, vérifiez que `bizid.fr` est bien renseigné.
4. Cochez **Enforce HTTPS** (dès que le certificat SSL est généré).

---

## 🌐 Configuration DNS (Chez votre Registrar : OVH, Gandi, Cloudflare...)

Pour faire pointer `bizid.fr` vers GitHub Pages et **quitter Tumblr**, modifiez votre zone DNS :

### 1. Remplacer l'ancienne adresse IP Tumblr par GitHub Pages
Supprimez l'enregistrement `A` qui pointait vers Tumblr (`66.6.44.4`) et ajoutez les 4 enregistrements `A` officiels de GitHub :

| Type | Nom d'hôte | Valeur cible / IP |
| :--- | :--- | :--- |
| **A** | `@` (ou vide) | `185.199.108.153` |
| **A** | `@` (ou vide) | `185.199.109.153` |
| **A** | `@` (ou vide) | `185.199.110.153` |
| **A** | `@` (ou vide) | `185.199.111.153` |

### 2. Configurer le sous-domaine `www`
| Type | Nom d'hôte | Valeur cible |
| :--- | :--- | :--- |
| **CNAME** | `www` | `ribayza.github.io.` |

### 3. Sous-domaine existant du Roulement (Ne pas toucher)
Conservez votre enregistrement existant :
| Type | Nom d'hôte | Valeur cible |
| :--- | :--- | :--- |
| **CNAME** | `roulement` | `ribayza.github.io.` |

### ⚠️ Important : Préservation de vos e-mails (`riadh@bizid.fr`)
**Ne supprimez ni ne modifiez aucun enregistrement de type MX, TXT (SPF/DKIM)**. Ces enregistrements gèrent votre messagerie électronique et sont totalement indépendants du site web.
