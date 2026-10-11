# Ryosei Tamura - personal website

A one-page academic site: a large name with a one-line subtitle, the bio beside a rounded
portrait, a row of icon links, then News and a numbered Publications list. Nothing else.

No build step. It is plain HTML + CSS, so it works on GitHub Pages as-is.
Colors follow the visitor's system setting: light by default, dark when their device is in dark mode.

## Files

| Path | What it is |
| --- | --- |
| `index.html` | The whole site. Edit this. |
| `stylesheet.css` | Colors, fonts, layout. You rarely need to touch it. |
| `images/profile.jpg` | Headshot shown on the page: an 800x1000 crop of the original photo. |
| `images/ryosei_tamura01.jpg` | Original photo. Clicking the headshot opens it. |
| `images/*-poster.jpg` | Posters, linked as images so every browser shows them instead of downloading a PDF. |
| `view.html` | PDF viewer page (Mozilla PDF.js). Links like `view.html?doc=cv` show a PDF from `data/` as pages instead of downloading it. To add a PDF, put it in `data/` and add a line to the `DOCS` list in `view.html`. |
| `data/` | PDFs shown through `view.html`: the RISS 2026 paper and your CV (`cv.pdf`). |
| `.nojekyll` | Tells GitHub Pages to serve the files verbatim. |

## Preview locally

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>. If a change to `stylesheet.css` does not show up, hard-refresh the page (Cmd+Shift+R); browsers cache it.

## Customize (checklist)

1. **Name and subtitle**: the first name is bold and the last name is light. The subtitle line under it holds your position and lab.
2. **Bio**: one or two short paragraphs next to the photo. Link people, labs, and programs, and bold your main research topics.
3. **Links**: set the real URLs for Email (`mailto:`), CV (`data/cv.pdf`), Scholar, GitHub, X, LinkedIn in the icon row. Delete any you don't use.
   Icons come from Font Awesome (`fa-brands fa-github`) and Academicons (`ai ai-google-scholar`); browse
   <https://fontawesome.com/search?o=r&m=free> and <https://jpswalsh.github.io/academicons/> for others.
4. **Photo**: `images/profile.jpg` is shown as a 4:5 portrait with rounded corners. To use a new photo, crop it to a
   head-and-shoulders 4:5 shot (about 800x1000 pixels), save it over `images/profile.jpg`, and update the link to the original.
5. **News**: one `<li>` per item, newest first, starting with a bold date.
6. **Publications**: one `<li>` per paper, newest first (see below).

### Adding a paper

```html
<li>
  <strong>Paper Title</strong><br>
  First Author, <strong>Ryosei Tamura</strong>, Another Author, Advisor Name. CoRL 2026.<br>
  <a href="https://arxiv.org/abs/...">paper</a> / <a href="https://my-paper.github.io">website</a> / <a href="https://github.com/...">code</a>
</li>
```

### Adding a news item

```html
<li><strong>Oct. 2026:</strong> One sentence, with <a href="https://...">a link</a> if useful.</li>
```

## Publishing

The site is live at <https://ryohector.github.io>, served by GitHub Pages from the `main` branch of
<https://github.com/ryohector/ryohector.github.io>. To publish a change, commit it and push:

```bash
git add -A && git commit -m "Update website" && git push
```

GitHub rebuilds the site within a minute or two. Push over HTTPS (the `origin` remote): this Mac's SSH key belongs to a
different GitHub account.

## Credits and licenses

- Font: [Lato](https://fonts.google.com/specimen/Lato), SIL Open Font License, loaded from Google Fonts.
- Icons: [Font Awesome Free 6.7.2](https://fontawesome.com/license/free) (CC BY 4.0 icons, SIL OFL font, MIT code) and
  [Academicons 1.9.6](https://jpswalsh.github.io/academicons/) (SIL OFL / MIT), both loaded from cdnjs.
