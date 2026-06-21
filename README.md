# we Depanne — Construire l'APK Android (build cloud)

Ce dossier est prêt pour fabriquer un fichier **.apk** installable sur Android,
sans rien installer de lourd sur ton PC. Le build se fait gratuitement sur GitHub.

## Contenu du dossier
- `main.py` — le code de l'application (version APK : images dans `assets/`)
- `assets/` — toutes les images (des images temporaires "placeholder" sont fournies)
- `pyproject.toml` — configuration de l'app
- `requirements.txt` — la version de Flet à utiliser
- `.github/workflows/build-apk.yml` — la recette qui construit l'APK

## Étape 0 — Mettre TES vraies images
Dans le dossier `assets/`, remplace chaque image temporaire par la tienne,
en gardant EXACTEMENT le même nom de fichier :
- logo.png, banniere.png, demarrage.png, profil.png, plus.png, localisation.png
- google.png, apple.png
- cat_depannage.png, cat_mecanique.png, cat_electricite.png, cat_plomberie.png,
  cat_peinture.png, cat_coiffure.png, cat_vulcanisation.png, cat_menuiserie.png,
  cat_vitrerie.png, cat_chauffeur.png, cat_nettoyage.png, cat_livraison.png,
  cat_frigoriste.png
- nav_accueil.png, nav_services.png, nav_messages.png, nav_profil.png

## Étape 1 — Indiquer ta version de Flet
Sur ton PC, lance :  `pip show flet`
Note la version (ex : 0.28.3) puis écris-la dans `requirements.txt` :
`flet==0.28.3`

## Étape 2 — Créer un compte GitHub
Va sur https://github.com et crée un compte gratuit.

## Étape 3 — Créer un dépôt (repository)
- Clique sur "+" en haut à droite → "New repository"
- Nom : `wedepanne`
- Coche "Public" (ou Private)
- Clique "Create repository"

## Étape 4 — Envoyer ce dossier sur GitHub
Le plus simple sans outil : sur la page du dépôt, clique
"uploading an existing file", puis glisse-dépose TOUT le contenu de ce dossier
(y compris le dossier caché `.github`). Valide avec "Commit changes".

## Étape 5 — Lancer le build
- Onglet "Actions" du dépôt
- Choisis "Build APK we Depanne" → "Run workflow"
- Attends ~15-25 min

## Étape 6 — Télécharger l'APK
- Quand le build est fini (coche verte), ouvre-le
- En bas, section "Artifacts" → télécharge `wedepanne-apk`
- Décompresse le .zip → tu obtiens `app-release.apk`
- Envoie-le sur ton téléphone, ouvre-le, autorise "sources inconnues", installe.

## En cas d'erreur
Ouvre le build rouge dans "Actions", clique l'étape en échec,
copie le message d'erreur et envoie-le moi : je corrige.
