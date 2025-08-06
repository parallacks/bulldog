# Brick Wall Bulldogs Website

A modern static site built with **11ty (Eleventy)** for easy maintenance and shared components.

## 🚀 Quick Start

```bash
# Install dependencies
npm install

# Start development server (with live reload)
npm start

# Build for production
npm run build

# Clean build directory
npm run clean
```

## 📁 Project Structure

```
src/
├── _includes/          # Reusable components
│   ├── head.njk       # <head> section with fonts & styles
│   ├── header.njk     # Site header with logo
│   ├── nav.njk        # Navigation menu
│   ├── footer.njk     # Site footer
│   └── scripts.njk    # JavaScript includes
├── _layouts/
│   └── base.njk       # Main page layout
├── assets/            # Images, fonts, etc.
└── *.njk              # Page content files
```

## ✨ Benefits of This Setup

### **Shared Components**
- **Header, navigation, footer** are defined once and used everywhere
- **CSS and fonts** are centralized in `_includes/head.njk`
- **JavaScript** is shared via `_includes/scripts.njk`

### **Easy Page Creation**
Create a new page by adding a `.njk` file:

```html
---
layout: base.njk
title: New Page
---

<h1>Your content here</h1>
<p>Automatically gets header, nav, footer, and styling!</p>
```

### **Consistent Styling**
- All your beautiful Tailwind styles are in `_includes/head.njk`
- Fonts, animations, and custom CSS are shared across all pages
- No more copying and pasting style blocks!

## 🛠 How to Add New Pages

1. **Create a new `.njk` file** in the `src/` directory
2. **Add frontmatter** with layout and title:
   ```yaml
   ---
   layout: base.njk
   title: Your Page Title
   ---
   ```
3. **Write your content** using HTML
4. **Build** and the page is automatically included!

## 🔧 Customizing Components

### Update Navigation
Edit `src/_includes/nav.njk` to add/remove menu items.

### Change Styling
Modify `src/_includes/head.njk` to update:
- Colors and theme
- Fonts and typography
- Animations and effects
- Responsive breakpoints

### Add JavaScript
Include new scripts in `src/_includes/scripts.njk`.

## 🌐 URL Structure

11ty automatically creates clean URLs:
- `src/index.njk` → `/`
- `src/about-us.njk` → `/about-us/`
- `src/contact.njk` → `/contact/`
- `src/services/research.njk` → `/services/research/`

## 📦 What's Included

✅ **Modern styling** with Tailwind CSS
✅ **Google Fonts** (Playfair Display + Inter)
✅ **Scroll animations** and interactive effects
✅ **Mobile responsive** design
✅ **Clean URLs** and SEO-friendly structure
✅ **Fast build times** and live reload
✅ **Easy deployment** to any static host

## 🚀 Deployment

The `_site` directory contains your built website. Deploy it to:
- **Netlify**: Drag & drop the `_site` folder
- **Vercel**: Connect your GitHub repo
- **GitHub Pages**: Push `_site` contents to `gh-pages` branch
- **Any static host**: Upload `_site` contents

## 🔄 Migrating Existing Pages

To convert your existing HTML pages:

1. **Copy the content** between `<body>` tags (excluding header, nav, footer)
2. **Create a new `.njk` file** with frontmatter
3. **Paste the content** below the frontmatter
4. **Update asset paths** to use `/assets/` instead of `./assets/`
5. **Update internal links** to use clean URLs (e.g., `/about-us/` instead of `about-us.html`)

## 💡 Pro Tips

- **Nunjucks templating**: Use `{{ variable }}` and `{% if %}` for dynamic content
- **Data files**: Add `.json` files to `src/_data/` for site-wide data
- **Collections**: Group related pages with tags
- **Shortcodes**: Create reusable content snippets
- **Plugins**: Extend 11ty with community plugins

Your site now has a maintainable structure while keeping all the beautiful styling and functionality you've built!