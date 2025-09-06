# Dark Mode Email Implementation Guide

## Overview

Dark mode support in emails provides users with their preferred viewing experience and reduces eye strain. This guide covers implementing dark mode for Proply email templates with proper fallbacks for unsupported clients.

## Meta Tag Requirements

### Essential Dark Mode Meta Tags
Include these meta tags in every email template:

```html
<meta name="color-scheme" content="light dark">
<meta name="supported-color-schemes" content="light dark">
```

### Complete Meta Tag Section:
```html
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="x-apple-disable-message-reformatting">
  <meta name="color-scheme" content="light dark">
  <meta name="supported-color-schemes" content="light dark">
</head>
```

## CSS Media Queries

### Basic Dark Mode Media Query
```css
@media (prefers-color-scheme: dark) {
  /* Dark mode styles here */
}
```

### Complete Dark Mode CSS Implementation:
```html
<style type="text/css">
  /* Light mode (default) styles */
  .body-bg { background-color: #ffffff !important; }
  .content-bg { background-color: #f8f9fa !important; }
  .text-primary { color: #333333 !important; }
  .text-secondary { color: #666666 !important; }
  .button-primary { background-color: #007bff !important; }
  .border-color { border-color: #e0e0e0 !important; }

  /* Dark mode styles */
  @media (prefers-color-scheme: dark) {
    .body-bg { background-color: #1a1a1a !important; }
    .content-bg { background-color: #2d2d2d !important; }
    .text-primary { color: #ffffff !important; }
    .text-secondary { color: #cccccc !important; }
    .button-primary { background-color: #0d6efd !important; }
    .border-color { border-color: #404040 !important; }
    
    /* Override inline styles in dark mode */
    .dark-override {
      background-color: #2d2d2d !important;
      color: #ffffff !important;
    }
  }
</style>
```

## Color Scheme Strategy

### Proply Dark Mode Color Palette
Define a complete color system for both light and dark modes:

```css
/* Light Mode Colors */
:root {
  --bg-primary: #ffffff;
  --bg-secondary: #f8f9fa;
  --text-primary: #333333;
  --text-secondary: #666666;
  --accent-color: #007bff;
  --border-color: #e0e0e0;
}

/* Dark Mode Colors */
@media (prefers-color-scheme: dark) {
  :root {
    --bg-primary: #1a1a1a;
    --bg-secondary: #2d2d2d;
    --text-primary: #ffffff;
    --text-secondary: #cccccc;
    --accent-color: #0d6efd;
    --border-color: #404040;
  }
}
```

### Practical Implementation:
Since CSS custom properties have limited email support, use classes:

```html
<td style="background-color: #ffffff; color: #333333;" class="body-bg text-primary">
  Content here
</td>
```

## Image Handling in Dark Mode

### Dark Mode Image Strategy
Provide image alternatives for dark mode when needed:

```html
<!-- Light mode image (default) -->
<img src="https://proply.com/images/logo-light.png" 
     alt="Proply Logo" 
     width="200" 
     height="60" 
     style="display: block;" 
     class="light-mode-img">

<!-- Dark mode image (hidden by default) -->
<img src="https://proply.com/images/logo-dark.png" 
     alt="Proply Logo" 
     width="200" 
     height="60" 
     style="display: none;" 
     class="dark-mode-img">

<style>
  @media (prefers-color-scheme: dark) {
    .light-mode-img { display: none !important; }
    .dark-mode-img { display: block !important; }
  }
</style>
```

### Single Image with Background Fallback:
For images that work in both modes, provide background color fallbacks:

```html
<img src="https://proply.com/images/illustration.png" 
     alt="Feature illustration" 
     width="300" 
     height="200" 
     style="display: block; background-color: #f0f0f0;" 
     class="adaptive-image">

<style>
  @media (prefers-color-scheme: dark) {
    .adaptive-image {
      background-color: #404040 !important;
    }
  }
</style>
```

## Button Design for Dark Mode

### Dark Mode Button Implementation:
```html
<table role="presentation" cellpadding="0" cellspacing="0" border="0">
  <tr>
    <td style="border-radius: 6px; background-color: #007bff;" class="button-primary dark-button-bg">
      <a href="#" 
         style="display: inline-block; padding: 14px 28px; font-family: Arial, sans-serif; font-size: 16px; color: #ffffff; text-decoration: none; border-radius: 6px;" 
         class="button-text">
        Get Started
      </a>
    </td>
  </tr>
</table>

<style>
  @media (prefers-color-scheme: dark) {
    .dark-button-bg {
      background-color: #0d6efd !important;
      border: 1px solid #0d6efd !important;
    }
    .button-text {
      color: #ffffff !important;
    }
  }
</style>
```

### Secondary Button for Dark Mode:
```html
<td style="border-radius: 6px; background-color: transparent; border: 2px solid #007bff;" class="secondary-button">
  <a href="#" 
     style="display: inline-block; padding: 12px 26px; color: #007bff; text-decoration: none;" 
     class="secondary-button-text">
    Learn More
  </a>
</td>

<style>
  @media (prefers-color-scheme: dark) {
    .secondary-button {
      border-color: #0d6efd !important;
    }
    .secondary-button-text {
      color: #0d6efd !important;
    }
  }
</style>
```

## Layout Structure for Dark Mode

