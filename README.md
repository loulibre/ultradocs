# UltraDocs Theme for Hugo Docs by UltraRepo

UltraDocs is a Hugo theme designed for documentation websites. It automatically ingests your repository content and generates a documentation website that is viewable offline by AI or by humans. UltraDocs also provides an enhanced knowledge graph-based content map in JSON schema, XLSX, and Markdown formats.

UltraDocs is built on the [Hugo](https://gohugo.io/) static site generator.

## Documentation

For detailed information, visit the [UltraDocs documentation website](https://github.com/loulibre/ultradocs/) which is built using this theme.

## Steps to Use UltraDocs as Your Hugo Docs Template in New Projects

### 1. Install Hugo

Ensure you have Hugo installed. If not, install it with:

```sh
brew install hugo  # macOS
choco install hugo # Windows
sudo apt install hugo # Linux
```

### 2. Clone the UltraDocs Repository

```sh
git clone https://github.com/loulibre/ultradocs.git
cd ultradocs
```

### 3. Initialize Git and Connect to Your Own Repository

```sh
git init
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git branch -M main
git add .
git commit -m "Initial commit"
git push -u origin main
```

### 4. Start the Hugo Server Locally

```sh
hugo server -D
```

Then open your browser at:  
[http://localhost:1313](http://localhost:1313)

### 5. Use UltraDocs in a New Hugo Project

To use UltraDocs in a new project:

```sh
hugo new site mydocs
cd mydocs
git init
git submodule add https://github.com/loulibre/ultradocs.git themes/ultradocs
```

Modify `config.toml` in your new project:

```toml
theme = "ultradocs"
```

### 6. Configure the UltraDocs Theme

Modify `config.toml` to include UltraDocs features:

```toml
baseURL = "http://localhost:1313/"
languageCode = "en-us"
title = "My Documentation Site"
theme = "ultradocs"
```

### 7. Regenerate Documentation with UltraDocs

Whenever you add content, generate the documentation:

```sh
hugo
```

This will create the static files in the `public/` directory.

### 8. Deploy UltraDocs to GitHub Pages (Optional)

```sh
git add .
git commit -m "Deploy UltraDocs site"
git push origin main
hugo -D -d docs  # Output files to /docs
```

Then configure GitHub Pages to serve from the `docs/` folder.

### 9. Enable Sitemap, TOC, and Tags

Modify `config.toml` to enable sitemap and TOC:

```toml
[outputs]
  home = ["HTML", "RSS", "JSON"]

[markup]
  [markup.tableOfContents]
    endLevel = 3
    startLevel = 1

[taxonomies]
  tag = "tags"
  category = "categories"
```

### 10. Verify and Test

Use the following to check the setup:

```sh
hugo server -D --disableFastRender
```

## License

UltraDocs is released under the MIT License. See [LICENSE](LICENSE) for details.

For any issues or contributions, submit an issue or pull request on [GitHub](https://github.com/loulibre/ultradocs).
