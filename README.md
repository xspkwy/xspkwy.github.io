# Pengwei Xie's Personal Website

A simple, clean personal website inspired by Jon Barron's minimalist design.

## Features

- **Minimalist Design**: Clean typography and layout inspired by academic websites
- **Dark/Light Mode**: Toggle between themes with localStorage persistence
- **Responsive**: Works on mobile and desktop
- **Fast**: No external dependencies, pure HTML/CSS/JavaScript

## Project Structure

```
personal-website/
├── index.html          # Main page (the only page)
├── css/
│   └── styles.css      # Minimalist styling with dark/light mode
├── js/
│   └── theme.js        # Theme toggle functionality
├── assets/
│   ├── images/         # Project images (optional)
│   └── docs/           # PDF files (optional)
├── materials/           # CV and source materials
└── README.md
```

## Getting Started

### Local Development
```bash
# Serve the site locally
python3 -m http.server 8000
# or
npx serve .

# Open http://localhost:8000 in browser
```

### Customization

#### Personal Information
Edit `index.html` to update:
- Name and bio
- Contact links (Email, Scholar, Github)
- Research interests
- Publications and projects

#### Publications
Add papers in the `<section>` area:
```html
<article>
    <h3>Paper Title</h3>
    <p><strong>Your Name</strong>, Co-author 1, Co-author 2</p>
    <p><strong>Conference/Journal</strong>, Year</p>
    <p>Brief abstract...</p>
    <p>
        <a href="https://github.com/...">code</a> / 
        <a href="...">project page</a> / 
        <a href="...">arXiv</a>
    </p>
</article>
```

#### Colors
Edit CSS variables in `css/styles.css`:
```css
:root {
    --accent: #0066cc;        /* Link color */
    --bg: #ffffff;            /* Background */
    --text: #000000;          /* Text color */
}
```

## Deployment

### GitHub Pages
```bash
git add .
git commit -m "Update website"
git push origin main
# Site auto-deploys from main branch
```

### Netlify
- Drag and drop the folder to Netlify
- Or connect GitHub repository

## Design Inspiration

Design and source code inspired by [Jon Barron's website](https://jonbarron.info).

## Browser Support
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
