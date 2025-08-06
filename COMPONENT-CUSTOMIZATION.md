# Component Customization Guide 🎨

This guide shows you how to customize the shared components in your 11ty site. All changes you make to shared components automatically apply to every page!

## 🧭 Navigation Customization (`src/_includes/nav.njk`)

### Add New Navigation Items
```html
<!-- Add to the main navigation list -->
<li><a href="/blog/" class="text-white font-bold hover:text-light-brown transition-colors">Blog</a></li>
```

### Add New Services to Dropdown
```html
<!-- Add inside the Services dropdown -->
<li><a href="/consultation-service/" class="block px-4 py-2 text-white hover:bg-light-brown transition-colors">Consultation</a></li>
```

### Change Navigation Styling
```html
<!-- Modify the main nav container -->
<nav class="bg-deep-brown p-4 shadow-lg"> <!-- Added shadow -->
```

## 🎨 Styling Customization (`src/_includes/head.njk`)

### Add New Colors
```javascript
// Add to the Tailwind config colors section
colors: {
    'accent-gold': '#D4AF37',
    'success-green': '#10B981',
    'your-custom-color': '#123456',
}
```

### Create New Animations
```javascript
// Add to animations
animation: {
    'your-animation': 'yourKeyframe 0.6s ease-out',
}

// Add corresponding keyframe
keyframes: {
    yourKeyframe: {
        '0%': { opacity: '0', transform: 'scale(0.5)' },
        '100%': { opacity: '1', transform: 'scale(1)' }
    }
}
```

### Add Custom CSS Classes
```css
/* Add to the <style> section */
.your-custom-class {
    background: linear-gradient(135deg, #8F3C3C, #d17878);
    border-radius: 15px;
    padding: 2rem;
}
```

## 🏠 Header Customization (`src/_includes/header.njk`)

### Add Company Tagline
```html
<header class="bg-gradient-to-r from-brick-red to-deep-brown text-white p-4 text-center animate-fade-in">
    <div class="flex items-center justify-center gap-4 mb-4">
        <!-- logo and title -->
    </div>
    <p class="text-light-brick text-lg font-light italic">Your Custom Tagline Here</p>
</header>
```

### Change Header Colors
```html
<!-- Change the gradient colors -->
<header class="bg-gradient-to-r from-accent-gold to-success-green text-white...">
```

### Add Header Animation
```html
<!-- Add bounce-in animation to logo -->
<div class="w-20 h-20 bg-light-brown rounded-full flex items-center justify-center overflow-hidden service-icon pulse-on-hover animate-bounce-in">
```

## 👣 Footer Customization (`src/_includes/footer.njk`)

### Add New Social Media Links
```html
<!-- Add inside the social links container -->
<a href="#" class="bg-brick-red hover:bg-light-brick w-10 h-10 rounded-full flex items-center justify-center transition-colors" aria-label="YouTube">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
        <!-- YouTube icon path -->
        <path d="M22.54 6.42a2.78 2.78 0 0 0-1.94-2C18.88 4 12 4 12 4s-6.88 0-8.6.46a2.78 2.78 0 0 0-1.94 2A29 29 0 0 0 1 11.75a29 29 0 0 0 .46 5.33A2.78 2.78 0 0 0 3.4 19c1.72.46 8.6.46 8.6.46s6.88 0 8.6-.46a2.78 2.78 0 0 0 1.94-2 29 29 0 0 0 .46-5.25 29 29 0 0 0-.46-5.33z"></path>
        <polygon points="9.75,15.02 15.5,11.75 9.75,8.48"></polygon>
    </svg>
</a>
```

### Update Copyright Text
```html
<p>&copy; 2025 Your Company Name. All rights reserved.</p>
```

## 🧩 Creating Reusable Components

### Example: Testimonial Component (`src/_includes/testimonial.njk`)
```html
<div class="bg-cream p-6 rounded-lg shadow-lg border-l-4 border-accent-gold animate-bounce-in">
    <div class="flex items-start gap-4">
        <div class="text-accent-gold text-4xl leading-none">"</div>
        <div>
            <p class="text-gray-700 italic mb-4">{{ content }}</p>
            <div class="flex items-center gap-3">
                {% if photo %}
                <img src="{{ photo }}" alt="{{ name }}" class="w-12 h-12 rounded-full object-cover">
                {% endif %}
                <div>
                    <p class="font-semibold text-brick-red">{{ name }}</p>
                    {% if location %}
                    <p class="text-sm text-gray-600">{{ location }}</p>
                    {% endif %}
                </div>
            </div>
        </div>
    </div>
</div>
```

### Using the Testimonial Component
```html
<!-- In any page file -->
{% include "testimonial.njk" with {
    content: "This service was amazing!",
    name: "John Doe",
    location: "New York, NY",
    photo: "/assets/testimonials/john.jpg"
} %}
```

## 🎯 Quick Customization Examples

### Change Brand Colors Globally
1. Edit `src/_includes/head.njk`
2. Update the colors in the Tailwind config:
```javascript
'brick-red': '#YOUR_NEW_COLOR',
'deep-brown': '#YOUR_SECONDARY_COLOR',
```

### Add a Site-Wide Announcement Banner
1. Edit `src/_includes/header.njk`
2. Add before the main header:
```html
<div class="bg-accent-gold text-center py-2 text-sm font-semibold">
    🎉 Special Offer: 20% off all services this month!
</div>
```

### Change Fonts
1. Edit `src/_includes/head.njk`
2. Update the Google Fonts import:
```html
@import url('https://fonts.googleapis.com/css2?family=YOUR_FONT:wght@400;700&display=swap');
```
3. Update the font classes:
```css
.font-heading { font-family: 'YOUR_FONT', serif; }
```

## 📱 Responsive Customization

### Add Mobile-Specific Styles
```css
@media (max-width: 768px) {
    .your-element {
        font-size: 1.5rem !important;
        padding: 1rem !important;
    }
}
```

## 🔗 Working with Clean URLs

When linking between pages, always use the clean URL format:
```html
<!-- ✅ Correct -->
<a href="/about-us/">About Us</a>
<a href="/contact/">Contact</a>

<!-- ❌ Wrong -->
<a href="about-us.html">About Us</a>
```

## 🚀 Testing Your Changes

1. **Start development server**: `npm start`
2. **View your site**: Visit `http://localhost:8080`
3. **Check all pages**: Navigate through to ensure consistency
4. **Test responsiveness**: Resize browser window

## 💡 Pro Tips

1. **Always test on multiple pages** - Component changes affect everything
2. **Use browser dev tools** - Inspect elements to fine-tune styles
3. **Keep backups** - Git commit your changes regularly
4. **Use CSS classes** - Avoid inline styles for maintainability
5. **Follow the existing patterns** - Match the current coding style

## 🆘 Common Issues

### Colors Not Applying
- Make sure you've added the color to the Tailwind config
- Use `!important` if needed to override defaults

### Animation Not Working
- Check that both `animation` and `keyframes` are properly defined
- Ensure the class name matches exactly

### Navigation Dropdown Issues
- Verify the HTML structure matches the existing pattern
- Check that hover states are properly configured

---

**Remember**: Every change you make to shared components automatically updates across all pages! This is the power of your new 11ty setup. 🎉