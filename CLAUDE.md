# CLAUDE.md - AI Assistant Guide

## Project Overview

**fluffy-chainsaw** is a simple, clean portfolio website template written in French. It's designed as a starting point for showcasing personal projects, skills, and contact information. The site uses pure HTML5 and CSS3 without any frameworks or build tools, making it lightweight and easy to customize.

**Primary Language**: French (content and UI text)
**Last Updated**: January 2026
**Version**: 2.0

### Project Goals

- 🎯 **Simplicity First**: No build tools, no dependencies, just HTML & CSS
- 🇫🇷 **French Native**: All content in French for French-speaking audiences
- 📱 **Responsive**: Works seamlessly on mobile, tablet, and desktop
- ♿ **Accessible**: Follows WCAG 2.1 AA standards
- ⚡ **Performance**: Loads fast with minimal overhead
- 🎨 **Clean Design**: Professional aesthetic with modern card-based layout

---

## Codebase Structure

```
fluffy-chainsaw/
├── index.html          # Main HTML structure and content
├── style.css           # All styling and visual design
└── CLAUDE.md           # This file - AI assistant guidelines
```

### File Descriptions

- **index.html** (~47 lines): Main HTML document
  - Purpose: Complete page structure and content
  - Sections: Header, About, Projects, Footer
  - Encoding: UTF-8
  - Language: French (`lang="fr"`)
  - Key features: Semantic HTML5, mobile viewport, clean structure

- **style.css** (~67 lines): Visual styling
  - Purpose: All presentation and layout
  - Approach: Mobile-first, element selectors with minimal classes
  - Components: Header, sections, project cards, footer
  - Design tokens: Colors, spacing, typography
  - No media queries yet (inherently responsive with flexible units)

- **CLAUDE.md** (this file): Documentation for AI assistants
  - Purpose: Codebase context and guidelines
  - Audience: AI assistants (Claude, GPT, etc.)
  - Maintenance: Update when architecture or conventions change

### Visual Layout

```
┌────────────────────────────────┐
│         HEADER                 │
│     [Votre Nom]                │
│  Développeur | Designer        │
└────────────────────────────────┘
┌────────────────────────────────┐
│     SECTION: À propos          │
│  ┌──────────────────────────┐  │
│  │  Bio text content here   │  │
│  └──────────────────────────┘  │
└────────────────────────────────┘
┌────────────────────────────────┐
│     SECTION: Mes Projets       │
│  ┌──────────────────────────┐  │
│  │  Projet 1                │  │
│  │  Description...          │  │
│  └──────────────────────────┘  │
│  ┌──────────────────────────┐  │
│  │  Projet 2                │  │
│  └──────────────────────────┘  │
│  ┌──────────────────────────┐  │
│  │  Projet 3                │  │
│  └──────────────────────────┘  │
└────────────────────────────────┘
┌────────────────────────────────┐
│         FOOTER                 │
│   Contactez-moi: email@...     │
└────────────────────────────────┘
```

---

## Technology Stack

| Category | Technology | Notes |
|----------|-----------|-------|
| **Markup** | HTML5 | Semantic elements, French lang attribute |
| **Styling** | CSS3 | No preprocessors, vanilla CSS |
| **JavaScript** | None | Currently no interactivity |
| **Build Tools** | None | Direct file serving |
| **Dependencies** | None | Zero external dependencies |

---

## Development Workflow

### Git Branching Strategy

This repository follows a Claude AI-assisted development workflow:

1. **Claude Branches**: All AI-assisted development happens on branches following the pattern:
   - Format: `claude/claude-md-{session-id}-{unique-id}`
   - Example: `claude/claude-md-mirw4kvs9laqp86a-013VNYVY21c1istSC9eusZ31`
   - These branches are created automatically and should be used for all changes

2. **Commit Guidelines**:
   - Write clear, descriptive commit messages in English
   - Focus on the "why" rather than the "what"
   - Example: "Add responsive navigation for mobile devices" vs "Update CSS"

3. **Push Protocol**:
   - Always use: `git push -u origin <branch-name>`
   - Only push to branches starting with `claude/`
   - Retry on network failures with exponential backoff (2s, 4s, 8s, 16s)

### Deployment

This is a static website that can be deployed to any web server or static hosting service:
- No build step required
- Simply serve the files from the root directory
- Compatible with: GitHub Pages, Netlify, Vercel, Apache, Nginx, etc.

