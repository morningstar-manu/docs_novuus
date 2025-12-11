# Guide de Démarrage Rapide

## 🚀 Déploiement en 3 Étapes

### 1. Préparer votre dépôt GitHub

```bash
# Si vous n'avez pas encore créé le dépôt
git init
git add .
git commit -m "Documentation technologies médicales"
git branch -M main
git remote add origin https://github.com/VOTRE-USERNAME/NOM-DU-REPO.git
git push -u origin main
```

### 2. Activer GitHub Pages

1. Allez sur votre dépôt GitHub
2. **Settings** → **Pages**
3. **Source** : `main` branch, `/docs_novuus` folder
4. Cliquez **Save**

### 3. Attendre (5-10 minutes)

Votre site sera disponible à : `https://VOTRE-USERNAME.github.io/NOM-DU-REPO/`

## 📝 Créer une Nouvelle Page

1. **Copiez le template** :
   ```bash
   cp _template-technologie-medicale.md posts/2024-01-20-ma-technologie.md
   ```

2. **Éditez le fichier** et remplissez les sections

3. **Ajoutez des images** :
   - Placez-les dans `assets/images/`
   - Utilisez : `![Description]({{ '/assets/images/image.png' | relative_url }})`

4. **Commitez et poussez** :
   ```bash
   git add .
   git commit -m "Ajout documentation ma-technologie"
   git push
   ```

## 🖼️ Ajouter une Image

1. **Ajoutez l'image** dans `assets/images/`
2. **Dans votre Markdown** :
   ```markdown
   ![Description de l'image]({{ '/assets/images/nom-image.png' | relative_url }})
   ```

## 🧪 Tester Localement (Optionnel)

```bash
# Installer Ruby et Bundler (une seule fois)
# Windows : https://rubyinstaller.org/
# Mac : brew install ruby
# Linux : sudo apt-get install ruby-full

# Installer les dépendances
cd docs_novuus
bundle install

# Lancer le serveur
bundle exec jekyll serve

# Ouvrir http://localhost:4000 dans votre navigateur
```

## 📚 Documentation Complète

- **Guide de déploiement** : [DEPLOY.md](DEPLOY.md)
- **Guide d'utilisation** : [README.md](README.md)
- **Guide des images** : [assets/images/README.md](assets/images/README.md)

## ❓ Problèmes Courants

### Les images ne s'affichent pas
- Vérifiez que le chemin utilise `{{ '/assets/images/...' | relative_url }}`
- Vérifiez la casse du nom de fichier

### Le site ne se met pas à jour
- Attendez 5-10 minutes après un push
- Vérifiez l'onglet "Actions" sur GitHub

### Erreur de build
- Vérifiez la syntaxe YAML dans le front matter
- Vérifiez que tous les fichiers commencent par `---`

## 🎨 Personnalisation

### Modifier les couleurs
Éditez `assets/css/style.css` et modifiez les variables CSS :

```css
:root {
    --primary-color: #2563eb;  /* Changez cette couleur */
}
```

### Modifier l'en-tête
Éditez `_layouts/default.html`

### Ajouter un favicon
Placez `favicon.ico` dans `assets/images/`

---

**Besoin d'aide ?** Consultez [DEPLOY.md](DEPLOY.md) pour plus de détails.

