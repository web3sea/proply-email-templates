# Email Responsiveness Guide

## Mobile-First Email Design

## Overview

Email responsiveness ensures optimal viewing across all devices. This guide establishes standards for creating mobile-friendly Proply email templates that work seamlessly on smartphones, tablets, and desktops.

## Core Principles

### Single-Column Layout Strategy
Design emails with a single-column approach that naturally stacks on mobile devices:

```html
<table role="presentation" cellpadding="0" cellspacing="0" border="0" width="100%" style="max-width: 600px;">
  <tr>
    <td style="padding: 20px;">
      <!-- Header section -->
    </td>
  </tr>
  <tr>
    <td style="padding: 20px;">
      <!-- Content section -->
    </td>
  </tr>
  <tr>
    <td style="padding: 20px;">
      <!-- Footer section -->
    </td>
  </tr>
</table>
```

### Fluid Width Containers
Use percentage-based widths with maximum constraints:

```html
<table role="presentation" width="100%" style="max-width: 600px; margin: 0 auto;">
```

## Viewport and Meta Tags

### Essential Meta Tags
Include these meta tags in every email template:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="x-apple-disable-message-reformatting">
<meta name="format-detection" content="telephone=no, address=no, email=no, date=no, url=no">
```

### Explanation:
- `viewport`: Controls mobile scaling
- `x-apple-disable-message-reformatting`: Prevents iOS Mail from reformatting
- `format-detection`: Prevents automatic link creation

## Media Queries

### Email-Safe Media Queries
Use these tested media query approaches:

```html
<style type="text/css">
  /* Mobile styles */
  @media screen and (max-width: 600px) {
    .mobile-width {
      width: 100% !important;
      max-width: 100% !important;
    }
    
    .mobile-padding {
      padding-left: 10px !important;
      padding-right: 10px !important;
    }
    
    .mobile-center {
      text-align: center !important;
    }
    
    .mobile-hide {
      display: none !important;
    }
    
    .mobile-stack {
      display: block !important;
      width: 100% !important;
      max-width: 100% !important;
    }
  }
  
  /* Small mobile styles */
  @media screen and (max-width: 480px) {
    .small-mobile-padding {
      padding: 10px !important;
    }
    
    .small-mobile-font {
      font-size: 14px !important;
      line-height: 1.4 !important;
    }
  }
</style>
```

## Typography Responsiveness

### Font Size Guidelines

**Desktop (600px+ screens):**
- Headlines: 24px - 28px
- Body text: 16px - 18px
- Small text: 14px

**Mobile (under 600px):**
- Headlines: 20px - 24px
- Body text: 14px - 16px
- Small text: 12px (minimum)

### Implementation Example:
```html
<td style="font-size: 24px; line-height: 1.3; font-family: Arial, sans-serif;" class="mobile-font-adjust">
  <h1 style="margin: 0; font-size: 24px;" class="mobile-h1">Welcome to Proply</h1>
</td>

<style>
  @media screen and (max-width: 600px) {
    .mobile-h1 {
      font-size: 20px !important;
    }
    .mobile-font-adjust {
      font-size: 20px !important;
    }
  }
</style>
```

## Button Responsiveness

### Mobile-Friendly Buttons
Create buttons that are easily tappable on mobile:

```html
<!-- Desktop/Mobile Button -->
<table role="presentation" cellpadding="0" cellspacing="0" border="0" class="mobile-button-container">
  <tr>
    <td style="border-radius: 4px; background-color: #007bff; text-align: center;" class="mobile-button">
      <a href="#" style="display: inline-block; padding: 14px 28px; font-family: Arial, sans-serif; font-size: 16px; color: #ffffff; text-decoration: none; border-radius: 4px; min-width: 44px; min-height: 44px; line-height: 1.4;" class="button-link">
        Get Started Today
      </a>
    </td>
  </tr>
</table>

<style>
  @media screen and (max-width: 600px) {
    .mobile-button {
      width: 100% !important;
    }
    .button-link {
      width: 90% !important;
      padding: 16px 10px !important;
      font-size: 16px !important;
    }
  }
</style>
```

### Button Requirements:
- Minimum 44px height (iOS accessibility guideline)
- Adequate padding for thumb navigation
- High contrast colors
- Full-width on mobile for easier targeting

## Image Responsiveness

### Responsive Image Implementation
Make images scale properly across devices:

```html
<img src="https://example.com/proply-hero.jpg" 
     alt="Proply dashboard interface" 
     width="600" 
     height="300" 
     style="display: block; width: 100%; max-width: 600px; height: auto; border: 0;" 
     class="responsive-image">