---

## Key Conventions & Design Patterns

### 1. Language and Localization

- **Primary Language**: French
- All user-facing text is in French (UI labels, content, comments)
- When adding content, maintain French language consistency
- Placeholder text uses brackets: `[Votre Nom]`, `votre.email@example.com`

### 2. HTML Structure

- **Semantic HTML**: Uses proper semantic elements (`<header>`, `<main>`, `<section>`, `<footer>`)
- **Accessibility**: Include proper meta tags, lang attributes, and semantic structure
- **Mobile-First**: Viewport meta tag included for responsive behavior

### 3. CSS Architecture

- **No Classes for Layout**: Main structural elements use element selectors
- **Component Classes**: `.projet` for reusable project cards
- **Color Scheme**:
  - Primary: `#333` (dark gray for headers/footer)
  - Background: `#f4f4f4` (light gray)
  - Content: `#fff` (white cards)
  - Text: `#333` (dark gray)
- **Typography**: System font stack for native look and performance
- **Spacing**: Consistent use of rem units for scalability
- **Cards**: Box shadow and border-radius for modern card design

### 4. Design System

**Font Stack**:
```css
-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif
```

**Key Values**:
- Max content width: `800px`
- Border radius: `8px`
- Box shadow: `0 2px 4px rgba(0,0,0,0.1)`
- Line height: `1.6`

**Design Tokens Reference**:
```css
/* Colors */
--color-primary: #333;
--color-background: #f4f4f4;
--color-surface: #fff;
--color-text: #333;
--color-text-inverse: #fff;

/* Spacing (conceptual - not using CSS variables yet) */
--spacing-xs: 0.5rem;   /* 8px */
--spacing-sm: 1rem;      /* 16px */
--spacing-md: 1.5rem;    /* 24px */
--spacing-lg: 2rem;      /* 32px */

/* Typography */
--font-size-base: 16px;
--line-height-base: 1.6;

/* Layout */
--content-max-width: 800px;
--border-radius: 8px;

/* Shadows */
--shadow-sm: 0 2px 4px rgba(0,0,0,0.1);
```

**Note**: The above CSS variables are *not* currently implemented in the codebase, but represent the design tokens in use. Consider implementing them if theming or easier maintenance is requested.

---

## Guidelines for AI Assistants

### When Making Changes

#### DO:
- ✅ **Maintain French language** for all user-facing content
- ✅ **Preserve semantic HTML structure** when modifying markup
- ✅ **Keep the design system consistent** (colors, spacing, typography)
- ✅ **Use vanilla CSS** - no preprocessors or CSS-in-JS
- ✅ **Test responsive behavior** when adding new elements
- ✅ **Read files before editing** - always understand context first
- ✅ **Keep it simple** - avoid over-engineering solutions
- ✅ **Maintain accessibility** - proper alt text, semantic markup, keyboard navigation

#### DON'T:
- ❌ **Don't add build tools** unless explicitly requested (no npm, webpack, etc.)
- ❌ **Don't add JavaScript frameworks** unless there's a clear need
- ❌ **Don't change the language** to English without explicit permission
- ❌ **Don't add unnecessary dependencies** - keep it lightweight
- ❌ **Don't create config files** unless needed (no package.json, .gitignore, etc.)
- ❌ **Don't over-comment** - the code should be self-explanatory
- ❌ **Don't add features** not explicitly requested

### Common Tasks

#### Adding a New Section

1. Read `index.html` to understand structure
2. Add new `<section>` inside `<main>` following existing pattern
3. Update `style.css` if custom styling needed (reuse existing styles when possible)
4. Maintain French language in all text content
5. Test that it fits the existing design system

#### Updating Styling

1. Read `style.css` to understand current design tokens
2. Prefer modifying existing rules over adding new ones
3. Maintain consistency with color scheme and spacing
4. Use rem units for spacing, px for borders/shadows
5. Keep mobile responsiveness in mind

#### Adding Interactivity

1. Assess if vanilla JavaScript is sufficient
2. If adding JS, create `script.js` and link it in `index.html` before `</body>`
3. Use modern ES6+ syntax
4. Keep JavaScript minimal and progressive enhancement in mind
5. Ensure functionality degrades gracefully without JS

### Testing Checklist

Before committing changes:

