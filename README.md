# Créateur de bande — Trench Crusade

Application web autonome (un seul fichier HTML, sans serveur ni dépendance) pour composer et jouer une bande de **Trench Crusade** (Bandes v4, VF).

## Fonctions

- Recrutement par faction (Nouvelle-Antioche, Pèlerins, Sainte-Affliction, Sultanat, Légions, Raiders navals, Graal noir, Cour du Serpent), calcul du budget et des limites.
- **Mode jeu** : un profil par page (boutons ◀ ▶, flèches du clavier, balayage tactile) avec compteurs de marqueurs **Sang**, **Bénédiction** et **Infection** par figurine.
- **Onglet Mots-clés** : glossaire complet avec recherche ; les mots-clés des fiches et des armes sont cliquables.
- Sauvegarde automatique dans le navigateur, gestion de plusieurs bandes (« Mes bandes »).
- **Export / import JSON** d'une bande ou de plusieurs bandes.
- Thème clair.

## Installation sur Android (PWA)

Ouvrir l'adresse du site dans Chrome, puis menu ⋮ → « Installer l'application » (ou « Ajouter à l'écran d'accueil »). L'application s'ouvre en plein écran et fonctionne hors ligne.
Les bandes sont enregistrées dans le navigateur : penser à les exporter en JSON avant d'effacer les données de Chrome.

Fichiers nécessaires à la PWA, à garder à la racine du dépôt : `index.html`, `manifest.webmanifest`, `service-worker.js` et le dossier `icons/`.
Pour forcer la mise à jour du cache hors ligne, changer le numéro de version `CACHE` dans `service-worker.js`.

## Utilisation

Ouvrir `index.html` dans un navigateur. Avec GitHub Pages (Settings → Pages → branche `main`, dossier `/root`), l'application est accessible en ligne.

## Format JSON d'une bande

```json
{
  "name": "Ma bande",
  "faction": "raidnaval",
  "sin": null,
  "roster": [
    { "uid": 1, "unitId": "rn-capitaine", "name": "Hanun", "equip": ["rn-pistolet"], "powers": [], "opts": [], "blood": 0, "bless": 0, "infect": 0 }
  ]
}
```

L'import accepte aussi un fichier contenant plusieurs bandes (`{ "bands": { "...": { ... } } }`).

## Note

Projet de fan, non officiel. Trench Crusade est une marque de ses propriétaires respectifs.
