# AI Coding Agent Instructions - Hero Dev Portfolio

## Project Overview
This is a personal portfolio website for Mayisha Amin (styled as "Mary Hardy"). It's a static HTML/CSS frontend showcasing a hero section with navigation, banner content, and responsive design.

**Key Files:**
- [index.html](../index.html) - Main landing page structure
- [styles/portfolio.css](../styles/portfolio.css) - All styling; centralized design system
- [images/](../images/) - Assets (developer.png, header_bg.png, hardy.png, icons/)

## Architecture & Design Patterns

### Color System
- **Primary accent:** `#FD6E0A` (orange) - Used in logo "r" and buttons
- **Background light:** `#FFF8F3` (off-white header background)
- **Text colors:** `#181818` (dark headers), `#474747` (nav), `#757575` (body text)

Keep these consistent when modifying styles or adding new components.

### CSS Organization
- Single stylesheet approach (`portfolio.css` contains all styles)
- Reset using universal selector (`*{margin:0; padding:0; box-sizing:border-box;}`)
- Component-based classes (`.btn`, `.logo`, `.banner-*`)
- Font imported from Google Fonts: Open Sans (variable weight 300-800)

### Layout Structure
- Navigation fixed at 71% width, max-width 1140px, centered with margin auto
- Banner section uses flexbox with responsive positioning (content left, image right)
- Background images use `background-position: top left, bottom right` for layering (developer.png top-left, header_bg.png bottom-right)

## Development Conventions

### Button Styling
When adding new buttons, use the `.btn` class pattern:
```css
/* Orange background, white text, 18px padding, rounded corners */
background-color: #FD6E0A;
border: none;
padding: 18px 35px;
border-radius: 5px;
cursor: pointer;
```

### Naming Conventions
- CSS classes: kebab-case (`.banner-content`, `.banner-image`)
- IDs: kebab-case for major sections (`#banner`, `#header`)
- Note: There's an inconsistent typo in the logo ("orenge" → "orange") - keep as-is to avoid breaking references

### Build & Testing
- **Build task:** `g++ -g ${file} -o ${fileDirname}/${fileBasenameNoExtension}.exe` (configured but currently unused for a web project)
- **No automated tests** - static site; manual browser testing recommended for layout changes
- **No build step needed** - HTML/CSS served directly; serve with local web server for development

## Common Tasks

### Adding New Components
1. Add HTML structure to [index.html](../index.html)
2. Add `.component-name` styles to [portfolio.css](../styles/portfolio.css) before body/section styles
3. Follow existing flexbox patterns; ensure responsive behavior with max-width constraints

### Modifying Styles
- Always maintain the color system values
- Test background image layering on header changes (multiple background-image URLs)
- Font sizing follows pattern: headings 45-85px, body 18-20px, nav 20px

### Adding Images
- Place in [images/](../images/) folder
- Update references in CSS (use `../images/filename.png` relative paths)
- Optimize PNG files before committing (current project uses .png assets)

## Integration Points
- Google Fonts API: Open Sans imported via `<link>` tag - ensure preconnect headers remain for performance
- No external JavaScript frameworks or APIs currently used
- Static content only - suitable for hosting on GitHub Pages

## Gotchas & Known Issues
- CSS has syntax error: `font size: 45px;` should be `font-size: 45px;` (space instead of hyphen in logo h2 rule)
- Inconsistent spelling in class name: `.color-orenge` (misspelled "orange") - referenced in HTML
- Commented-out body background rule - preserve comment or clean up