- [ ] Visual inspection in browser (if possible)
- [ ] HTML validates (semantic structure maintained)
- [ ] CSS follows existing conventions
- [ ] French language maintained in all user-facing text
- [ ] No console errors or warnings
- [ ] Responsive design considerations addressed
- [ ] Accessibility not degraded

### Security Considerations

This is a simple static website with minimal security concerns:
- No user input handling (no XSS risk currently)
- No external API calls
- No sensitive data storage

**If adding features:**
- Validate all user inputs if forms are added
- Use HTTPS for any external resources
- Sanitize any dynamic content
- Follow OWASP guidelines for web security

---

## Extending the Project

### Potential Enhancements

If the user requests new features, consider these patterns:

1. **Navigation Menu**: Add `<nav>` in header with anchor links to sections
2. **Image Gallery**: Add images to projects with lazy loading
3. **Contact Form**: Consider using a service like Formspree or Netlify Forms
4. **Dark Mode**: Add CSS custom properties and a theme toggle
5. **Animations**: Use CSS transitions/animations (avoid heavy JS libraries)
6. **Multi-page**: Create additional HTML files for blog, detailed project pages

### When to Suggest Modern Tools

Only suggest adding tools when:
- User explicitly requests them
- The project complexity genuinely requires them
- Simple vanilla solutions are insufficient

Examples:
- **Tailwind CSS**: Only if user wants utility-first approach
- **React/Vue**: Only if building complex interactive features
- **Build Tools**: Only if using TypeScript, SASS, or bundling is needed

---

## Performance Optimization

### Current Performance Profile

- **Load Time**: ~50-100ms (2 HTTP requests + minimal CSS)
- **Size**: HTML (~1.5KB) + CSS (~1KB) = **~2.5KB total** (uncompressed)
- **Gzipped**: ~1KB total
- **Render Blocking**: CSS only (minimal impact)
- **JavaScript**: None (0 bytes)

### Best Practices

#### Images (when added)

```html
<!-- Use modern formats with fallbacks -->
<picture>
  <source srcset="projet1.webp" type="image/webp">
  <source srcset="projet1.jpg" type="image/jpeg">
  <img src="projet1.jpg" alt="Description du projet 1" loading="lazy" width="400" height="300">
</picture>
```

**Guidelines**:
- Always include `width` and `height` attributes to prevent layout shift
- Use `loading="lazy"` for images below the fold
- Compress images (aim for <100KB per image)
- Use WebP format with JPEG/PNG fallback
- Provide descriptive `alt` text in French

#### CSS Optimization

- ✅ Already optimized: No unused CSS
- ✅ Minimal selectors (low specificity)
- ✅ No CSS animations (yet)
- ⚠️ Consider minification for production (optional)

#### Font Loading

Current approach uses system fonts (already optimal):
- Zero font download overhead
- No FOUT (Flash of Unstyled Text)
- Native look and feel per platform

**If adding custom fonts**:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preload" as="style" href="https://fonts.googleapis.com/css2?family=Inter&display=swap">
```

#### HTTP/2 and Caching

**Recommended `.htaccess` (for Apache)**:
```apache
# Cache CSS and HTML
<IfModule mod_expires.c>
  ExpiresActive On
  ExpiresByType text/html "access plus 1 hour"
  ExpiresByType text/css "access plus 1 year"
  ExpiresByType image/jpeg "access plus 1 year"
  ExpiresByType image/png "access plus 1 year"
  ExpiresByType image/webp "access plus 1 year"
</IfModule>

# Enable Gzip compression
<IfModule mod_deflate.c>
  AddOutputFilterByType DEFLATE text/html text/css text/javascript
