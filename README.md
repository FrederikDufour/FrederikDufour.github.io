# Frédérik Dufour — academic website

This repository uses the Jekyll **Minima** theme and publishes through GitHub Pages.

## Files to edit

- `index.md` — portrait, contact links, and the two About paragraphs
- `research.md` — working papers and published work
- `teaching.md` — teaching-assistant experience
- `cv.pdf` — the CV opened by the header link
- `_config.yml` — site title, description, URL, and theme selection
- `assets/main.scss` — custom layout and appearance layered on top of Minima
- `_includes/header.html` — shared name and navigation bar

## Replace the portrait

Put your photograph in `assets`, preferably as:

```text
assets/photo_web1.jpg
```

In both `index.md` and `research.md`, replace:

```text
assets/profile-placeholder.svg
```

with:

```text
assets/photo_web1.jpg
```

The stylesheet automatically crops it into a circle. A roughly square photograph gives the best result.

## Update contact details

In `index.md`, replace `you@example.com`, the LinkedIn URL, and `Toronto, Canada`.

## Add research papers

Duplicate a complete `<article class="paper"> ... </article>` block in `research.md`. Replace the title, authors, description, and links.

Paper PDFs can be stored in a `papers` folder and linked like this:

```html
<a href="{{ '/papers/my-paper.pdf' | relative_url }}">Paper</a>
```

## Publish on GitHub Pages

Upload or push all these files to the root of the `FrederikDufour.github.io` repository. Preserve the filenames and leading underscores.

In the repository, open **Settings → Pages** and set **Source** to **GitHub Actions**. The included workflow builds and deploys the Minima site after every push to `main`.

Important: do not add a `.nojekyll` file. That file disables Jekyll processing.
