# Contributing

Thank you for helping improve Discover Bangladesh.

## Before making a change

1. Read the project overview in `README.md`.
2. Read `docs/MAINTENANCE.md`.
3. Identify the exact user-facing behavior that needs to change.
4. Preserve the existing layout, colors, content, route identifiers, and interactions unless the task explicitly asks otherwise.

## Safe workflow

1. Create a focused branch from `main`.
2. Make the smallest practical change.
3. Do not reformat or rewrite the entire `index.html` for an unrelated fix.
4. Keep external dependencies minimal; this project currently has no build tool.
5. Review the diff and confirm no unrelated content was removed.
6. Test at mobile and desktop widths.
7. Open a pull request with a concise summary and a manual test checklist.

## Manual regression checklist

- [ ] Homepage loads without a console error.
- [ ] Main navigation and mobile menu work.
- [ ] Search and destination filters work.
- [ ] Destination cards and detail dialogs open correctly.
- [ ] Planner calculations and print flow work.
- [ ] Browser back and forward navigation work.
- [ ] No horizontal overflow at narrow screen widths.
- [ ] Images have sensible fallbacks and do not break the layout.
- [ ] All changed links point to valid destinations.

## Content and accessibility

- Keep visitor-facing copy clear and factual.
- Use descriptive link text and meaningful alternative text.
- Preserve keyboard access and visible focus indicators.
- Do not invent opening hours, prices, transport details, or safety advice.
- Do not commit secrets, private data, or credentials.
