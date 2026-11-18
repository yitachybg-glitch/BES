# Building Engineering Studio (BES) — Core 0.1

Premier socle applicatif du logiciel BES : interface React/TypeScript, visualisation 3D Three.js, aperçu 2D conceptuel, gestion locale des projets et configuration Tauri 2 pour Windows.

## Prérequis

- Node.js 20 ou plus récent
- npm
- Rust stable et les outils de compilation Windows requis par Tauri 2
- WebView2 Runtime (normalement présent sur Windows 10/11)

## Démarrer en mode Web

```bash
npm install
npm run dev
```

Ouvrir http://localhost:1420.

## Préparer la version Windows

Installer les prérequis Tauri 2 pour Windows, puis :

```bash
npm install
npm run tauri dev
```

Créer un installateur :

```bash
npm run tauri build
```

Les installateurs seront générés dans `src-tauri/target/release/bundle/`.

## Fonctionnalités incluses

- Tableau de bord et création de projets.
- Sauvegarde locale du registre des projets dans le navigateur / WebView.
- Espace de travail avec navigation entre modules.
- Scène 3D Three.js orbitable (glisser pour tourner, molette pour zoomer).
- Aperçu de plan 2D conceptuel.
- Structure de départ pour l'application Windows Tauri.

## Limites explicites de cette version

Cette version est un socle de développement. Le plan 2D est un aperçu statique, la scène 3D est une maquette de démonstration, les autres modules sont des espaces réservés. Il n'y a pas encore de noyau CAO paramétrique, de calcul électrique validé, de solveur structurel, de CFD ou de simulation thermique. Ne pas utiliser les vues de démonstration pour prendre des décisions de construction.

## Architecture prévue

- `src/`: application React partagée Web/Windows.
- `src/components/`: composants visuels, dont scène Three.js.
- `src-tauri/`: enveloppe Windows native.
- `engines/` (à ajouter) : moteurs scientifiques isolés.
- `docs/` (à ajouter) : spécifications, validations et décisions d'architecture.

## Prochaine itération recommandée

1. Remplacer l'aperçu 2D par un éditeur géométrique interactif.
2. Introduire le modèle de données bâtiment (projet, niveaux, pièces, murs, ouvertures).
3. Faire générer la scène 3D depuis ce modèle partagé.
4. Créer le format `.besproject` versionné et les tests d'import/export.
5. Ajouter la sélection d'objets et le panneau de propriétés.
