# Dossier des Images

Ce dossier contient toutes les images utilisées dans la documentation.

## Structure Recommandée

```
assets/images/
├── README.md (ce fichier)
├── architecture/          # Schémas d'architecture
├── screenshots/           # Captures d'écran
├── diagrams/              # Diagrammes de flux
├── logos/                 # Logos et marques
└── examples/              # Exemples visuels
```

## Comment Utiliser les Images

### Dans un fichier Markdown

```markdown
![Description de l'image]({{ '/assets/images/nom-fichier.png' | relative_url }})
*Légende optionnelle sous l'image*
```

### Exemples

```markdown
<!-- Image simple -->
![Architecture du système]({{ '/assets/images/architecture-systeme.png' | relative_url }})

<!-- Image avec légende -->
![Interface utilisateur]({{ '/assets/images/interface.png' | relative_url }})
*Figure 1 : Interface principale du système*

<!-- Image centrée (via CSS) -->
<div style="text-align: center;">
![Schéma]({{ '/assets/images/schema.png' | relative_url }})
</div>
```

## Formats Supportés

- **PNG** : Recommandé pour les schémas, diagrammes, captures d'écran
- **JPG/JPEG** : Pour les photos et images avec beaucoup de couleurs
- **SVG** : Pour les diagrammes vectoriels (scalables)
- **GIF** : Pour les animations simples

## Bonnes Pratiques

1. **Nommage** : Utilisez des noms descriptifs en minuscules avec des tirets
   - ✅ `architecture-systeme.png`
   - ❌ `Architecture Système.PNG`

2. **Optimisation** : Compressez vos images avant de les ajouter
   - Utilisez des outils comme [TinyPNG](https://tinypng.com/) ou [Squoosh](https://squoosh.app/)
   - Taille recommandée : < 500KB par image

3. **Résolution** : 
   - Pour les schémas : 1200-1920px de largeur
   - Pour les captures d'écran : Résolution native ou 2x pour Retina

4. **Accessibilité** : Toujours inclure un texte alternatif descriptif

5. **Organisation** : Organisez les images par catégorie dans des sous-dossiers

## Exemple de Structure Complète

```
assets/images/
├── architecture/
│   ├── systeme-complet.png
│   └── composants.png
├── screenshots/
│   ├── interface-principale.png
│   └── rapport-generique.png
├── diagrams/
│   ├── flux-donnees.png
│   └── processus-analyse.png
└── logos/
    └── novuus-logo.png
```

## Outils Recommandés

- **Création de diagrammes** : [Draw.io](https://app.diagrams.net/), [Excalidraw](https://excalidraw.com/)
- **Édition d'images** : [GIMP](https://www.gimp.org/), [Photopea](https://www.photopea.com/)
- **Compression** : [TinyPNG](https://tinypng.com/), [Squoosh](https://squoosh.app/)
- **Conversion** : [CloudConvert](https://cloudconvert.com/)

