# Birthday Card - Interactive Image Popup

## Project Overview

An interactive popup that cycles through a sequence of images when the user clicks a button, ending with a final message. Designed as a customizable greeting card template.

## Tech Stack

- **Frontend**: Vanilla HTML5, CSS3, JavaScript (ES6)
- **Fonts**: Google Fonts (Pixelify Sans)
- **Deployment**: Static hosting (Netlify recommended)
- **No build tools required** - open `index.html` directly in browser

## Project Structure

```
bday-card/
├── index.html          # Main HTML structure
├── index.js            # Image cycling logic and event handling
├── style.css           # Styling with CSS custom properties
├── assets/
│   ├── image-content/  # Sequential images (image-1.png through image-6.png)
│   ├── main-bg.png     # Page background
│   ├── favicon.png     # Browser tab icon
│   ├── close-icon.png  # Decorative window control
│   └── shrink-icon.png # Decorative window control
└── README.md           # User-facing documentation
```

## Key Files

| File | Purpose | Key Lines |
|------|---------|-----------|
| `index.js` | Image array & click handler | `index.js:6-13` (image paths), `index.js:61-75` (click logic) |
| `style.css` | Theme variables | `style.css:1-33` (all customizable variables) |
| `index.html` | Customizable text content | `index.html:8` (title), `index.html:25` (header), `index.html:39` (button), `index.html:42` (final message) |

## Development

**Run locally:**
```bash
# No build step - just open in browser
open index.html
```

**Deploy:**
Drag and drop project folder to Netlify dashboard, or connect via Git.

## Customization Quick Reference

### Colors & Theming
Edit CSS variables in `style.css:2-33`

### Image Sequence
1. Replace files in `assets/image-content/`
2. Update array in `index.js:6-13` if adding/removing images

### Text Content
Edit in `index.html`:
- Title: line 8
- Header: line 25
- Button text: line 39
- Final message: line 42

## Image Requirements

| Asset | Recommended Size | Notes |
|-------|------------------|-------|
| Animation sequence | 300 x 360px | Transparent PNG recommended |
| Background | 2093 x 1132px | - |
| Favicon | 238 x 279px | Transparent PNG |
| Icons | Square aspect ratio | 287 x 287px used |

---

## Additional Documentation

When working on this project, consult these files for deeper context:

- `.claude/docs/architectural_patterns.md` - Design patterns, state management, and CSS architecture conventions used throughout the codebase
