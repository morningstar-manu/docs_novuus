# Guide de Déploiement sur GitHub Pages

Ce guide explique comment déployer votre documentation sur GitHub Pages avec support HTML et images.

## Prérequis

- Un compte GitHub
- Un dépôt GitHub (peut être ce dépôt)
- Git installé sur votre machine

## Méthode 1 : Déploiement Automatique avec GitHub Pages (Recommandé)

### Étape 1 : Préparer le dépôt

1. Assurez-vous que tous vos fichiers sont dans le dossier `docs_novuus/`
2. Commitez et poussez vos changements :

```bash
git add .
git commit -m "Ajout de la documentation"
git push origin main
```

### Étape 2 : Activer GitHub Pages

1. Allez sur votre dépôt GitHub
2. Cliquez sur **Settings** (Paramètres)
3. Dans le menu de gauche, cliquez sur **Pages**
4. Sous **Source**, sélectionnez :
   - **Branch**: `main` (ou `master`)
   - **Folder**: `/docs_novuus` (ou `/` si vous avez mis les fichiers à la racine)
5. Cliquez sur **Save**

### Étape 3 : Attendre le déploiement

- GitHub Pages va automatiquement construire votre site avec Jekyll
- Cela peut prendre quelques minutes (jusqu'à 10 minutes)
- Votre site sera disponible à : `https://votre-username.github.io/nom-du-repo/`

## Méthode 2 : Utiliser GitHub Actions (Avancé)

Si vous voulez plus de contrôle, créez un fichier `.github/workflows/pages.yml` :

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-ruby@v1
        with:
          ruby-version: '3.1'
      - name: Install dependencies
        run: |
          cd docs_novuus
          bundle install
      - name: Build site
        run: |
          cd docs_novuus
          bundle exec jekyll build
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./docs_novuus/_site
```

## Utilisation des Images

### Ajouter une image

1. Placez votre image dans `docs_novuus/assets/images/`
2. Dans votre fichier Markdown, utilisez :

```markdown
![Description de l'image]({{ '/assets/images/nom-image.png' | relative_url }})
```

### Exemple

```markdown
![Architecture du système]({{ '/assets/images/architecture.png' | relative_url }})
```

### Formats supportés

- PNG (recommandé pour les schémas)
- JPG/JPEG (pour les photos)
- SVG (pour les diagrammes vectoriels)
- GIF (pour les animations)

### Bonnes pratiques

- Nommez vos fichiers en minuscules avec des tirets : `architecture-systeme.png`
- Optimisez vos images avant de les ajouter (utilisez des outils comme TinyPNG)
- Gardez une taille raisonnable (< 1MB par image)
- Utilisez des descriptions alt text pertinentes

## Structure des Chemins

Sur GitHub Pages, les chemins doivent utiliser le filtre `relative_url` :

- Images : `{{ '/assets/images/image.png' | relative_url }}`
- Liens vers posts : `{{ '/posts/nom-post.html' | relative_url }}`
- CSS : `{{ '/assets/css/style.css' | relative_url }}`

## Test Local (Optionnel)

Pour tester votre site localement avant de le déployer :

### Installation

```bash
# Installer Ruby (si pas déjà installé)
# Windows : https://rubyinstaller.org/
# Mac : brew install ruby
# Linux : sudo apt-get install ruby-full

# Installer les dépendances
cd docs_novuus
bundle install
```

### Lancer le serveur local

```bash
cd docs_novuus
bundle exec jekyll serve
```

Votre site sera accessible sur `http://localhost:4000`

## Personnalisation

### Modifier l'URL de base

Si votre dépôt n'est pas à la racine de votre domaine GitHub Pages, modifiez `_config.yml` :

```yaml
baseurl: "/nom-du-repo"  # Le nom de votre dépôt
url: "https://votre-username.github.io"
```

### Ajouter un favicon

1. Placez votre favicon dans `docs_novuus/assets/images/favicon.ico`
2. Le layout l'utilisera automatiquement

### Personnaliser les couleurs

Modifiez les variables CSS dans `assets/css/style.css` :

```css
:root {
    --primary-color: #2563eb;  /* Changez cette couleur */
    --secondary-color: #1e40af;
    /* ... */
}
```

## Dépannage

### Le site ne se met pas à jour

- Attendez 5-10 minutes après un push
- Vérifiez les actions GitHub dans l'onglet "Actions"
- Vérifiez les erreurs dans Settings > Pages

### Les images ne s'affichent pas

- Vérifiez que le chemin utilise `relative_url`
- Vérifiez que l'image existe dans le bon dossier
- Vérifiez la casse du nom de fichier (sensible sur Linux)

### Erreurs Jekyll

- Vérifiez la syntaxe YAML dans le front matter
- Vérifiez que les layouts existent dans `_layouts/`
- Consultez les logs dans l'onglet "Actions" de GitHub

## Support

Pour plus d'aide :
- [Documentation GitHub Pages](https://docs.github.com/en/pages)
- [Documentation Jekyll](https://jekyllrb.com/docs/)
- [Support GitHub](https://support.github.com/)

