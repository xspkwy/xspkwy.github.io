# AGENTS.md

This document provides guidelines for agentic coding assistants working on this personal academic website.

## Build/Test Commands

### Local Development
```bash
# Serve the site locally
python3 -m http.server 8000
# or
npx serve .

# Open http://localhost:8000 in browser
```

### Testing
**No automated tests configured.** To add tests:
```bash
npm install --save-dev jest jest-environment-jsdom
npm test                    # Run all tests
npm test -- tests/name.js   # Run specific test file
npm test -- --watch         # Watch mode
npm test -- --coverage      # With coverage
```

### Linting
```bash
npm install --save-dev eslint eslint-config-standard
npx eslint js/             # Run linter
npx eslint js/ --fix       # Auto-fix issues
```

### HTML Validation
```bash
# Online: https://validator.w3.org/#validate_by_upload
npm install -g html-validate
html-validate index.html
```

## Code Style Guidelines

### HTML
- Use semantic HTML5 (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- Start with `<!DOCTYPE html>` and `lang="en"` attribute
- Include `<meta charset="UTF-8">` and viewport meta tag
- Use lowercase tags/attributes, always include `alt` text for images
- Add `aria-label` for accessibility on interactive elements

### CSS
- Use CSS custom properties (variables) in `:root` for light mode, override in `[data-theme="dark"]`
- Naming: `--category-property` (e.g., `--bg-primary`, `--text-secondary`)
- Classes use kebab-case (`.hero-section`, `.btn-primary`), BEM-inspired for complex components
- Avoid tag selectors; prefer class selectors
- Mobile-first with `@media (min-width: 768px)` breakpoints
- Use flexbox/grid for layouts, ensure 44x44px touch targets

### JavaScript
- Use strict mode at top: `'use strict';`
- Use `const` for constants, `let` for variables (avoid `var`)
- Prefer arrow functions, IIFE pattern to avoid global scope
- Check null/undefined before accessing properties
- Use try-catch for operations that may throw

### File Naming
- HTML: `kebab-case.html` (e.g., `publications.html`)
- CSS: `kebab-case.css` (e.g., `styles.css`)
- JS: `kebab-case.js` (e.g., `theme.js`)
- Images: `kebab-case.jpg` or `.png`
- Docs: `kebab-case.pdf`

### Directory Structure
```
personal-website/
├── index.html
├── about.html
├── publications.html
├── projects.html
├── contact.html
├── css/styles.css
├── js/theme.js
└── assets/
    ├── images/
    └── docs/
```

### Imports
- CSS loads in `<head>` before JS
- JS scripts at end of `<body>` before closing tag
- No external frameworks (vanilla JS preferred)

### Accessibility
- All images need `alt` text (empty for decorative)
- Include `aria-label` on buttons without text
- Ensure WCAG AA color contrast (4.5:1 for text)
- Make all interactive elements keyboard accessible
- Use `<label>` with `for` attribute on form inputs

### Assets
- Profile photo: 300x300px or 400x400px, circle crop
- Project images: 800x600px or 4:3 ratio
- Use JPEG for photos, PNG for graphics/transparency
- Optimize images (TinyPNG, ImageOptim)
- Keep PDFs under 5MB

### Content Placeholders
- `[Your Name]` - Full name and title
- `[University/Institution]` - Affiliation
- `[email@domain.com]` - Email
- `[research area]` - Research topics
- `[Date]` - Publication dates

### Content Style
- Write in first person ("I research..." not "We research...")
- Keep descriptions concise (2-3 sentences per item)
- Use active voice, include metrics where possible

### Browser Testing
- Target: Latest Chrome, Firefox, Safari, Edge + mobile browsers
- Test multiple screen sizes, dark/light mode, form validation, all links

### Deployment
**GitHub Pages:** `git push origin main` (auto-deploys from main branch)
**Netlify:** Drag/drop folder or connect GitHub repo
**Before deploying:** Check links, images, form, proofread, test mobile

### Common Tasks

**Add Page:** Create `new-page.html`, add nav link in all HTML files, include CSS/JS
**Add Publication:** Add to year section in `publications.html`, include title/authors/venue/abstract, add PDF to `assets/docs/`, update BibTeX, set `data-type`
**Add Project:** Add card to `projects.html`, upload image to `assets/images/`, update links/tags
**Change Colors:** Edit `--accent` and `--accent-hover` in both `:root` and `[data-theme="dark"]`

## Notes
- Static site, no build process
- No package.json or node_modules
- No CI/CD pipeline (can be added)
- Contact form needs external service (Formspree, etc.)
- Test thoroughly before committing
