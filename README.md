# Boîte à reçus

Petite application Android (PWA) pour photographier ses reçus et factures, lire automatiquement l'émetteur, le n° de TVA intracommunautaire, l'objet et la ventilation HT / TVA / TTC (0 %, 5,5 %, 10 %, 20 %), puis exporter le tout en CSV.

- Reçus et photos stockés **dans le téléphone** (aucun serveur).
- Lecture automatique par l'**API Claude** avec ta propre clé (enregistrée dans le téléphone, jamais dans le code).
- Fonctionne hors ligne pour consulter et saisir à la main.
- Sauvegarde / restauration complète (reçus + photos) dans un fichier `.json`.

## Fichiers

| Fichier | Rôle |
|---|---|
| `index.html` | Toute l'application |
| `manifest.webmanifest` | Nom, icônes, mode plein écran |
| `sw.js` | Fonctionnement hors ligne |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | Icônes |

## Mise en ligne (GitHub Pages, depuis le téléphone)

1. Sur github.com : **New repository** → nom `boite-a-recus` → Public → Create.
2. **Add file → Upload files** → sélectionne les 6 fichiers → **Commit changes**.
3. **Settings → Pages** → Source : *Deploy from a branch* → Branch : `main` / `(root)` → Save.
4. Après 1 à 2 minutes, l'app est en ligne à `https://<ton-pseudo>.github.io/boite-a-recus/`.

## Installation sur le téléphone

1. Ouvre l'adresse dans **Chrome**.
2. Menu ⋮ → **Ajouter à l'écran d'accueil** → **Installer**.
3. Lance l'app depuis son icône, ouvre **Réglages** (roue dentée) et colle ta clé API Claude
   (à créer sur https://console.anthropic.com/settings/keys), puis **Tester**.

## Mise à jour

Remplace `index.html` sur GitHub, et change `VERSION` dans `sw.js` (ex. `recus-v2`) pour que le téléphone récupère la nouvelle version au prochain lancement.

## Option : vrai fichier APK

Colle l'adresse de l'app sur https://www.pwabuilder.com → **Package for stores** → Android : tu obtiens un APK installable sans environnement de développement.
