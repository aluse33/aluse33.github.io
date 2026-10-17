# aluse33.github.io

Personal academic website of **Alejandro Lucas Serrano**, PhD candidate in Industrial Economics at the University of Valencia.

Live at **https://aluse33.github.io** · built with [Quarto](https://quarto.org) and served by GitHub Pages from `docs/`.

## Structure

```
_quarto.yml                    site configuration: navbar, footer, theme
styles.scss                    custom styles
equations.html                 snippet included after every page body
index.qmd                      home page (about, trestles template)
research.qmd                   working papers
projects.qmd                   automatic listing of projects/
projects/<name>/index.qmd      one folder per project or notebook
teaching.qmd, media.qmd        teaching and talks
cv/CV.tex                      CV source (compiled to files/CV.pdf)
files/                         photo, CV, favicon (copied as is)
docs/                          rendered site (what GitHub Pages serves)
```

## Workflow

```bash
quarto preview      # local preview with live reload
quarto render       # rebuild docs/
git add -A && git commit -m "..." && git push
```

- **CV:** edit `cv/CV.tex`, compile it and save the PDF as `files/CV.pdf`, then run `quarto render`.
- **New project:** copy `projects/piaac-primeros-pasos/`, change title, date and categories; it appears automatically under *Projects*.
- **Code:** `execute: freeze: auto` keeps results of executed chunks, so the site can be rebuilt without the data.
- **Data:** microdata (`data/`, `*.dta`, `*.sav`) and `_private/` are excluded by `.gitignore`.
