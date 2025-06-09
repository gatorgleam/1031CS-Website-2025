# 1031 Capital Solutions - Website Style Guide

## 🎨 Brand Colors

### Primary Palette
```css
Navy Blue (Primary): #002B45  →  var(--cs-primary)
Gold (Accent): #A48D29        →  var(--cs-accent)
White (Background): #FFFFFF   →  var(--cs-bg)
Text Gray: #26344e            →  var(--cs-text)
```

### Secondary Colors
```css
Light Gold: rgba(198, 166, 100, 0.7)  →  var(--cs-accent-light)
Disclaimer Gold: #b4953e               →  var(--cs-disclaimer)
Text Light: #333333                    →  var(--cs-text-light)
```

### Color Usage Guidelines
- **Navy Blue**: Main headings, buttons, card backgrounds, primary brand elements
- **Gold**: Accent elements, icons, borders, hover effects, call-to-action highlights
- **White**: Page backgrounds, card text, button text on navy backgrounds
- **Text Gray**: Body text, paragraphs, secondary content

---

## 📝 Typography

### Font Family
**Primary**: Montserrat (all weights: 400, 500, 600, 700)
```css
font-family: 'Montserrat', -apple-system, BlinkMacSystemFont, sans-serif;
```

### Type Scale
```css
/* Extra Small */   var(--cs-font-size-xs):   0.75rem  (12px)
/* Small */         var(--cs-font-size-sm):   0.9rem   (14.4px)
/* Base */          var(--cs-font-size-base): 0.95rem  (15.2px)
/* Large */         var(--cs-font-size-lg):   1.1rem   (17.6px)
/* Extra Large */   var(--cs-font-size-xl):   1.6rem   (25.6px)
/* 2X Large */      var(--cs-font-size-2xl):  2.1rem   (33.6px)
```

### Typography Hierarchy

#### Main Page Titles
```css
.cs-title-lg {
    font-size: var(--cs-font-size-2xl);  /* 2.1rem */
    font-weight: 700;
    color: var(--cs-primary);
    line-height: 1.2;
}
```

#### Section Headings
```css
.cs-title-md {
    font-size: var(--cs-font-size-xl);   /* 1.6rem */
    font-weight: 700;
    color: var(--cs-primary);
    line-height: 1.2;
}
```

#### Body Text
```css
.cs-text {
    font-size: var(--cs-font-size-base); /* 0.95rem */
    color: var(--cs-text);
    line-height: 1.6;
}
```

#### Small Text / Disclaimers
```css
.cs-disclaimer {
    font-size: var(--cs-font-size-sm);   /* 0.9rem */
    color: var(--cs-disclaimer);
    font-style: italic;
}
```

---

## 🔘 Buttons

### Primary Button (Gold with Navy Text)
```css
.cs-button {
    background: var(--cs-accent);        /* Gold */
    color: var(--cs-primary);            /* Navy text */
    padding: var(--cs-spacing-sm) var(--cs-spacing-xl);
    border-radius: var(--cs-radius-full); /* Fully rounded */
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
}

.cs-button:hover {
    background: var(--cs-primary);       /* Navy */
    color: var(--cs-bg);                 /* White text */
    transform: translateY(-2px);
    box-shadow: var(--cs-glow);          /* Gold glow */
}
```

### When to Use
- **Primary buttons**: Main call-to-actions, "Schedule Call", "Learn More"
- **Hover effects**: Always include gold glow and subtle lift
- **Size**: Max width 420px for optimal mobile experience

---

## 📦 Cards & Components

### Value Cards (Navy with Gold Accents)
```css
.cs-card {
    background: var(--cs-primary);       /* Navy background */
    color: var(--cs-bg);                 /* White text */
    border-radius: var(--cs-radius-md);  /* 1rem */
    padding: var(--cs-spacing-lg) var(--cs-spacing-md);
    box-shadow: var(--cs-shadow-base);
}

.cs-card:hover {
    transform: scale(1.03);
    box-shadow: var(--cs-glow);          /* Gold glow */
    z-index: 2;
}
```