</IfModule>
```

---

## Accessibility (a11y) Guidelines

### Current Accessibility Features

- ✅ Semantic HTML (`<header>`, `<main>`, `<section>`, `<footer>`)
- ✅ Language attribute (`lang="fr"`)
- ✅ Proper heading hierarchy (h1 → h2 → h3)
- ✅ Sufficient color contrast (dark text on light background)
- ✅ Responsive viewport meta tag
- ✅ Focus styles (browser defaults)
- ⚠️ No skip links (consider adding)
- ⚠️ No ARIA labels (may be needed for dynamic content)

### WCAG 2.1 AA Compliance Checklist

#### Perceivable

- [ ] **1.1.1 Non-text Content**: Add descriptive `alt` attributes to images when added
- [x] **1.3.1 Info and Relationships**: Semantic HTML used correctly
- [x] **1.4.3 Contrast**: Text has sufficient contrast (21:1 for dark on light)
- [ ] **1.4.10 Reflow**: Test at 400% zoom (should work with current rem-based design)

#### Operable

- [x] **2.1.1 Keyboard**: All links keyboard accessible (no custom JS navigation)
- [ ] **2.4.1 Bypass Blocks**: Add skip link to main content
- [x] **2.4.6 Headings and Labels**: Clear heading hierarchy
- [ ] **2.4.7 Focus Visible**: Consider enhancing focus styles

#### Understandable

- [x] **3.1.1 Language of Page**: `lang="fr"` present
- [x] **3.2.3 Consistent Navigation**: Simple, consistent layout

#### Robust

- [x] **4.1.1 Parsing**: Valid HTML5
- [x] **4.1.2 Name, Role, Value**: Standard HTML elements

### Recommended Improvements

#### 1. Add Skip Link

```html
<!-- Add after <body> opening tag -->
<a href="#main-content" class="skip-link">Aller au contenu principal</a>

<header>...</header>
<main id="main-content">...</main>
```

```css
/* Add to style.css */
.skip-link {
    position: absolute;
    top: -40px;
    left: 0;
    background: #333;
    color: #fff;
    padding: 8px;
    text-decoration: none;
    z-index: 100;
}

.skip-link:focus {
    top: 0;
}
```

#### 2. Enhance Focus Styles

```css
/* Add visible focus indicators */
a:focus,
button:focus {
    outline: 3px solid #0066cc;
    outline-offset: 2px;
}
```

#### 3. ARIA Labels for Projects

```html
<section id="projets" aria-labelledby="projets-heading">
    <h2 id="projets-heading">Mes Projets</h2>
    <div class="projet" role="article" aria-labelledby="projet1-title">
        <h3 id="projet1-title">Projet 1</h3>
        <p>Description...</p>
    </div>
</section>
```

### Screen Reader Testing

Test with:
- **NVDA** (Windows, free)
- **JAWS** (Windows, commercial)
- **VoiceOver** (macOS/iOS, built-in)
- **TalkBack** (Android, built-in)

---

## SEO Best Practices

### Current SEO Status

- ✅ Valid HTML5
- ✅ Descriptive `<title>` tag
- ⚠️ Missing meta description
- ⚠️ No Open Graph tags
- ⚠️ No structured data
- ⚠️ Generic title ("Mon Portfolio")

### Essential Meta Tags

Add to `<head>` in index.html:

```html
<!-- Essential SEO -->
<meta name="description" content="Portfolio de [Votre Nom] - Développeur Web et Designer. Découvrez mes projets et compétences.">
<meta name="keywords" content="développeur web, designer, portfolio, [votre ville], [technologies]">
<meta name="author" content="[Votre Nom]">

<!-- Open Graph (for social sharing) -->
<meta property="og:title" content="[Votre Nom] - Portfolio">
<meta property="og:description" content="Développeur Web et Designer passionné. Découvrez mes projets.">
<meta property="og:image" content="https://votre-domaine.com/images/og-image.jpg">
<meta property="og:url" content="https://votre-domaine.com">
<meta property="og:type" content="website">
<meta property="og:locale" content="fr_FR">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="[Votre Nom] - Portfolio">
<meta name="twitter:description" content="Développeur Web et Designer">
<meta name="twitter:image" content="https://votre-domaine.com/images/twitter-card.jpg">

<!-- Canonical URL -->
<link rel="canonical" href="https://votre-domaine.com/">

<!-- Favicon -->
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
```

### Structured Data (JSON-LD)

Add before `</head>`:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "[Votre Nom]",
  "jobTitle": "Développeur Web",
  "url": "https://votre-domaine.com",
  "sameAs": [
    "https://github.com/votre-username",
    "https://linkedin.com/in/votre-profile"
  ],
  "knowsAbout": ["Développement Web", "Design", "HTML", "CSS", "JavaScript"]
}
</script>
```

### Content Optimization

- Use **descriptive headings** with relevant keywords
- Write **unique, valuable content** (not just "Lorem ipsum")
- Include **internal links** if adding multiple pages
- Use **semantic HTML** (already done ✓)
- Keep **page titles under 60 characters**
- Keep **meta descriptions under 155 characters**

### robots.txt

Create `/robots.txt`:
```
User-agent: *
Allow: /
Sitemap: https://votre-domaine.com/sitemap.xml
```

