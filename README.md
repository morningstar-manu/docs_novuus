# Documentation des Technologies Médicales Novuus

Ce répertoire contient la documentation complète des technologies médicales développées par Novuus, optimisée pour GitHub Pages avec support HTML et images.

## Structure

```
docs_novuus/
├── README.md                          # Ce fichier
├── DEPLOY.md                          # Guide de déploiement sur GitHub Pages
├── _config.yml                        # Configuration Jekyll/GitHub Pages
├── _layouts/                          # Templates HTML
│   ├── default.html                   # Layout principal
│   └── post.html                      # Layout pour les posts
├── _template-technologie-medicale.md  # Template pour créer de nouvelles pages
├── posts/                             # Pages de documentation individuelles
│   └── exemple-technologie.md        # Exemple de documentation
├── assets/                            # Ressources (images, CSS, etc.)
│   ├── css/
│   │   └── style.css                  # Styles CSS personnalisés
│   └── images/                        # Images et schémas
│       └── README.md                  # Guide d'utilisation des images
├── index.md                           # Page d'accueil de la documentation
├── Gemfile                            # Dépendances Ruby/Jekyll
└── .gitignore                         # Fichiers à ignorer par Git
```

## Déploiement sur GitHub Pages

### Déploiement Rapide

1. **Poussez votre code sur GitHub**
   ```bash
   git add .
   git commit -m "Ajout documentation"
   git push origin main
   ```

2. **Activez GitHub Pages**
   - Allez dans Settings > Pages de votre dépôt
   - Source : Branch `main`, Folder `/docs_novuus`
   - Cliquez sur Save

3. **Votre site sera disponible** à : `https://votre-username.github.io/nom-du-repo/`

📖 **Guide complet** : Voir [DEPLOY.md](DEPLOY.md) pour les instructions détaillées

## Comment Utiliser

### Créer une Nouvelle Documentation

1. Copiez le fichier `_template-technologie-medicale.md` dans le dossier `posts/`
2. Renommez-le avec le nom de votre technologie (format: `YYYY-MM-DD-nom-technologie.md`)
3. Ajoutez le front matter en haut du fichier :
   ```yaml
   ---
   layout: post
   title: "Titre de votre technologie"
   date: YYYY-MM-DD
   categories: [technologies-medicales]
   tags: [tag1, tag2]
   math: true  # Si vous avez des équations mathématiques
   ---
   ```
4. Remplissez toutes les sections du template
5. Ajoutez les images dans `assets/images/` et utilisez :
   ```markdown
   ![Description]({{ '/assets/images/nom-image.png' | relative_url }})
   ```
6. Mettez à jour `index.md` pour ajouter un lien vers votre nouvelle documentation

### Format des Fichiers

- **Nom de fichier** : `YYYY-MM-DD-nom-technologie.md`
- **Format** : Markdown avec front matter YAML
- **Structure** : Suivre le template fourni
- **Layout** : Utiliser `layout: post` dans le front matter

### Utilisation des Images

1. Placez vos images dans `assets/images/`
2. Utilisez le format suivant dans vos fichiers Markdown :
   ```markdown
   ![Description de l'image]({{ '/assets/images/nom-image.png' | relative_url }})
   ```
3. Voir [assets/images/README.md](assets/images/README.md) pour plus de détails

### Standards de Documentation

- Utiliser un langage clair et accessible
- Inclure des schémas et diagrammes pour les concepts complexes
- Citer toutes les références scientifiques
- Inclure des métriques quantifiables lorsque possible
- Respecter les standards médicaux et réglementaires

## Technologies Documentées

[Liste des technologies documentées sera mise à jour ici]

- [Exemple de Technologie Médicale](posts/exemple-technologie.md)

## Contribution

Pour contribuer à la documentation :

1. Suivez le template fourni
2. Assurez-vous que toutes les sections sont complétées
3. Vérifiez l'exactitude médicale et technique
4. Ajoutez des références appropriées
5. Incluez des visuels lorsque nécessaire

## Contact

Pour toute question concernant la documentation, contactez [votre équipe].

