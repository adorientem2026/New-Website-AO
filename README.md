# Ad Orientem Foundation Static Website

This folder contains a complete one-page bilingual static website for the Ad Orientem Foundation.

## Files

- `index.html` — complete semantic HTML structure.
- `styles.css` — complete responsive styling.
- `script.js` — English/French language toggle and bilingual text store.
- `assets/images/logo.png` — optimized logo used by the website.
- `assets/images/books/*.webp` — optimized book cover images used by the website.

## How to view locally

Open `index.html` in any modern browser. No server, database, build system, or framework is required.

For the most reliable local preview, you can also run a simple static server from this folder:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

## Where to place image assets

Logo:

```text
assets/images/logo.png
```

Book covers:

```text
assets/images/books/sprouts-1.webp
assets/images/books/sprouts-2.webp
assets/images/books/sprouts-3.webp
assets/images/books/sprouts-4.webp
assets/images/books/sprouts-5.webp
assets/images/books/page-pals-1.webp
assets/images/books/page-pals-2.webp
assets/images/books/page-pals-3.webp
assets/images/books/page-pals-4.webp
assets/images/books/page-pals-5.webp
assets/images/books/trailblazers-1.webp
assets/images/books/trailblazers-2.webp
assets/images/books/trailblazers-3.webp
assets/images/books/trailblazers-4.webp
assets/images/books/trailblazers-5.webp
```

If you replace a cover, keep the same file name and dimensions/proportions where possible. The current layout expects portrait book-cover images.

## How to update book titles

Open `script.js` and edit the `books` object inside each language:

```js
translations.en.books
translations.fr.books
```

The keys must remain the same, for example `sprouts1`, `page4`, or `trail5`. Only change the displayed title text.

## How to update bilingual website text

Open `script.js` and edit the English or French values inside:

```js
translations.en
translations.fr
```

The HTML uses `data-i18n` attributes to connect page elements to the translation keys. For example:

```html
<h2 data-i18n="missionTitle">Our Mission</h2>
```

This means the visible text comes from `translations.en.missionTitle` or `translations.fr.missionTitle`.

## How to update navigation labels

In `script.js`, edit these keys:

```js
navAbout
navMission
navSeries
navContact
```

## How to update contact information

The email address appears in `index.html` inside the Contact section:

```html
<a href="mailto:ad.orientem1@gmail.com">ad.orientem1@gmail.com</a>
```

The location text is controlled in `script.js` by the `location` key.

## Accessibility and performance notes

- The site uses semantic sections, headings, accessible alt text, a skip link, visible keyboard focus states, and a language switcher with `aria-pressed`.
- Book images are optimized as WebP files and lazy-loaded outside the hero section.
- The site uses no external fonts, frameworks, or tracking scripts.
- The color palette is based on the magenta/plum identity of the provided logo, with warm paper, gold, green, and blue accents for the three series.

## Deployment

Upload the full folder contents to any static host, such as Netlify, GitHub Pages, Cloudflare Pages, Vercel, or a standard web hosting account. Make sure this structure is preserved:

```text
index.html
styles.css
script.js
assets/
  images/
    logo.png
    books/
      ...cover files...
```
