# Maintenance Guide

This document records the current implementation as supplied. It is intended to make future changes predictable and low-risk.

## 1. Source of truth

- `index.html` is the complete supplied homepage source.
- It contains the page markup, styles, destination data, routing, rendering logic, and event handlers.
- There is no package manifest, transpilation step, or JavaScript bundler in the current project.
- Keep the source intact when working on documentation or repository configuration.

## 2. Application areas

The current client-side navigation includes these route areas:

- Home: `/`
- Destinations: `/destinations`
- History: `/history`
- Culture and food: `/culture`
- Stories: `/stories`
- Travel essentials: `/essentials`
- Map: `/map`
- Trip planner: `/planner`
- About: `/about`
- Destination details: `/d/:id`

The app uses hash-based navigation. Preserve route spelling and destination IDs; links and destination records rely on them.

## 3. Destination data

The source currently contains 19 destination entries and a corresponding full-details lookup. When adding or editing a destination:

1. Use a stable, URL-safe ID.
2. Keep the display name and destination description consistent across cards and detail views.
3. Verify the image source and fallback behavior.
4. Check the category/filter values.
5. Confirm the full-details destination exists before publishing the link.

Do not remove existing destination records as part of unrelated maintenance.

## 4. External assets and dependencies

- Destination photography is loaded from remote Unsplash image URLs.
- Typography is loaded from Google Fonts.
- There are no local JavaScript or CSS dependencies in the supplied homepage.

Remote image/font failures should not prevent the rest of the page from rendering. Preserve existing fallback handling when editing image code.

## 5. Configuration currently embedded in the source

The homepage contains a `SITE` object for About Me, Clients, and Admin Login links. These currently point to the NEXTIT-BD website as placeholders.

The `CONTACT_EMAIL` constant is currently empty. The optional email contact form is therefore not enabled.

Before changing these values:
- Confirm the final destination URL or contact address with the project owner.
- Do not guess private contact details.
- Keep external links safe (for example, preserve `rel="noopener"` for links opened in a new tab).

## 6. Known source references to verify

The source includes navigation references to:
- `photo-studio.html`
- `bangladesh-map.html`

It also references several separate destination detail pages. The supplied repository baseline did not include those pages, so their availability cannot be assumed. Check whether the original files exist before creating replacements. Avoid replacing missing pages with fabricated content.

Two destination detail path strings in the supplied lookup appear malformed:
- `sylhet-srimangal`: `fufull-details-sylhet-srimangaltml`
- `mahasthangarh`: `fufull-details-mahasthangarhtml`

Confirm the intended filenames before correcting them. This foundation commit deliberately does not guess the intended paths.

## 7. SEO and deployment

The homepage already contains title, description, robots, Open Graph, Twitter, and structured-data metadata. It sets canonical and Open Graph URL values at runtime based on the current page URL.

No sitemap or custom-domain declaration has been added because the final production URL has not been confirmed. When the deployment URL is known:

1. Confirm whether the site is hosted at a repository subpath or a custom domain.
2. Verify canonical URLs on the homepage and hash routes.
3. Add a sitemap only for real, crawlable URLs.
4. Add the verified sitemap URL to `robots.txt`.
5. Test the GitHub Pages 404 behavior and internal links.

## 8. Release checklist

- [ ] Review the complete diff.
- [ ] Confirm no existing destination or copy has been unintentionally changed.
- [ ] Run the site locally.
- [ ] Test the mobile menu and narrow viewport layout.
- [ ] Test search, filters, route changes, destination details, planner, and print.
- [ ] Check browser console for runtime errors.
- [ ] Check every local page link and external link.
- [ ] Confirm deployment URL and SEO canonical values.
- [ ] Verify the published site after deployment.

## 9. Architecture evolution

A future extraction of the single-file application into separate HTML, CSS, JavaScript, and data modules may improve maintainability, but it is a separate refactor. It should be done only after a behavior inventory and with screenshot/manual regression checks. Do not combine such a refactor with small content or bug-fix tasks.
