# henderson-maxwell.github.io

Placeholder landing page for the **Henderson Maxwell** GitHub org. Plain HTML/CSS, no build step.

## Structure

```
index.html         # org landing page (root)
css/style.css       # shared styles (supports light/dark via prefers-color-scheme)
masamu/index.html   # Masamu product page, served at /masamu/
.nojekyll           # tells GitHub Pages not to run Jekyll on this repo
```

Each product gets its own subfolder with an `index.html` (e.g. `masamu/`), so it's served at
`henderson-maxwell.github.io/<product>/`. They all share `css/style.css` for a consistent look.

## Adding another product

1. Create a new folder at the repo root, e.g. `myproduct/`, with its own `index.html` (copy
   `masamu/index.html` as a starting point — it links back to `css/style.css` via `../css/style.css`).
2. In [index.html](index.html), duplicate the `<article class="product-card">...</article>` block
   inside `.product-grid` (in the `#products` section), update the name, description, and status
   badge, and point its link at `myproduct/`.

## GitHub Pages setup

This repo publishes **from the root of the `main` branch** (not `/docs`).

To enable it:

1. Push this repo to `github.com/henderson-maxwell/henderson-maxwell.github.io`.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, select `main` and folder `/ (root)`, then **Save**.
5. The site will be published at `https://henderson-maxwell.github.io/`.

## Updating the Masamu link

The Masamu product card currently links to its GitHub repo
(`https://github.com/henderson-maxwell/masamu`) as a placeholder. Once it's deployed,
update the `href` on the "View on GitHub" link in [index.html](index.html) to point to the live app.