### sitemap.xml

Create `/sitemap.xml`:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://votre-domaine.com/</loc>
    <lastmod>2026-01-16</lastmod>
    <priority>1.0</priority>
  </url>
</urlset>
```

---

## Responsive Design Patterns

### Current Approach

The site is **inherently responsive** without media queries:
- ✅ `max-width: 800px` on main content prevents over-wide text
- ✅ `padding: 1rem 2rem` provides breathing room
- ✅ Flexible `rem` units scale with user preferences
- ✅ No fixed widths on content elements

### When to Add Media Queries

Consider adding breakpoints when:
- Navigation becomes horizontal on desktop
- Multi-column layouts are needed
- Typography needs size adjustments
- Images require different layouts

### Recommended Breakpoints

```css
/* Mobile First - Base styles above, then enhance */

/* Small tablets and large phones (landscape) */
@media (min-width: 600px) {
    main {
        padding: 1.5rem 3rem;
    }
}

/* Tablets and small desktops */
@media (min-width: 768px) {
    header h1 {
        font-size: 2.5rem;
    }

    /* Two-column project grid */
    .projets-grid {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 1rem;
    }
}

/* Desktops and large screens */
@media (min-width: 1024px) {
    main {
        padding: 2rem 4rem;
    }

    /* Three-column project grid */
    .projets-grid {
        grid-template-columns: repeat(3, 1fr);
    }
}

/* Extra large screens */
@media (min-width: 1440px) {
    /* Optional: increase max-width */
    main {
        max-width: 1200px;
    }
}
```

### Testing Viewports

Test on these common sizes:
- **Mobile**: 375×667 (iPhone SE), 390×844 (iPhone 12/13)
- **Tablet**: 768×1024 (iPad), 820×1180 (iPad Air)
- **Desktop**: 1366×768, 1920×1080
- **Large**: 2560×1440

### Touch-Friendly Design

- Maintain **minimum tap target size of 44×44px**
- Links in footer already have adequate size
- Consider increasing padding if adding button elements

---

## Browser Compatibility

### Supported Browsers

Current code works in:
- ✅ Chrome/Edge 90+ (2021+)
- ✅ Firefox 88+ (2021+)
- ✅ Safari 14+ (2020+)
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

### CSS Features Used

All features have excellent support:
- `flexbox` - 99%+ support
- `rem` units - 99%+ support
- `box-shadow` - 99%+ support
- `border-radius` - 99%+ support
- System font stack - Universal support

### Potential Issues

**If adding advanced features**, check compatibility:

❌ **CSS Grid** - Use with caution (IE11 has limited support)
```css
/* Safe approach with fallback */
.projet-grid > * {
    width: 100%; /* Fallback */
}

