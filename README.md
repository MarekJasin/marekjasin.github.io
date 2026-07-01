# Marek Jasinski homepage

This is a compact [Quarto](https://quarto.org/) website for `marekjasin.ski`.

## Local development

Install Quarto, then run:

```sh
quarto preview
```

To render the static site locally:

```sh
quarto render
```

Quarto writes generated output to `_site/`, which is ignored by git.

## Deployment

`.github/workflows/publish.yaml` renders the Quarto project on GitHub Actions and deploys `_site/` to GitHub Pages. The custom domain is kept in `CNAME`.

## Source structure

- `_quarto.yml` configures the website and GitHub Pages output.
- `index.qmd` is the one-page homepage.
- `styles.scss` and `styles-dark.scss` contain the custom design.
- `assets/` contains the portrait, favicon, and CV PDF linked from the homepage.
