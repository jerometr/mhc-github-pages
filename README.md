# Site Web Mon Health Coach

Ce site est hébergé sur GitHub Pages.

La documentation pour GitHub Pages est disponible [ici](https://docs.github.com/en/pages/quickstart).

## Comment développer localement

Le plus simple, en développant sur Windows, est d'utiliser WSL (Windows Subsystem for Linux).

### Pré-requis

- Avoir [Ruby](https://www.ruby-lang.org/fr/documentation/installation/) installé :

```bash
sudo apt update && sudo apt install -y ruby ruby-bundler
```

- Avoir [Bundler](https://bundler.io/) installé :

```bash
sudo gem install bundler
```

- Avoir les dépendances installées (bundler s'en charge lorsqu'il est exécuté) :

```bash
bundle
```

### Servir le site localement

Pour voir le rendu du site dans un navigateur, exécuter la commande suivante :

```bash
bundle exec jekyll serve --watch --incremental --livereload
```

> Note : Seules les modifications des fichiers source (`*.md` ou `.html`) déclenchent une recompilation.
> Pour forcer une recompilation, il suffit donc de sauvegarder (même sans modifications) un fichier source.
>
> Attention ! Les modifications du fichier `_config.yml` nécessitent de relancer la commande ci-dessus (`bundle exec ...`).

### Modifier le site

Le site utilise [Jekyll](https://jekyllrb.com/) et le thème [minimal-mistakes](https://github.com/mmistakes/minimal-mistakes).

La documentation du thème est disponible [ici](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/).

Des styles personnalisés sont définis dans [main.scss](./assets/css/main.scss).

Le menu de navigation est défini dans [navigation.yml](./_data/navigation.yml).

Les fichiers dans [_includes](./_includes/) et [_layouts](./_layouts/) sont des copies du code source du thème (dans `./vendor/bundle/ruby/3.2.0/gems/minimal-mistakes-jekyll-<version>/`).

Le fichier [default.html](./_layouts/default.html) a été copié car il était nécessaire pour que le fichier [footer.html](./_includes/footer.html) soit inclus dans le build.

Le code principal du site est situé dans [index.markdown](./index.markdown).

### Mettre à jour le site publié

Pour mettre à jour le site publié après l'avoir modifié localement, il faut enregistrer les modifications et les pousser sur GitHub :

```bash
git add --all
git commit -m "<message>"
git push
```

> Note : Il est possible d'effectuer cela en utilisant, par exemple, [GitHub Desktop](https://github.com/apps/desktop).
> Il est possible de le télécharger en utilisant winget : `winget install github-desktop`.