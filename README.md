# henderson-maxwell.github.io

Landing page for the **Henderson Maxwell** GitHub org. Plain HTML/CSS, no build step.

## Structure

```
index.html                    # org landing page (root)
css/style.css                 # shared design system (light/dark via prefers-color-scheme)
henderson-maxwell-logo.svg/.png   # Henderson Maxwell logo (original, white background)
henderson-maxwell-mark.svg        # same mark with the background stripped, used in the page UI
kusolva/index.html            # Kusolva product page, served at /kusolva/
kusolva/kusolva.css           # Kusolva's brand-color overrides, loaded after css/style.css
kusolva/kusolva-logo.svg/.png # Kusolva logo (original, white background)
kusolva/kusolva-mark.svg      # same mark with the background stripped, used in the page UI
.nojekyll                     # tells GitHub Pages not to run Jekyll on this repo
```

Each product gets its own subfolder with an `index.html` (e.g. `kusolva/`), so it's served at
`henderson-maxwell.github.io/<product>/`. Every page loads the shared `css/style.css` for layout,
typography, and components; a product can add its own small stylesheet after it (like
`kusolva/kusolva.css`) to override the brand color tokens (`--accent`, `--ink`, `--glow`, `--brand-2`)
with its own logo colors, without duplicating any layout CSS.

## Adding another product

1. Create a new folder at the repo root, e.g. `myproduct/`, with its own `index.html` (copy
   `kusolva/index.html` as a starting point — update the `../css/style.css` link and either drop or
   rewrite the `kusolva.css` link for the new product's own colors).
2. In [index.html](index.html), duplicate the `<article class="product-card">...</article>` block
   inside `.product-grid` (in the `#products` section, next to the "More products coming soon"
   placeholder card), update the name, description, and status badge, and point its link at
   `myproduct/`.

## Brand colors

- **Henderson Maxwell** — navy `#06285c`, teal `#00d2ca` (from `henderson-maxwell-logo.svg`).
- **Kusolva** — navy `#000b41`, blue `#003ca9`, green `#006d37`, gold `#e4ac00` (from
  `kusolva/kusolva-logo.svg`).

## GitHub Pages setup

This repo publishes **from the root of the `master` branch** (not `/docs`).

To enable it:

1. Push this repo to `github.com/henderson-maxwell/henderson-maxwell.github.io`.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, select `master` and folder `/ (root)`, then **Save**.
5. The site will be published at `https://henderson-maxwell.github.io/`.

## Updating the Kusolva link

The Kusolva hero and product card currently link to its GitHub repo
(`https://github.com/henderson-maxwell/kusolva`) as a placeholder for both "Get started" and
"View on GitHub". Once Kusolva is deployed, update the "Get started" link in
[kusolva/index.html](kusolva/index.html) to point at the live app, and update the "Get in touch"
link in the same file once a real contact channel (email/form) exists.
