# Structure de la Documentation

## 📁 Arborescence Complète

```
docs_novuus/
│
├── 📄 Configuration & Setup
│   ├── _config.yml                    # Configuration Jekyll/GitHub Pages
│   ├── Gemfile                        # Dépendances Ruby
│   ├── .gitignore                     # Fichiers ignorés par Git
│   └── .github/workflows/pages.yml    # Workflow GitHub Actions (optionnel)
│
├── 🎨 Templates & Layouts
│   ├── _layouts/
│   │   ├── default.html               # Layout principal (header, footer)
│   │   └── post.html                  # Layout pour les articles
│   └── _template-technologie-medicale.md  # Template pour nouvelles pages
│
├── 📝 Contenu
│   ├── index.md                       # Page d'accueil
│   └── posts/
│       └── exemple-technologie.md     # Exemple de documentation
│
├── 🎨 Assets
│   └── assets/
│       ├── css/
│       │   └── style.css              # Styles CSS personnalisés
│       └── images/
│           ├── README.md               # Guide d'utilisation des images
│           └── PLACEHOLDER.md          # Instructions pour ajouter des images
│
└── 📚 Documentation
    ├── README.md                      # Guide principal
    ├── QUICKSTART.md                  # Démarrage rapide
    ├── DEPLOY.md                      # Guide de déploiement détaillé
    └── STRUCTURE.md                   # Ce fichier
```

## 🔄 Flux de Travail

### Créer une Nouvelle Documentation

```
1. Copier le template
   └── _template-technologie-medicale.md → posts/YYYY-MM-DD-nom.md

2. Remplir le contenu
   └── Éditer le fichier Markdown

3. Ajouter des images (optionnel)
   └── assets/images/ → Utiliser dans Markdown

4. Commiter et pousser
   └── git add . && git commit && git push

5. GitHub Pages génère automatiquement
   └── Site disponible en 5-10 minutes
```

## 📋 Fichiers Clés

### `_config.yml`
Configuration principale de Jekyll. Définit :
- Titre et description du site
- Collections (posts)
- Support MathJax pour les équations
- Paramètres d'auteur

### `_layouts/default.html`
Template HTML principal avec :
- Header avec navigation
- Footer
- Support MathJax
- Liens CSS

### `_layouts/post.html`
Template pour les articles avec :
- En-tête avec titre et métadonnées
- Contenu principal
- Tags et catégories
- Navigation retour

### `assets/css/style.css`
Styles CSS personnalisés avec :
- Variables CSS pour personnalisation facile
- Styles responsive
- Support print
- Thème moderne et professionnel

## 🖼️ Gestion des Images

### Structure Recommandée
```
assets/images/
├── architecture/      # Schémas d'architecture
├── screenshots/       # Captures d'écran
├── diagrams/          # Diagrammes de flux
└── logos/             # Logos et marques
```

### Utilisation dans Markdown
```markdown
![Description]({{ '/assets/images/nom-image.png' | relative_url }})
```

## 🚀 Déploiement

### Méthode 1 : Automatique (Recommandé)
1. Push sur GitHub
2. Activer Pages dans Settings
3. Attendre 5-10 minutes

### Méthode 2 : GitHub Actions
- Workflow automatique configuré dans `.github/workflows/pages.yml`
- Build et déploiement automatiques à chaque push

## 🎯 Points Importants

1. **Front Matter** : Tous les fichiers Markdown doivent commencer par `---`
2. **Chemins** : Utiliser `{{ '/chemin' | relative_url }}` pour les assets
3. **Layouts** : Spécifier `layout: post` dans le front matter
4. **Images** : Toujours utiliser le filtre `relative_url`
5. **Math** : Activer avec `math: true` dans le front matter

## 📖 Ressources

- [Guide de déploiement](DEPLOY.md)
- [Démarrage rapide](QUICKSTART.md)
- [Guide principal](README.md)
- [Guide des images](assets/images/README.md)

