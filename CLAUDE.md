# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static personal website for MoTech, a technology solutions consulting business. The site is a single-page application hosted via GitHub Pages at mattortiz.net.

## Repository Structure

- **index.html** - The main (and only) HTML file containing all site content, styles, and JavaScript
- **hexagon-background.jpg** - Hero section background image
- **matt.jpeg** - Profile photo used in the About section
- **mopic_logo.png** - Logo asset (not currently used in the live site)
- **old-index.html** - Previous version of the site (archived)
- **CNAME** - GitHub Pages custom domain configuration

## Architecture

This is a **single-file static website** with no build process, no dependencies, and no package management. The entire site lives in `index.html:1-789`.

### Key Components

**Navigation** (index.html:526-536)
- Fixed navbar with smooth scroll links
- Logo and navigation menu

**Hero Section** (index.html:539-552)
- Full viewport height
- Background image with overlay effect
- Call-to-action buttons

**Services Section** (index.html:555-579)
- Grid of 4 service cards
- Icons, titles, and descriptions for each service offering

**About Section** (index.html:582-622)
- Profile information with image
- Stats display showing provider/datacenter metrics

**Contact Form** (index.html:625-657)
- Form submission handled by submit-form.com service (endpoint: `https://submit-form.com/ug7idEJJy`)
- AJAX submission with loading states and error handling
- JavaScript implementation in index.html:695-763

### Styling Approach

All CSS is embedded in `<style>` tags (index.html:7-522):
- CSS custom properties for theming (index.html:14-25)
- Responsive design with mobile breakpoints at 768px (index.html:460-490)
- CSS animations for fade-in effects (index.html:498-521)
- Dark theme with navy blue accents

### JavaScript Features

All JavaScript is embedded in `<script>` tags (index.html:670-787):
- Smooth scrolling navigation (index.html:672-683)
- Navbar background opacity on scroll (index.html:686-693)
- Form submission with AJAX (index.html:696-763)
- Intersection Observer for scroll animations (index.html:766-786)

## Development Workflow

Since this is a static HTML file with no build process:

1. **Local Development**: Open `index.html` directly in a browser or use a local server:
   ```bash
   python -m http.server 8000
   # or
   npx serve .
   ```

2. **Making Changes**: Edit `index.html` directly and refresh the browser

3. **Deployment**: Commit and push to the `main` branch - GitHub Pages will automatically deploy

## Important Notes

- The contact form uses submit-form.com service - form submissions go to `https://submit-form.com/ug7idEJJy`
- The site is configured for the custom domain `mattortiz.net` (via CNAME file)
- No external CSS or JavaScript dependencies - everything is self-contained
- Mobile responsiveness is handled with a single breakpoint at 768px
- The navigation menu disappears on mobile (index.html:461-463) but no hamburger menu is implemented