### Complete Email Structure Template:
```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="color-scheme" content="light dark">
  <meta name="supported-color-schemes" content="light dark">
  
  <style type="text/css">
    /* Light mode defaults */
    .email-body { background-color: #ffffff !important; }
    .content-area { background-color: #ffffff !important; }
    .text-primary { color: #333333 !important; }
    .text-secondary { color: #666666 !important; }
    
    /* Dark mode overrides */
    @media (prefers-color-scheme: dark) {
      .email-body { background-color: #1a1a1a !important; }
      .content-area { background-color: #2d2d2d !important; }
      .text-primary { color: #ffffff !important; }
      .text-secondary { color: #cccccc !important; }
    }
  </style>
</head>

<body style="margin: 0; padding: 0; background-color: #ffffff;" class="email-body">
  <table role="presentation" width="100%" cellpadding="0" cellspacing="0" border="0" style="background-color: #ffffff;" class="email-body">
    <tr>
      <td align="center" style="padding: 20px;">
        <table role="presentation" width="600" cellpadding="0" cellspacing="0" border="0" style="max-width: 600px; background-color: #ffffff;" class="content-area">
          <tr>
            <td style="padding: 40px 30px; color: #333333;" class="text-primary">
              <!-- Email content here -->
            </td>
          </tr>
        </table>
      </td>
    </tr>
  </table>
</body>
</html>
```

## Email Client Support

### Dark Mode Support by Client:

**Full Support:**
- Apple Mail (iOS 13+, macOS 10.14+)
- Outlook for iOS/Android
- Gmail (iOS/Android apps)

**Partial Support:**
- Outlook.com (web)
- Yahoo Mail (mobile apps)

**No Support:**
- Outlook desktop (Windows/Mac)
- Gmail web interface
- Thunderbird

### Fallback Strategy:
Always design for light mode as the default, with dark mode as an enhancement:

```html
<!-- Default light mode styling, enhanced with dark mode -->
<td style="background-color: #ffffff; color: #333333;" class="adaptive-cell">
```

## Testing Dark Mode

### Testing Methods:

**Device Settings:**
- iOS: Settings > Display & Brightness > Dark
- Android: Settings > Display > Theme > Dark
- macOS: System Preferences > General > Appearance > Dark

**Browser Testing:**
- Chrome DevTools: Settings > Preferences > Appearance > Dark
- Firefox: View > Page Style > No Style (approximates dark mode)
- Safari: Develop > Experimental Features > Dark Mode CSS Support

### Testing Checklist:
- [ ] Test in Apple Mail with dark mode enabled
- [ ] Check Gmail mobile app in dark mode
- [ ] Verify Outlook mobile in dark mode
- [ ] Test image visibility in dark backgrounds
- [ ] Confirm text contrast ratios
- [ ] Check button visibility and contrast
- [ ] Validate link colors are visible
- [ ] Test with images blocked scenario

## Common Dark Mode Issues

### Problem Solutions:

**Issue: Text becomes invisible**
```css
/* Always provide fallback colors */
.text { color: #333333 !important; }
@media (prefers-color-scheme: dark) {
  .text { color: #ffffff !important; }
}
```

**Issue: Images blend into dark background**
```css
/* Add border or background to images */
.dark-image-border {
  border: 1px solid #404040 !important;
}
```

**Issue: Buttons lose visibility**
```css
/* Ensure sufficient contrast in dark mode */
@media (prefers-color-scheme: dark) {
  .button { 
    background-color: #0d6efd !important;
    border: 1px solid #0d6efd !important;
  }
}
```

## Advanced Dark Mode Techniques

### Conditional Content for Dark Mode:
```html
<!-- Show different content based on mode -->
<div class="light-only" style="display: block;">
  Light mode content here
</div>
<div class="dark-only" style="display: none;">
  Dark mode specific content here
</div>

<style>
  @media (prefers-color-scheme: dark) {
    .light-only { display: none !important; }
    .dark-only { display: block !important; }
  }
</style>
```

### Mixed Mode Support:
Handle cases where users have mixed preferences:

```html
<style>
  /* Force light mode for specific sections if needed */
  .force-light {
    background-color: #ffffff !important;
    color: #333333 !important;
  }
  
  /* This section stays light even in dark mode */
  @media (prefers-color-scheme: dark) {
    .force-light {
      background-color: #ffffff !important;
      color: #333333 !important;
    }
  }
</style>
```

## Accessibility in Dark Mode

### Contrast Requirements:
- Maintain 4.5:1 contrast ratio in both modes
- Test with accessibility tools
- Ensure link visibility in both modes

### Color Considerations:
```css
/* High contrast colors for both modes */
.high-contrast-text {
  color: #000000; /* Black on light backgrounds */
}

@media (prefers-color-scheme: dark) {
  .high-contrast-text {
    color: #ffffff; /* White on dark backgrounds */
  }
}
```

## Final Implementation Checklist

Before deploying dark mode email templates:

- [ ] Include proper meta tags for dark mode
- [ ] Implement media queries for color scheme
- [ ] Test on devices with dark mode enabled
- [ ] Verify image visibility in both modes
- [ ] Check button contrast and visibility  
- [ ] Validate text readability in both modes
- [ ] Test fallback behavior in unsupported clients
- [ ] Confirm accessibility standards are met
- [ ] Test email in multiple clients and devices
- [ ] Validate HTML and CSS syntax

Following this guide ensures Proply's email templates provide an excellent experience for users regardless of their color scheme preference.