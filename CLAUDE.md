# CLAUDE.md - AI Assistant Guide

## Project Overview

**fluffy-chainsaw** is a simple, clean portfolio website template written in French. It's designed as a starting point for showcasing personal projects, skills, and contact information. The site uses pure HTML5 and CSS3 without any frameworks or build tools, making it lightweight and easy to customize.

**Primary Language**: French (content and UI text)
**Last Updated**: December 2025

---

## Codebase Structure

```
fluffy-chainsaw/
├── index.html          # Main HTML structure and content
├── style.css           # All styling and visual design
└── CLAUDE.md           # This file - AI assistant guidelines
```

### File Descriptions

- **index.html** (47 lines): Contains the complete page structure including header, about section, projects showcase, and footer with contact information
- **style.css** (67 lines): Defines all visual styling using modern CSS with a clean, professional design system

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

*This CLAUDE.md file was automatically generated to help AI assistants understand and work effectively with this codebase. Last updated: December 4, 2025*
