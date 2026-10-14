# Mettre en ligne le classeur virtuel de 6e

## Fonctionnement

- **Pour les élèves et les parents :** un seul lien internet ; aucun compte, aucune installation.
- **Pour le professeur :** déposer des PDF, JPG ou PNG dans les dossiers prévus. Ils seront affichés au prochain déploiement du site (généralement en quelques minutes), dans l’ordre des noms de fichiers.
- Les fiches sont **avant** les six intercalaires, pas dans un septième intercalaire.
- Chaque fichier PDF correspond à une seule feuille du classeur, même pour les livrets de plusieurs pages : seule sa première page est prévisualisée, et le bouton « Ouvrir / imprimer » donne accès à l’ensemble du document.
- Les cases « Bien rangé » mémorisent uniquement les choix de l'élève dans **son navigateur** (pas de collecte de données d'élèves). Elles ne sont pas synchronisées entre appareils.

## Installation UNE SEULE FOIS

1. Créer ou ouvrir un compte sur [github.com](https://github.com).
2. Créer un nouveau dépôt **public** nommé `classeur-6e` (nom modifiable). Éviter de cocher « Add a README » pour démarrer avec un dépôt vide.
3. Décompresser l'archive `classeur_6e_site_web.zip` sur son ordinateur.
4. Dans le dépôt GitHub, choisir **uploading an existing file**, ou **Add file > Upload files**, puis **glisser tous les éléments** à la racine de l'archive (`index.html`, `catalogue.json`, `_config.yml` et tout le dossier `documents`). Valider avec **Commit changes**. Vérifier que les sous-dossiers sont bien présents.
5. Dans le dépôt, ouvrir **Settings > Pages** puis, sous « Build and deployment », choisir **Deploy from a branch** ; sélectionner `main`, puis `/(root)` ; **Save**.
6. Après publication, le classeur sera visible à l'adresse `https://VOTRE-PSEUDO.github.io/classeur-6e/` (adapter le pseudo et le nom de dépôt). Vérifier l'URL exacte indiquée dans Settings > Pages.
7. Mettre ce lien dans Pronote, par exemple en lien accessible aux familles.

## Mise à jour en autonomie : à chaque nouvelle fiche

1. Sur GitHub, entrer dans le dépôt `classeur-6e` et ouvrir le dossier `documents`.
2. Ouvrir le bon sous-dossier :
   - `00-fiches` = feuilles tout au début du classeur
   - `01-activites` = intercalaire 1, Activités
   - `02-competences` = intercalaire 2, Compétences
   - `03-exercices` = intercalaire 3, Exercices
   - `04-aides` = intercalaire 4, Aides
   - `05-evaluations` = intercalaire 5, Évaluations
   - `06-feuilles` = intercalaire 6, Feuilles
3. Cliquer **Add file > Upload files**, glisser les PDF ou images, puis **Commit changes**.
4. Le lien vers le classeur reste **toujours le même**. Il n'y a rien à recopier dans le site.

## Ranger les documents dans le bon ordre

Les fichiers apparaissent par ordre de nom. Employer une numérotation au début :

- `01 - Page de garde.pdf`
- `02 - Fiche méthode.pdf`
- `03 - Fiche de cours.pdf`

Pour intercaler un document : `02a - ...` ou renommer les fichiers. Éviter les données identifiantes d'élèves dans les noms et le contenu.

## Modifier un document ou le retirer

Dans le dossier correspondant, supprimer l'ancien fichier depuis GitHub puis envoyer le nouveau. S'il conserve le même nom, toutes les cases cochées par les élèves pour ce document risquent de rester cochées : ajouter un suffixe au nom si l'ancienne version n'est plus valable.

## Remarques importantes

- Le dépôt et tous les documents publiés avec GitHub Pages sont **publics sur Internet** : ne jamais publier de données personnelles, copies ou photos identifiables d'élèves.
- Vérifier les droits de diffusion des pages de manuels ou autres œuvres protégées. Préférer des fiches personnelles, documents autorisés et ressources sous licence adéquate.
- L'importation par le site GitHub est limitée à **25 Mio par fichier**. Réduire le poids des PDF si nécessaire.
- Le rendu intégré des PDF utilise la bibliothèque libre PDF.js chargée depuis Cloudflare CDN ; si elle est bloquée par un réseau scolaire, les boutons « Ouvrir / imprimer » restent disponibles.
- Le fichier `catalogue.json` est un **modèle Jekyll** et paraît illisible en ouvrant l'archive hors ligne : il est généré automatiquement au moment de la publication via GitHub Pages.
- GitHub Pages doit être configuré pour publier depuis une branche (`main`, racine du dépôt), en laissant Jekyll actif. **Ne pas créer de fichier `.nojekyll`**.

## Tester rapidement sans publier

Ouvrir `index.html` dans un navigateur permet de voir le classeur vide et son esthétique. Le chargement des fichiers n'est opérationnel qu'une fois le site publié avec GitHub Pages.