### Icons in Cards
```css
.cs-icon {
    color: var(--cs-accent);             /* Gold color */
    font-size: 2em;
    animation: iconFloat 3s ease-in-out infinite;
}

.cs-icon:hover {
    animation: iconPulse 0.5s ease-in-out;
}
```

---

## 📏 Spacing System

### Spacing Scale
```css
/* Extra Small */ var(--cs-spacing-xs): 0.5rem   (8px)
/* Small */       var(--cs-spacing-sm): 1rem     (16px)
/* Medium */      var(--cs-spacing-md): 1.5rem   (24px)
/* Large */       var(--cs-spacing-lg): 2rem     (32px)
/* Extra Large */ var(--cs-spacing-xl): 3rem     (48px)
```

### Usage Guidelines
- **xs**: Icon margins, small gaps between elements
- **sm**: Button padding, small margins
- **md**: Standard padding, gaps between cards
- **lg**: Section padding, large margins
- **xl**: Major section spacing

---

## 🎭 Animations & Effects

### Card Hover Effects
```css
/* Standard card hover */
transform: scale(1.03);
box-shadow: 0 0 30px rgba(198, 166, 100, 0.7); /* Gold glow */
transition: transform 0.3s ease, box-shadow 0.5s ease;
```

### Icon Animations
```css
/* Floating animation */
@keyframes iconFloat {
    0% { transform: translateY(0); }
    50% { transform: translateY(-5px); }
    100% { transform: translateY(0); }
}

/* Pulse on hover */
@keyframes iconPulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.1); }
    100% { transform: scale(1); }
}
```

### Performance Requirements
- Always include `will-change: transform, box-shadow`
- Add `backface-visibility: hidden` for smooth animations
- Respect `prefers-reduced-motion` for accessibility

---

## 📱 Responsive Breakpoints

### Mobile First Approach
```css
/* Mobile: Default styles up to 768px */
/* Tablet/Desktop: 769px and above */

@media (max-width: 768px) {
    /* Mobile-specific styles */
    :root {
        --cs-font-size-base: 0.9rem;
        --cs-font-size-xl: 1.4rem;
        --cs-font-size-2xl: 1.8rem;
    }
}
```

### Mobile Guidelines
- Stack cards vertically
- Increase touch target sizes
- Reduce font sizes appropriately
- Simplify animations for performance

---

## 🏗️ Layout Patterns

### Grid System
```css
.cs-grid {
    display: grid;
    gap: var(--cs-spacing-md);
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 var(--cs-spacing-md);
}
```

### Flex Layouts
```css
.cs-flex {
    display: flex;
    gap: var(--cs-spacing-md);
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
}
```

---

## ✅ Best Practices

### Do's
✅ Always use CSS variables for colors and spacing
✅ Test hover effects on all interactive elements
✅ Ensure 4.5:1 color contrast ratio minimum
✅ Include focus states for keyboard navigation
✅ Test on mobile devices regularly

### Don'ts
❌ Don't use hardcoded hex colors in new components
❌ Don't forget hover states on clickable elements
❌ Don't make animations too fast or aggressive
❌ Don't ignore mobile experience
❌ Don't override global styles unnecessarily

---

## 🎯 Component Examples

### Section Title Pattern
```html
<h2 class="cs-title-lg">Our Values</h2>
<div class="cs-divider"></div>
```

### Card Grid Pattern
```html
<div class="cs-grid">
    <div class="cs-card">
        <i class="cs-icon fas fa-handshake"></i>
        <h3 class="cs-title">Trust</h3>
        <p class="cs-text">Description text here...</p>
    </div>
</div>
```

### Button Pattern
```html
<a href="#" class="cs-button">Schedule a Call</a>
```

### Disclaimer Pattern
```html
<div class="cs-disclaimer">
    Important legal disclaimer text here...
</div>
```

---

## 🔄 Maintenance Guidelines

1. **Adding New Components**: Always extend existing patterns before creating new ones
2. **Color Updates**: Only modify the CSS variables, never individual instances
3. **Testing**: Check all pages when making global changes
4. **Documentation**: Update this guide when adding new patterns
5. **Performance**: Monitor loading times after changes

---

*Last Updated: [Current Date]*
*Version: 1.0* 