<style>
  @media screen and (max-width: 600px) {
    .responsive-image {
      width: 100% !important;
      height: auto !important;
      max-width: 100% !important;
    }
  }
</style>
```

### Image Best Practices:
- Always set `width` and `height` attributes
- Use `max-width: 100%` for responsiveness
- Include descriptive `alt` text
- Use `display: block` to prevent spacing issues
- Optimize file sizes for mobile connections

## Layout Patterns

### Two-Column to Single-Column
Convert desktop two-column layouts to mobile single-column:

```html
<table role="presentation" cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <td width="50%" style="vertical-align: top; padding: 20px;" class="mobile-stack">
      <!-- Left column content -->
    </td>
    <td width="50%" style="vertical-align: top; padding: 20px;" class="mobile-stack">
      <!-- Right column content -->
    </td>
  </tr>
</table>

<style>
  @media screen and (max-width: 600px) {
    .mobile-stack {
      display: block !important;
      width: 100% !important;
      padding: 10px !important;
    }
  }
</style>
```

### Content Spacing
Adjust spacing for mobile viewing:

```html
<td style="padding: 40px 30px;" class="mobile-spacing">

<style>
  @media screen and (max-width: 600px) {
    .mobile-spacing {
      padding: 20px 15px !important;
    }
  }
</style>
```

## Testing Breakpoints

### Primary Breakpoints
Test these common device widths:

- **320px**: Small smartphones (iPhone SE)
- **375px**: Standard smartphones (iPhone)
- **414px**: Large smartphones (iPhone Plus)
- **768px**: Tablets (iPad)
- **1024px**: Desktop/laptop screens

### Testing Methods
1. **Browser DevTools**: Use responsive design mode
2. **Email Testing Tools**: Litmus, Email on Acid device previews
3. **Physical Devices**: Test on actual smartphones and tablets
4. **Email Client Apps**: Gmail, Outlook, Apple Mail mobile apps

## Dark Mode Responsiveness

### Media Query for Dark Mode
Combine dark mode with responsive design:

```html
<style>
  @media screen and (max-width: 600px) {
    .mobile-text { font-size: 14px !important; }
  }
  
  @media (prefers-color-scheme: dark) {
    .dark-bg { background-color: #1a1a1a !important; }
    .dark-text { color: #ffffff !important; }
  }
  
  @media screen and (max-width: 600px) and (prefers-color-scheme: dark) {
    .mobile-dark-text { 
      font-size: 14px !important; 
      color: #ffffff !important; 
    }
  }
</style>
```

## Common Responsive Issues

### Problem Solutions

**Issue: Text too small on mobile**
```css
@media screen and (max-width: 600px) {
  .body-text { font-size: 16px !important; }
}
```

**Issue: Buttons too small to tap**
```css
@media screen and (max-width: 600px) {
  .cta-button { 
    padding: 16px 20px !important; 
    min-height: 44px !important; 
  }
}
```

**Issue: Images overflowing container**
```css
.responsive-image {
  max-width: 100% !important;
  height: auto !important;
}
```

## Email Client Considerations

### Client-Specific Responsive Support

**Gmail Mobile App:**
- Supports media queries
- Automatically scales non-responsive emails
- Prefers single-column layouts

**iOS Mail:**
- Excellent media query support
- May auto-scale text if too small
- Supports complex responsive layouts

**Outlook Mobile:**
- Limited media query support
- Relies more on fluid layouts
- Single-column approach works best

**Android Email Apps:**
- Varies by app and Android version
- Gmail app has best support
- Simple responsive patterns work best

## Validation Checklist

Before finalizing responsive email templates:

- [ ] Test on multiple screen sizes (320px - 1024px+)
- [ ] Verify text readability on small screens
- [ ] Confirm buttons are easily tappable (44px minimum)
- [ ] Check image scaling and quality
- [ ] Validate layout doesn't break on narrow screens
- [ ] Test in major email clients' mobile apps
- [ ] Verify media queries work as expected
- [ ] Check loading speed on mobile connections

## Performance Considerations

### Mobile Optimization
- Keep total email size under 100KB
- Optimize images for retina displays
- Minimize CSS complexity
- Use system fonts when possible
- Test on slower mobile connections

Following these responsive design principles ensures Proply's email templates provide an excellent user experience across all devices and email clients.