@supports (display: grid) {
    .projet-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    }
}
```

❌ **CSS Variables** - Not supported in IE11
```css
/* Provide fallback values */
color: #333; /* Fallback */
color: var(--color-primary, #333); /* Progressive enhancement */
```

❌ **ES6+ JavaScript** - Transpile or use carefully
```javascript
// Avoid arrow functions if supporting IE11
// Use: function() {} instead of () => {}
```

### Testing Strategy

1. **Modern browsers**: Chrome, Firefox, Safari (primary targets)
2. **Mobile**: iOS Safari, Chrome Mobile (high priority)
3. **Edge cases**: Samsung Internet, Opera (if time permits)
4. **Tools**: BrowserStack, LambdaTest, or manual device testing

---

## Troubleshooting Guide

### Common Issues

#### Issue: Styles not appearing

**Symptoms**: Page displays unstyled HTML
**Causes**:
1. CSS file path incorrect
2. CSS file not in same directory as HTML
3. Server not serving CSS with correct MIME type

**Solutions**:
```bash
# Check file exists
ls -la style.css

# Verify HTML link (should be relative path)
grep "stylesheet" index.html
# Should show: <link rel="stylesheet" href="style.css">

# Check browser console for 404 errors
# Open DevTools > Console
```

#### Issue: Layout breaks on mobile

**Symptoms**: Text overflows, horizontal scrolling appears
**Causes**:
1. Missing viewport meta tag
2. Fixed widths in CSS
3. Large images without max-width

**Solutions**:
```html
<!-- Ensure viewport tag is present -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

```css
/* Ensure images are responsive */
img {
    max-width: 100%;
    height: auto;
}
```

#### Issue: French characters display incorrectly (é, à, ç, etc.)

**Symptoms**: Accented characters show as � or garbled text
**Cause**: Missing or incorrect charset declaration

**Solution**:
```html
<!-- Must be first element in <head> -->
<meta charset="UTF-8">
```

Save files as UTF-8 in your editor (not ANSI or ISO-8859-1).

#### Issue: Git push fails with 403

**Symptoms**: `git push` returns 403 Forbidden
**Cause**: Pushing to wrong branch (not `claude/` prefixed)

**Solution**:
```bash
# Check current branch
git branch

# Ensure it starts with 'claude/'
# If not, create correct branch
git checkout -b claude/claude-md-{session-id}-{unique-id}

# Push with correct branch name
git push -u origin claude/claude-md-{session-id}-{unique-id}
```

#### Issue: Sections overlap

**Symptoms**: Content from one section appears over another
**Cause**: CSS positioning or float issues

**Solution**:
- Check for `position: absolute` without proper containment
- Verify no unclosed HTML tags
- Inspect with browser DevTools

#### Issue: Footer not at bottom

**Symptoms**: Footer appears mid-page with white space below
**Current status**: Footer uses `position: relative` (not sticky)

**If this is a problem**:
```css
/* Option 1: Sticky footer with flexbox */
body {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

main {
    flex: 1;
}

footer {
    position: relative; /* Keep existing style */
}
```

### Debugging Commands

```bash
# Validate HTML (requires validator)
npx html-validate index.html

# Check file encoding
file -I index.html
# Should show: charset=utf-8

# View file in browser (if local server running)
python3 -m http.server 8000
# Then visit: http://localhost:8000

# Check git status
git status
git log --oneline -5

# View CSS specificity issues (in browser console)
document.querySelectorAll('*').forEach(el => {
    console.log(el.tagName, window.getComputedStyle(el).color);
});
```

---

## Frequently Asked Questions (FAQ)

### General Questions

**Q: Why no JavaScript?**
A: This is a static portfolio. JavaScript adds complexity and isn't needed for the current feature set. Add it only when interactivity is required (forms, animations, SPAs, etc.).

**Q: Why French and not English?**
A: The original requirement specified French content. This targets French-speaking audiences. To create an English version, translate all content while maintaining structure.

**Q: Can I use this for a blog?**
A: Yes, but you'd need to create additional HTML pages for each post. Consider a static site generator (Jekyll, Hugo, 11ty) for easier blog management.

**Q: Is this production-ready?**
A: Almost. Replace placeholder content ([Votre Nom], email), add real project descriptions, test on multiple devices, and deploy. Consider adding the SEO meta tags mentioned above.

### Technical Questions

**Q: Should I add CSS variables?**
A: Optional. CSS variables (custom properties) make theming easier but add minimal complexity. Implement if:
- User wants dark mode
- Multiple color schemes needed
- Easier maintenance is priority

**Q: How do I add a dark mode?**
A:
```css
/* Add CSS variables first */
:root {
    --bg-color: #f4f4f4;
    --text-color: #333;
    --surface-color: #fff;
}

@media (prefers-color-scheme: dark) {
    :root {
        --bg-color: #1a1a1a;
        --text-color: #e4e4e4;
        --surface-color: #2a2a2a;
    }
}

/* Update existing rules to use variables */
body {
    background-color: var(--bg-color);
    color: var(--text-color);
}
```

**Q: How do I add Google Analytics?**
A:
```html
<!-- Add before </head> -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

**Q: Can I use this with React/Vue?**
A: You *could*, but it defeats the purpose. This template is intentionally simple. For React/Vue projects, use their official scaffolding tools (Vite, Create React App, Nuxt, etc.).

**Q: How do I add a contact form?**
A: Use a third-party service since this is static:
- **Formspree**: https://formspree.io
- **Netlify Forms**: Built-in if using Netlify
- **Google Forms**: Embed an iframe
- **Custom backend**: Requires server-side code (Node.js, PHP, etc.)

**Q: Why no build process?**
A: Simplicity. Build tools (webpack, Vite, Parcel) are valuable for complex apps but overkill here. They add:
- Setup time
- Dependencies (node_modules)
- Learning curve
- Maintenance overhead

Add them only when needed (TypeScript, JSX, SASS, bundling, etc.).

**Q: Should I minify CSS/HTML?**
A: For production, yes (marginal benefit). Tools:
```bash
# CSS minification
npx csso-cli style.css --output style.min.css

# HTML minification
npx html-minifier-terser index.html -o index.min.html --collapse-whitespace
```

But at <3KB total, the impact is minimal (~20-30% reduction).

### Deployment Questions

**Q: Where should I host this?**
A: Best options (all free):
1. **GitHub Pages**: Push to repo, enable in settings
2. **Netlify**: Drag & drop or Git integration
3. **Vercel**: Git integration, automatic deployments
4. **Cloudflare Pages**: Fast CDN, Git integration
5. **Traditional hosting**: Any shared hosting, FTP upload

**Q: Do I need a domain name?**
A: No, but recommended for professional portfolios. Free subdomains available:
- GitHub Pages: `username.github.io`
- Netlify: `random-name.netlify.app`
- Vercel: `project-name.vercel.app`

**Q: How do I set up a custom domain?**
A:
1. Buy domain (Namecheap, Google Domains, etc.)
2. Add DNS records (CNAME or A record)
3. Configure in hosting platform settings
4. Enable HTTPS (usually automatic)

**Q: How often should I update CLAUDE.md?**
A: Update when:
- Architecture changes (new files, structure)
- Conventions change (switching from French to bilingual)
- New patterns emerge (component library, new sections)
- Major features added (JavaScript, build process)

Minor CSS tweaks don't require updates.

---

## Code Quality Standards

### HTML Best Practices

```html
<!-- ✅ DO: Semantic, accessible markup -->
<section id="projets" aria-labelledby="projets-heading">
    <h2 id="projets-heading">Mes Projets</h2>
    <article class="projet">
        <h3>Nom du Projet</h3>
        <p>Description significative du projet...</p>
        <a href="/projet-details.html">En savoir plus</a>
    </article>
</section>

<!-- ❌ DON'T: Divs for everything -->
<div class="section">
    <div class="title">Mes Projets</div>
    <div class="projet">
        <div class="projet-title">Nom du Projet</div>
        <div class="projet-description">Description...</div>
    </div>
</div>
```

### CSS Best Practices

```css
/* ✅ DO: Mobile-first, clear selectors */
.projet {
    padding: 1rem;
}

@media (min-width: 768px) {
    .projet {
        padding: 1.5rem;
    }
}

/* ❌ DON'T: Desktop-first with !important */
.projet {
    padding: 1.5rem !important;
}

@media (max-width: 767px) {
    .projet {
        padding: 1rem !important;
    }
}
```

```css
/* ✅ DO: Low specificity, reusable */
.button {
    padding: 0.5rem 1rem;
    background: #333;
    color: #fff;
}

/* ❌ DON'T: Over-specific selectors */
section#projets div.projet div.button-container a.button.primary {
    padding: 0.5rem 1rem;
}
```

### Validation

```bash
# HTML validation (online)
# Visit: https://validator.w3.org/
# Upload index.html or enter URL

