# Mettre la landing page en ligne

Quatre fichiers à mettre en ligne ensemble : `index.html`, `equipe.webp` (la photo), `mentions-legales.html`, `confidentialite.html`.

## 1. Relier le formulaire au Google Sheet

Chaque préinscription s'ajoute comme une ligne dans un Google Sheet privé. Le script qui fait ce travail est dans `../google-sheets/Code.gs` : il ne fait pas partie du site, ne le mettez pas en ligne.

1. Créez un Google Sheet, par exemple « Préinscriptions NAPA ».
2. Menu **Extensions → Apps Script**. Effacez le contenu du fichier `Code.gs` affiché, collez à la place tout le contenu de `google-sheets/Code.gs`, puis enregistrez.
3. **Déployer → Nouveau déploiement**. Cliquez sur la roue dentée et choisissez **Application Web** :
   - Exécuter en tant que : **Moi** ;
   - Qui peut accéder : **Tout le monde** ;
   - cliquez sur **Déployer**.
4. Google demande d'autoriser l'accès. Choisissez votre compte. Si l'écran « Google n'a pas validé cette application » apparaît, c'est normal pour un script personnel : **Paramètres avancés → Accéder à … (non sécurisé) → Autoriser**.
5. Copiez l'**URL de l'application Web** (elle se termine par `/exec`). En l'ouvrant dans un navigateur, vous devez lire « Le formulaire NAPA est bien relié à ce Google Sheet. »
6. Dans `index.html`, collez-la dans `const SHEET_URL = "";`.
7. Faites une préinscription de test sur la page en ligne : une ligne doit apparaître dans l'onglet **Réponses** du Google Sheet (créé automatiquement à la première réponse).

Tant que `SHEET_URL` est vide, la page affiche « Mode démo » après l'envoi et rien n'est enregistré.

Si vous modifiez le script plus tard : **Déployer → Gérer les déploiements → crayon → Version : Nouvelle version**. L'URL reste la même.

Pour travailler dans Excel : **Fichier → Télécharger → Microsoft Excel (.xlsx)**.

Les colonnes du tableau :

| Colonne | Contenu |
|---|---|
| Date | date et heure de la réponse |
| E-mail | saisi par la personne |
| Missions | missions cochées, séparées par « ; » (ex. `Garde d'enfants ; Cours particuliers`) |
| Niveau | niveaux cochés pour les cours (Collège, Lycée, Prépa…) |
| Plus enclin (étudiants) | réponse à « Seriez-vous plus enclin·e à utiliser une plateforme qui fait travailler des étudiants ? » : `Oui, beaucoup plus`, `Oui, un peu plus`, `Ça ne change rien`, `Plutôt moins`, ou vide |
| Idées | texte libre « Vos idées ou remarques » |
| Tenu au courant | `oui` / `non`. Envoyez les nouvelles du projet seulement aux `oui` ; aux `non`, uniquement l'annonce du lancement |
| Entretien | `oui` si la personne accepte un échange de 10 minutes |
| Profil | toujours `particulier` sur cette page |
| Source | origine du QR code (voir étape 3) |

Le script retrouve chaque colonne par son titre. Une colonne qui manque est ajoutée à droite (c'est le cas de « Plus enclin (étudiants) » dans un Sheet créé avant cette question). Les anciennes colonnes Prénom et Quartier ne sont plus remplies : vous pouvez les garder ou les supprimer. Ne renommez pas les autres titres de colonne.

Le Google Sheet reste privé : l'adresse `/exec` permet seulement d'y ajouter des lignes, pas de les lire. Ne partagez pas le tableur au-delà de l'équipe.

## 2. Héberger la page

Hébergeur gratuit en HTTPS avec votre nom de domaine, par exemple Netlify, Cloudflare Pages ou GitHub Pages : on y dépose le dossier `landing/`, puis on branche le domaine NAPA dans les réglages.

Avant la diffusion, complétez les passages surlignés `[…]` dans `mentions-legales.html` et `confidentialite.html` (noms, adresse, e-mail de contact, hébergeur).

## 3. Créer les QR codes de l'affiche

Le QR code actuel de `Affiche-NAPA` ne pointe pas vers la page : remplacez-le une fois la page en ligne.

Idéalement, un QR code par lieu de diffusion, avec un paramètre `src` différent pour savoir lequel fonctionne le mieux :

- `https://votre-domaine.fr/?src=affiche-college-x`
- `https://votre-domaine.fr/?src=affiche-boulangerie-ile-verte`
- `https://votre-domaine.fr/?src=affiche-ape-ecole-y`

Gardez une marge blanche autour du QR code et une taille d'au moins 3 cm sur l'affiche pour qu'il se scanne de loin.

La valeur arrive dans la colonne « Source » du Google Sheet.
