# Mettre en ligne le classeur virtuel de 6e

## La méthode recommandée : gérer le classeur depuis le navigateur

L'espace enseignant est accessible ici :

**https://jkarmati.github.io/classeur-6eme/gestion.html**

Il permet de :
- Choisir « Fiches » ou l'un des six intercalaires.
- Déposer directement plusieurs PDF ou images par glisser-déposer, sans modifier leur nom.
- Organiser les documents à la souris, avec un glisser-déposer, ou en cliquant sur les flèches ↑ / ↓.
- Enregistrer cet ordre : les élèves le verront après le prochain déploiement.
- Supprimer des documents si nécessaire, avec une confirmation.

**Configuration nécessaire une seule fois (puis à renouveler à l'expiration de l'autorisation) :**
1. Sur ton compte GitHub, ouvre https://github.com/settings/personal-access-tokens/new .
2. Crée un **Fine-grained personal access token** avec un nom reconnaissable, par exemple `Classeur virtuel 6e`, et une date d'expiration.
3. Dans **Resource owner**, sélectionne **jkarmati** ; dans **Repository access**, sélectionne **Only select repositories**, puis **classeur-6eme** uniquement.
4. Dans **Repository permissions**, règle **Contents → Read and write**. Tu n'as pas besoin de donner d'autres droits.
5. Termine la création et copie le jeton. **Ne le partage pas et ne le dépose pas dans le dépôt ou sur Pronote.**
6. Ouvre l'espace enseignant, colle le jeton dans la zone réservée et clique sur **Accéder au classeur**.

**Connexion avec une phrase de passe mémorisable :** lors de la première connexion avec ton jeton, un encadré « Retenir mon accès sur cet appareil » te propose de choisir puis confirmer une phrase de passe personnelle d'au moins 16 caractères (idéalement au moins quatre mots sans lien). La page chiffre alors ton jeton avec AES-GCM et une clé dérivée de ta phrase de passe par PBKDF2-SHA256 (600 000 itérations), puis **enregistre uniquement le jeton chiffré dans ce navigateur**, jamais dans le dépôt public. À la prochaine visite, la phrase de passe suffit à déverrouiller l'accès sur **ce même appareil et dans ce même navigateur**.

- Le jeton en clair n'est conservé en mémoire que pendant la session connectée.
- La phrase de passe n'est pas stockée ; si tu l'oublies, utilise ton jeton GitHub pour te reconnecter (ou recrées-en un si nécessaire).
- Le bouton « Oublier le jeton mémorisé » ou « Effacer l'accès enregistré » efface sa copie chiffrée du navigateur ; cela ne révoque pas le jeton GitHub.
- Si le jeton expire, utilise « Utiliser un autre jeton », efface l'ancien accès chiffré puis enregistre le nouveau.
- Cette facilité n'est adaptée qu'à un ordinateur personnel de confiance, **pas à un ordinateur partagé du collège**. Une phrase trop simple expose à des attaques par essais. Pour un ordinateur partagé, saisis le jeton à chaque connexion et ne l'enregistre pas.

La page de gestion est publiquement consultable, mais seul un jeton valide, autorisé pour le dépôt, peut enregistrer des modifications. Le site restant public, n'y publie aucun document contenant des informations personnelles sur les élèves.

**Synchronisation :** une mise à jour faite depuis la page Web arrive directement sur GitHub. Si tu continues à utiliser GitHub Desktop, fais d'abord **Fetch origin → Pull origin** avant toute nouvelle modification locale.

**Limite d'importation depuis la page :** 20 Mio par fichier. Pour les PDF plus volumineux, utilise encore GitHub Desktop.

## Fonctionnement

- **Pour les élèves et les parents :** un seul lien internet ; aucun compte, aucune installation.
- **Pour le professeur :** déposer des PDF, JPG ou PNG dans les dossiers prévus. Ils seront affichés au prochain déploiement du site (généralement en quelques minutes), dans l’ordre des noms de fichiers.
- Les fiches sont **avant** les six intercalaires, pas dans un septième intercalaire.
- Dans l’intercalaire **Compétences**, chaque PDF reste représenté par une seule feuille virtuelle (aperçu de sa première page), comme auparavant.
- Dans les autres parties, un PDF de **2 pages** montre le **recto et le verso**. Pour un livret de **plus de 2 pages**, le classeur montre uniquement la **première page et la dernière page**, comme les deux faces extérieures du livret agrafé rangé dans une pochette plastique. Les pages intérieures sont accessibles par « Ouvrir / imprimer ».
- Les rectos sont placés à droite et les versos à gauche après feuilletage, comme dans un classeur papier.
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

**Méthode recommandée :** dans l'espace enseignant, choisis l'intercalaire, déplace les documents à la souris ou avec ↑ / ↓, puis clique sur **Enregistrer l'ordre**. Le fichier `ordre.json` est mis à jour automatiquement. Les noms des documents ne changent pas.

**Méthode de secours sans espace enseignant :** si aucun ordre personnalisé n'a été enregistré, les fichiers apparaissent par ordre de nom. Tu peux les numéroter au début :

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