# CSS validation
# Visit: https://jigsaw.w3.org/css-validator/
# Upload style.css

# Accessibility testing
# Visit: https://wave.webaim.org/
# Enter URL after deployment
```

---

## Advanced Patterns & Examples

### Adding a Navigation Menu

```html
<!-- Add after <header> opening tag, before <h1> -->
<nav aria-label="Navigation principale">
    <ul>
        <li><a href="#a-propos">À propos</a></li>
        <li><a href="#projets">Projets</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>
```

```css
/* Add to style.css */
nav {
    background: #444;
}

nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    gap: 2rem;
}

nav a {
    color: #fff;
    text-decoration: none;
    padding: 1rem;
    display: block;
    transition: background 0.3s;
}

nav a:hover,
nav a:focus {
    background: #555;
}

/* Mobile: Stack vertically */
@media (max-width: 600px) {
    nav ul {
        flex-direction: column;
        gap: 0;
    }
}
```

### Adding Smooth Scroll

```css
/* Add to style.css */
html {
    scroll-behavior: smooth;
}

/* Respect user preference */
@media (prefers-reduced-motion: reduce) {
    html {
        scroll-behavior: auto;
    }
}
```

### Adding Animations

```css
/* Fade-in sections on load */
@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

section {
    animation: fadeIn 0.6s ease-out;
}

