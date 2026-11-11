# Discover Bangladesh

**Discover the Soul of Bengal — Travel Guide**

A responsive, English-language travel guide that helps international visitors explore Bangladesh. The existing website source is preserved as the root-level `index.html`; this foundation adds clear project documentation and lightweight repository conventions without redesigning or rewriting the site.

## Current website

The current homepage is a self-contained HTML document with its styles and application JavaScript embedded in the file. It includes:

- Home page and destination discovery
- Destination search and category filtering
- History, culture and food, stories, travel essentials, and About sections
- Trip planner and estimated budget calculations
- Destination detail dialogs and detail-page links
- Responsive navigation, hero slideshow, and animated UI elements
- Print / save-to-PDF support
- Search-engine metadata, Open Graph metadata, and structured data

The source currently contains 19 destination records. The existing visual design, copy, data, and interactions are intentionally retained.

## Repository structure

```text
bangladesh-visits/
├── index.html                 # Original website; keep this as the source of truth
├── 404.html                   # GitHub Pages not-found page
├── favicon.svg                # Standalone brand icon asset
├── manifest.webmanifest       # Basic web-app metadata
├── robots.txt                 # Crawler policy
├── .nojekyll                  # Disable GitHub Pages Jekyll processing
├── .gitignore                 # Ignore local/editor/build artifacts
├── README.md                  # Project overview and maintenance guide
├── CONTRIBUTING.md            # Safe change and review workflow
└── docs/
    └── MAINTENANCE.md         # Detailed operational notes and known follow-ups
```

> The original application is currently a single-file website. Do not split it into multiple CSS/JS files or change its routing architecture unless that work is explicitly planned and regression-tested.

## Run locally

No package manager or build step is required.

1. Clone the repository.
2. Open `index.html` in a modern browser, or serve the folder with any static HTTP server.
3. Test the responsive layout on mobile and desktop.

Example (Python installed):

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Deployment

This is a static website and can be hosted on GitHub Pages or another static hosting provider.

For GitHub Pages:
1. Open **Settings → Pages** in the repository.
2. Under **Build and deployment → Source**, select **GitHub Actions**.
3. Keep the `.github/workflows/pages.yml` workflow on the `main` branch.
4. Push or merge a commit to `main`, or run the workflow manually from **Actions**.
5. Wait for the Pages deployment job to complete and open the published URL shown by GitHub.

If the project is deployed under a custom domain, update the canonical URL, Open Graph URL, sitemap, and domain configuration together. Do not publish a guessed canonical URL.

## External services

The existing page loads Google Fonts and remote Unsplash images. An internet connection is therefore required for those external resources. The website itself does not currently require a JavaScript build tool or server-side runtime.

## Important maintenance rules

- Keep the existing design, content, route names, and behavior unless a change is specifically requested.
- Make focused changes; avoid replacing the whole homepage for a small fix.
- Preserve destination IDs because the router and destination data depend on them.
- Check every local link and asset reference before release.
- Test the mobile menu, search, filters, planner, destination dialogs, print flow, and browser back/forward navigation after JavaScript changes.
- Do not add secrets, API keys, private contact details, or credentials to this public repository.
- Review `docs/MAINTENANCE.md` before editing.

## Current known follow-ups

The original source contains references to additional pages such as `photo-studio.html`, `bangladesh-map.html`, and destination detail HTML files that are not part of the supplied homepage source. Confirm and add those pages only when their original content/assets are available. Some promotional/contact URLs are placeholders in the current source. See the maintenance guide for exact notes.

## Project status

This repository foundation documents and preserves the supplied homepage source. It is not a claim that every external link, referenced secondary page, or live deployment has been verified.
