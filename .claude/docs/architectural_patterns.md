# Architectural Patterns

## CSS Architecture

### Design Tokens via Custom Properties
All theming is centralized in `:root` using CSS custom properties (`style.css:1-33`). This pattern enables:
- Single source of truth for colors, fonts, spacing
- Easy theme customization without touching component styles
- Consistent values across all components

**Categories defined:**
- Colors: `--color-*`
- Images: `--image-path-*`
- Typography: `--font-*`
- Spacing: `--padding-*`, `--gap-*`
- Borders: `--border-*`

### Layout Pattern: Flexbox Containers
All layout uses Flexbox with consistent patterns:
- Outer containers use `flex-direction: column` with `justify-content: space-between`
- See: `style.css:57-70` (container), `style.css:73-85` (inner-container)

### Responsive Design
Mobile-first adjustments via media query at `768px` breakpoint (`style.css:172-185`):
- Background sizing changes from `100% auto` to `cover`
- Container adds margin
- Font sizes scale down

## JavaScript Patterns

### Module-Level State
State is managed via module-scoped variables rather than classes or external state management:
- `currentIndex` tracks position in image sequence (`index.js:27`)
- Simple and appropriate for single-component interactions

### DOM Selection Pattern
Elements are cached at module load time for performance:
```
const imageContent = document.querySelector('.image-content');
const mainButton = document.getElementById('main-button');
const finalMessage = document.querySelector('.final-message');
```
Reference: `index.js:19-21`

### Image Preloading Pattern
Images are preloaded before display to ensure smooth transitions (`index.js:37-48`):
1. Fade out current image (opacity transition)
2. Create new `Image()` object
3. Set `src` to trigger browser fetch
4. On `load` event, update background and fade in

### Event-Driven Updates
Single event listener handles all state transitions (`index.js:61-75`):
- Increment index
- Call update function if not at end
- Handle end-state (hide button, show message) when reaching final image

## HTML Structure Pattern

### Container Nesting
Three-level nesting provides styling flexibility:
1. `body` - page background
2. `.container` - main popup window with header
3. `.inner-container` - content area with image and controls

### Semantic Organization
- `<header>` for title and decorative icons
- Content div (`.inner-container`) for interactive elements
- Separation of decorative (icons) vs functional (button) elements

## Transition Patterns

### CSS Transitions for Animation
All animations use CSS transitions rather than JavaScript animation:
- Image fade: `transition: opacity 0.5s ease` (`style.css:129`)
- Button hover: `transition: transform 0.2s ease` (`style.css:152`)
- Icon hover: `transition: opacity 0.2s ease-in-out` (`style.css:115`)

### State-Based Visibility
Element visibility controlled via `display` property toggle:
- Button hidden: `style.display = 'none'` (`index.js:72`)
- Message shown: `style.display = 'block'` (`index.js:73`)
- Initial state set in CSS: `display: none` (`style.css:160`)
