# Site de Thomas Aznar — mise en ligne avec GitHub Pages

Adresse du site : https://valentinaznar.github.io/site-thomas-aznar/
Back-office : https://valentinaznar.github.io/site-thomas-aznar/admin/

## Ce que contient ce dossier
- `index.html` : le site (Films, Qui suis-je, Contact)
- `admin/` : le back-office
- `contenu.json` : tous les textes du site (modifié par le back-office)
- `images/` : les images (`films/` au départ, `uploads/` pour celles ajoutées depuis le back-office)
- `config.js` : compte GitHub, dépôt et adresse du formulaire
- `style.css` : la mise en forme

## 1. Activer GitHub Pages
Dépôt → Settings → Pages → Source : « Deploy from a branch » → Branch : `main`, dossier `/ (root)` → Save.
Une ou deux minutes plus tard, le site est en ligne à l'adresse ci-dessus.

## 2. Relier le formulaire de contact (Formspree, gratuit jusqu'à 50 messages par mois)
1. Créer un compte sur formspree.io avec l'adresse e-mail qui doit recevoir les messages.
2. « New form », nom « Contact site Thomas ».
3. Copier l'adresse du formulaire (du type `https://formspree.io/f/abcdwxyz`).
4. Dans GitHub, ouvrir `config.js` → crayon → coller l'adresse entre les guillemets de `formulaire: ""` → Commit changes.
5. Au premier message reçu, Formspree peut demander de confirmer l'adresse e-mail : cliquer sur le lien reçu.

## 3. Créer la clé du back-office
1. Aller sur github.com/settings/personal-access-tokens/new
2. Nom : « Back-office site Thomas ». Expiration : 1 an.
3. Repository access : « Only select repositories » → `site-thomas-aznar`.
4. Permissions → Contents : « Read and write ».
5. « Generate token », copier la clé (`github_pat_…`).
6. Ouvrir le back-office, coller la clé, « Se connecter ».

Ne jamais mettre cette clé dans un fichier du dépôt.

## Au quotidien
- Contenus (films, textes, prix, images) : via le back-office, puis « Publier » une seule fois. Le site est à jour en quelques minutes.
- Fichiers de code : les déposer sur GitHub comme d'habitude (Add file → Upload files). GitHub Pages est gratuit et ne compte pas de crédits.
