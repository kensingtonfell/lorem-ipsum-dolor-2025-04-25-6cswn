# Landing Page Maintenance Guide

This guide will help you maintain and customize your landing page. It's written for beginners and provides step-by-step instructions for common updates.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Text Content Updates

#### Header Section
The header contains your logo and navigation menu. To update:
```html
<!-- Find this near the top of the file -->
<a href="/" class="text-2xl font-bold">Logo</a>  <!-- Replace "Logo" with your company name -->

<!-- Navigation menu items -->
<a href="#features">Features</a>  <!-- Update menu text here -->
<a href="#benefits">Benefits</a>  <!-- Update menu text here -->
```

#### Hero Section
Located at the top of the page with large text:
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl">Lorem ipsum dolor</h1>
<!-- Replace "Lorem ipsum dolor" with your main headline -->

<p class="text-xl md:text-2xl">Lorem ipsum dolor</p>
<!-- Replace with your subheading text -->
```

#### Features Section
Each feature card follows this structure:
```html
<div class="p-8 rounded-2xl bg-white shadow-lg">
    <h3 class="text-xl font-semibold">Lorem ipsum dolor</h3>
    <!-- Replace with your feature title -->
    <p class="text-gray-600">Lorem ipsum dolor sit amet</p>
    <!-- Replace with your feature description -->
</div>
```

### Tailwind CSS Modifications

#### Understanding Responsive Classes
- `md:` prefix applies styles on medium screens (768px+)
- `lg:` prefix applies styles on large screens (1024px+)
- Example: `text-4xl md:text-5xl lg:text-6xl` means:
  - Mobile: text-4xl (2.25rem)
  - Tablet: text-5xl (3rem)
  - Desktop: text-6xl (3.75rem)

#### Common Tailwind Classes Used
```html
<!-- Spacing -->
px-4 = padding left/right 1rem
py-4 = padding top/bottom 1rem
mb-8 = margin bottom 2rem

<!-- Colors -->
text-gray-900 = dark text
text-gray-600 = lighter text
bg-white = white background

<!-- Hover Effects -->
hover:shadow-xl = larger shadow on hover
hover:scale-105 = slight growth on hover
```

## Fixing Broken Links

### Navigation Menu Links
Current internal links in the navigation:
```html
<nav>
    <a href="#features">Features</a>
    <a href="#benefits">Benefits</a>
    <a href="#contact">Contact Us</a>
</nav>
```
To update:
1. For internal sections, keep the `#` prefix
2. For external pages, use full URLs:
```html
<a href="https://yourwebsite.com/about">About</a>
```

### Footer Links
Current footer structure:
```html
<footer>
    <ul>
        <li><a href="#">About</a></li>
        <li><a href="#">Blog</a></li>
        <li><a href="#">Careers</a></li>
    </ul>
</footer>
```
Replace `#` with actual URLs:
```html
<li><a href="https://yourwebsite.com/about">About</a></li>
```

## Linking Privacy and Terms Pages

### Adding Privacy and Terms Links
Add these links to the footer section:
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12">
    <!-- Add a new column or add to existing column -->
    <div>
        <h3 class="text-xl font-bold mb-4">Legal</h3>
        <ul class="space-y-2">
            <li><a href="/privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
            <li><a href="/terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
        </ul>
    </div>
</div>
```

### Styling Consistency
- Use `text-gray-400` for default state
- Use `hover:text-white` for hover state
- Include `transition-colors duration-300` for smooth transitions

## Troubleshooting

### Common Issues

1. **Broken Internal Links**
   - Ensure section IDs match exactly:
   ```html
   <a href="#features">Features</a> <!-- Link -->
   <section id="features">...</section> <!-- Target section -->
   ```

2. **Responsive Design Issues**
   - Check viewport meta tag is present:
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```
   - Verify responsive classes are properly ordered (mobile → tablet → desktop)

3. **Missing Styles**
   - Confirm Tailwind CSS is properly loaded:
   ```html
   <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
   ```

### Need Help?
- Double-check class names against [Tailwind CSS documentation](https://tailwindcss.com/docs)
- Use browser developer tools (F12) to inspect elements
- Ensure all HTML tags are properly closed
- Validate your HTML using [W3C Validator](https://validator.w3.org/)

Remember to always test your changes across different devices and browsers after making updates.