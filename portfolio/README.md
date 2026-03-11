# Keertana Vajjhala — Portfolio Website

Built with [Quarto](https://quarto.org). Clean, minimal design.

## Setup

### 1. Install Quarto
Download from https://quarto.org/docs/get-started/

### 2. Add your resume PDF
Place your resume at:
```
assets/Keertana_Resume.pdf
```
Create the `assets/` folder if it doesn't exist.

### 3. Preview locally
```bash
quarto preview
```
Opens at http://localhost:4321

### 4. Build for production
```bash
quarto render
```
Output goes to `_site/` folder.

## Deploy Options

### GitHub Pages (recommended)
1. Push this repo to GitHub
2. In your repo settings → Pages → Source: GitHub Actions
3. Create `.github/workflows/publish.yml`:

```yaml
on:
  push:
    branches: [main]
jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: quarto-dev/quarto-actions/setup@v2
      - uses: quarto-dev/quarto-actions/publish@v2
        with:
          target: gh-pages
```

### Netlify
1. Connect your GitHub repo to Netlify
2. Set build command: `quarto render`
3. Set publish directory: `_site`

### Quarto Pub (simplest)
```bash
quarto publish quarto-pub
```

## Customization

- **Content**: Edit the `.qmd` files
- **Colors / fonts**: Edit `styles.css`
- **Nav items**: Edit `_quarto.yml`
- **Add a photo**: Place `assets/photo.jpg` and add to `index.qmd`:
  ```markdown
  ![](assets/photo.jpg){width=160 style="border-radius:50%"}
  ```

## File Structure

```
portfolio/
├── _quarto.yml       # Site config & navbar
├── styles.css        # All custom styling
├── index.qmd         # About / home page
├── experience.qmd    # Work & education
├── projects.qmd      # Project cards
├── publications.qmd  # Publications
├── contact.qmd       # Contact links
└── assets/
    └── Keertana_Resume.pdf   ← add this!
```
