# Site de Thomas Aznar — mise en ligne

## Ce que contient ce dossier
- `index.html` : le site (Films, Qui suis-je, Contact)
- `admin/` : le back-office, à l'adresse `/admin`
- `contenu.json` : tous les textes du site (modifié par le back-office)
- `images/` : les images (`films/` au départ, `uploads/` pour celles ajoutées depuis le back-office)
- `config.js` : le nom du compte GitHub et du dépôt (à remplir, étape 2)
- `style.css`, `netlify.toml` : mise en forme et réglages Netlify

## 1. Créer le dépôt GitHub
1. Sur GitHub : « New repository », nom `site-thomas-aznar`, **Public**, sans README.
2. « uploading an existing file » : glisser **tout le contenu** du dossier (pas le dossier lui-même) en une seule fois.
3. Message du commit : « Première version », puis « Commit changes ».

## 2. Renseigner config.js
Dans GitHub, ouvrir `config.js` → crayon (Edit), remplacer `owner: ""` par ton nom d'utilisateur GitHub, par ex. `owner: "valentin-dupont"`. Valider (« Commit changes »).

## 3. Relier à Netlify
1. Netlify → « Add new project » → « Import an existing project » → GitHub → `site-thomas-aznar`.
2. Laisser la commande de build vide, dossier de publication `.` → « Deploy ».
3. Project configuration → « Change project name » → `thomas-aznar` → adresse : `thomas-aznar.netlify.app`.

## 4. Activer le formulaire de contact
1. Netlify → le projet → **Forms** → « Enable form detection ».
2. Relancer une mise en ligne une fois (Deploys → « Trigger deploy » → « Deploy project ») pour que le formulaire soit détecté.
3. Forms → « Form notifications » → « Add notification » → « Email notification » → adresse de Thomas.

## 5. Créer la clé du back-office
1. GitHub → photo de profil → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → « Generate new token ».
2. Nom : « Back-office site Thomas ». Expiration : 1 an (à renouveler ensuite).
3. Repository access : « Only select repositories » → `site-thomas-aznar`.
4. Permissions → Repository permissions → **Contents : Read and write**.
5. Générer, copier la clé, l'ouvrir dans `thomas-aznar.netlify.app/admin` et la coller.

Ne jamais mettre cette clé dans un fichier du dépôt.

## Au quotidien
- **Contenus** (films, textes, prix, images) : via `/admin`, puis « Publier » une seule fois. Rien n'est redéployé sur Netlify : le site lit les contenus directement dans GitHub. Les changements apparaissent en général en quelques minutes.
- **Changement de design ou de code** (nouveau fichier `index.html`, etc.) : déposer tous les fichiers en **un seul** envoi sur GitHub = une seule mise en ligne Netlify. Pour un envoi qui ne doit pas déclencher de mise en ligne, ajouter `[skip netlify]` dans le message du commit.
