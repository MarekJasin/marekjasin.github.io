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

## Maintenance notes

The horizontal divider under `Research` and `Op-eds` is not an item separator. It is the custom heading pseudo-element in `styles.scss`:

```scss
.content-section h2 {
  border-bottom: 0;
  padding-bottom: 0;
}

.content-section h2::after {
  bottom: -1.75rem;
}
```

To move that line up or down, change only `bottom` on `.content-section h2::after`. Do not add `border-bottom` to `.publication-item` or `.op-ed-item`; that creates unwanted separators between each paper/op-ed. Also do not add `.content-section::after` unless replacing the heading pseudo-element entirely, because that creates a second line.