/* Stagger animations */
section:nth-child(1) { animation-delay: 0.1s; }
section:nth-child(2) { animation-delay: 0.2s; }
section:nth-child(3) { animation-delay: 0.3s; }

/* Respect reduced motion preference */
@media (prefers-reduced-motion: reduce) {
    section {
        animation: none;
    }
}
```

### Adding a Contact Form

```html
<!-- Add new section before footer -->
<section id="contact">
    <h2>Contactez-moi</h2>
    <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
        <div class="form-group">
            <label for="name">Nom *</label>
            <input type="text" id="name" name="name" required>
        </div>

        <div class="form-group">
            <label for="email">Email *</label>
            <input type="email" id="email" name="email" required>
        </div>

        <div class="form-group">
            <label for="message">Message *</label>
            <textarea id="message" name="message" rows="5" required></textarea>
        </div>

        <button type="submit">Envoyer</button>
    </form>
</section>
```

```css
/* Add to style.css */
.form-group {
    margin-bottom: 1rem;
}

label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 600;
}

input,
textarea {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-family: inherit;
    font-size: 1rem;
}

input:focus,
textarea:focus {
    outline: 2px solid #333;
    outline-offset: 2px;
}

button {
    background: #333;
    color: #fff;
    padding: 0.75rem 2rem;
    border: none;
    border-radius: 4px;
    font-size: 1rem;
    cursor: pointer;
    transition: background 0.3s;
}

button:hover,
button:focus {
    background: #555;
}
```

### Adding Project Images

```html
<!-- Update projet structure -->
<div class="projet">
    <img src="images/projet1.jpg" alt="Capture d'écran du Projet 1" loading="lazy" width="600" height="400">
    <h3>Projet 1</h3>
    <p>Description du premier projet...</p>
    <div class="projet-links">
        <a href="https://projet1.com" target="_blank" rel="noopener">Voir le site</a>
        <a href="https://github.com/user/projet1" target="_blank" rel="noopener">Code source</a>
    </div>
</div>
```

```css
/* Add to style.css */
.projet img {
    width: 100%;
    height: auto;
    border-radius: 8px;
    margin-bottom: 1rem;
}

.projet-links {
    display: flex;
    gap: 1rem;
    margin-top: 1rem;
}

.projet-links a {
    padding: 0.5rem 1rem;
    background: #f4f4f4;
    border-radius: 4px;
    text-decoration: none;
    color: #333;
    transition: background 0.3s;
}

.projet-links a:hover {
    background: #e0e0e0;
}
```

---

## Project Context

### Repository History

- **Initial Commit** (1f6049d): "I have created a basic portfolio website template for you."
  - Created basic two-file structure
  - Established French language convention
  - Set up clean, minimal design system

### Current State

- **Status**: Template/starter project
- **Completion**: Basic structure complete, ready for customization
- **Placeholders**: Name, email, project descriptions need personalization
- **Branches**: Development on `claude/` prefixed branches

---

## Quick Reference

### File Locations
- HTML: `/home/user/fluffy-chainsaw/index.html`
- CSS: `/home/user/fluffy-chainsaw/style.css`

### Key Patterns
```html
<!-- Section Pattern -->
<section id="unique-id">
    <h2>Section Title</h2>
    <p>Content here...</p>
</section>

<!-- Project Card Pattern -->
<div class="projet">
    <h3>Project Name</h3>
    <p>Project description...</p>
</div>
```

### Common Commands
```bash
# View current structure
ls -la

# Check git status
git status

# Commit and push changes
git add .
git commit -m "Description of changes"
git push -u origin claude/claude-md-mirw4kvs9laqp86a-013VNYVY21c1istSC9eusZ31
```

---

## Questions?

When uncertain about:
- **Design decisions**: Follow existing patterns in style.css
- **Content changes**: Maintain French language
- **New features**: Ask user for clarification before adding
- **Architecture**: Keep it simple, avoid over-engineering

**Remember**: This is a portfolio template meant to be customized. Focus on maintainability, simplicity, and preserving the clean design aesthetic.

---

---

## Document Changelog

- **v2.0** (2026-01-16): Major expansion with performance, accessibility, SEO, responsive design, browser compatibility, troubleshooting, FAQ, code quality standards, and advanced patterns sections
- **v1.0** (2025-12-04): Initial CLAUDE.md creation with basic structure and guidelines

---

*This CLAUDE.md file was created to help AI assistants understand and work effectively with this codebase. Last updated: January 16, 2026*
