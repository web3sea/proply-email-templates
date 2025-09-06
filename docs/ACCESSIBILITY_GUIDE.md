# Email Accessibility Guide

## Overview

Email accessibility ensures all users, including those with disabilities, can effectively read and interact with Proply's email content. This guide covers WCAG 2.1 AA compliance standards for email templates.

## Color and Contrast Requirements

### Contrast Ratio Standards
- **Normal text**: Minimum 4.5:1 contrast ratio
- **Large text** (18pt+/14pt+ bold): Minimum 3:1 contrast ratio
- **Interactive elements**: Minimum 3:1 contrast ratio with surrounding content

### Contrast Testing Tools
- WebAIM Contrast Checker
- Colour Contrast Analyser
- Browser DevTools accessibility features
- WAVE Web Accessibility Evaluator

### Proply Color Implementation:
```html
<!-- High contrast text examples -->
<td style="color: #333333; background-color: #ffffff;">
  <!-- 12.63:1 ratio - Excellent -->
  High contrast dark text on white background
</td>

<td style="color: #ffffff; background-color: #007bff;">
  <!-- 5.14:1 ratio - Good -->
  White text on blue background
</td>

<!-- Test your brand colors -->
<td style="color: #[BRAND-DARK]; background-color: #[BRAND-LIGHT];">
  Test with Proply brand colors
</td>
```

### Avoid These Color Combinations:
- Light gray text on white backgrounds
- Insufficient contrast for links
- Red/green only distinctions (color-blind users)
- Low contrast in dark mode

## Typography Accessibility

### Font Size Requirements
```html
<!-- Minimum readable font sizes -->
<td style="font-size: 16px; line-height: 1.5; font-family: Arial, sans-serif;">
  Body text: 16px minimum (14px absolute minimum)
</td>

<td style="font-size: 18px; line-height: 1.4; font-family: Arial, sans-serif;">
  Large text: 18px or larger
</td>

<td style="font-size: 12px; line-height: 1.4; font-family: Arial, sans-serif;">
  Small text: 12px minimum for disclaimers only
</td>
```

### Font Family Guidelines
Use web-safe, readable font stacks:

```css
/* Primary font stack */
font-family: Arial, Helvetica, sans-serif;

/* Headers */
font-family: 'Trebuchet MS', Arial, Helvetica, sans-serif;

/* Avoid these fonts */
/* font-family: cursive, fantasy, decorative fonts */
```

### Line Height and Spacing
```html
<td style="font-size: 16px; line-height: 1.5; padding-bottom: 16px;">
  Proper line height (1.5) improves readability
</td>
```

## Semantic HTML Structure

### Proper Heading Hierarchy
```html
<table role="presentation">
  <tr>
    <td>
      <h1 style="margin: 0; font-size: 24px; color: #333333;">
        Main Email Heading (H1)
      </h1>
    </td>
  </tr>
  <tr>
    <td>
      <h2 style="margin: 16px 0 8px 0; font-size: 20px; color: #333333;">
        Section Heading (H2)
      </h2>
    </td>
  </tr>
  <tr>
    <td>
      <p style="margin: 0 0 16px 0; font-size: 16px; line-height: 1.5;">
        Body paragraph with proper spacing
      </p>
    </td>
  </tr>
</table>
```

### Semantic Elements
```html
<!-- Use semantic HTML when possible -->
<strong>Important text</strong> (not <b>)
<em>Emphasized text</em> (not <i>)

<!-- Lists for structured content -->
<ul style="margin: 0; padding-left: 20px;">
  <li style="margin-bottom: 8px;">List item one</li>
  <li style="margin-bottom: 8px;">List item two</li>
</ul>
```

## Image Accessibility

### Alt Text Requirements
Every image must have descriptive alt text:

```html
<!-- Decorative images -->
<img src="decoration.jpg" alt="" width="50" height="20" style="display: block;">

<!-- Functional images -->
<img src="proply-logo.png" alt="Proply - Personalized Learning Platform" width="200" height="60" style="display: block;">

<!-- Informative images -->
<img src="chart.png" alt="Sales increased 40% in Q3 compared to Q2" width="300" height="200" style="display: block;">

<!-- Complex images -->
<img src="infographic.png" alt="Process flow: Sign up, Create Profile, Get Recommendations, Start Learning - detailed description follows" width="400" height="300" style="display: block;">
```

### Alt Text Best Practices:
- **Decorative images**: Use empty alt="" 
- **Logo images**: Include company name and purpose
- **Charts/graphs**: Describe the data trend or key insight
- **Screenshots**: Describe what the interface shows
- **Keep it concise**: 125 characters or less when possible
- **Avoid "image of" or "picture of"**

### Image Implementation:
```html
<img src="https://proply.com/images/feature.jpg" 
     alt="Dashboard showing personalized learning recommendations" 
     width="300" 
     height="200" 
     style="display: block; max-width: 100%; height: auto; border: 0;">
```

## Link Accessibility

### Descriptive Link Text
```html
<!-- Good: Descriptive link text -->
<a href="https://proply.com/signup" style="color: #007bff; text-decoration: underline;">
  Create your free Proply account
</a>

<!-- Bad: Non-descriptive link text -->
<a href="https://proply.com/signup" style="color: #007bff;">
  Click here
</a>
```

### Link Styling Requirements:
```html
<a href="#" style="color: #007bff; text-decoration: underline;">
  Links must be visually distinct from body text
</a>

<!-- Ensure links are recognizable without color alone -->
<a href="#" style="color: #007bff; text-decoration: underline; border-bottom: 1px solid #007bff;">
  Multiple visual cues for links
</a>
```

### Button vs Link Accessibility:
```html
<!-- Use buttons for actions -->
<table role="presentation">
  <tr>
    <td style="background-color: #007bff; border-radius: 4px;">
      <a href="https://proply.com/action" 
         role="button"
         style="display: inline-block; padding: 12px 24px; color: #ffffff; text-decoration: none; font-weight: bold;"
         aria-label="Start your personalized learning journey">
        Get Started
      </a>
    </td>
  </tr>
</table>
```

## Interactive Element Accessibility

### Touch Target Size
Ensure interactive elements are large enough for touch interaction:

```html
<!-- Minimum 44px x 44px touch targets -->
<td style="background-color: #007bff; border-radius: 4px; text-align: center;">
  <a href="#" 
     style="display: inline-block; padding: 14px 28px; min-height: 44px; min-width: 44px; color: #ffffff; text-decoration: none; line-height: 1.2;"
     aria-label="Subscribe to Proply newsletter">
    Subscribe
  </a>
</td>
```

### Focus Indicators
While limited in email, ensure interactive elements are visually distinct:

```html
<a href="#" 
   style="color: #007bff; text-decoration: underline; outline: 2px solid transparent; padding: 2px;"
   onFocus="this.style.outline='2px solid #007bff'">
  Focusable link
</a>
```

## ARIA Labels and Roles

### Table Roles
```html
<!-- Layout tables -->
<table role="presentation" cellpadding="0" cellspacing="0" border="0">

<!-- Data tables (rare in email) -->
<table role="table">
  <caption>Monthly Sales Data</caption>
  <thead>
    <tr>
      <th scope="col">Month</th>
      <th scope="col">Sales</th>
    </tr>
  </thead>
</table>
```

### ARIA Labels for Complex Elements:
```html
<div role="banner" aria-label="Proply email header">
  <!-- Header content -->
</div>

<div role="main" aria-label="Email content">
  <!-- Main content -->
</div>

<div role="contentinfo" aria-label="Email footer">
  <!-- Footer content -->
</div>
```

## Language and Content Accessibility

### Language Declaration
```html
<html lang="en">
  <!-- Specify the primary language -->
</html>

<!-- For multilingual content -->
<p>Welcome to Proply</p>
<p lang="es">Bienvenido a Proply</p>
```

### Clear and Simple Language
- Use common, everyday words
- Keep sentences short and clear
- Avoid jargon and technical terms
- Explain abbreviations on first use
- Use active voice when possible

### Content Structure Example:
```html
<table role="presentation">
  <tr>
    <td>
      <h1 style="margin: 0; font-size: 24px; color: #333333;">
        Welcome to Proply
      </h1>
      <p style="margin: 16px 0; font-size: 16px; line-height: 1.5; color: #333333;">
        Start your personalized learning journey today. We've made it simple to get started.
      </p>
      <p style="margin: 0 0 24px 0; font-size: 16px; line-height: 1.5; color: #333333;">
        Here's what you can do:
      </p>
      <ul style="margin: 0 0 24px 20px; padding: 0;">
        <li style="margin-bottom: 8px; color: #333333;">Complete your profile</li>
        <li style="margin-bottom: 8px; color: #333333;">Browse recommended courses</li>
        <li style="margin-bottom: 8px; color: #333333;">Start learning immediately</li>
      </ul>
    </td>
  </tr>
</table>
```

## Dark Mode Accessibility

### Maintaining Contrast in Dark Mode:
```html
<style>
  .accessible-text {
    color: #333333;
    background-color: #ffffff;
  }
  
  @media (prefers-color-scheme: dark) {
    .accessible-text {
      color: #ffffff;
      background-color: #1a1a1a;
      /* Maintains high contrast in both modes */
    }
  }
</style>
```

## Screen Reader Considerations

### Content Structure for Screen Readers:
```html
<!-- Logical reading order -->
<table role="presentation">
  <tr>
    <td>
      <!-- Skip navigation for screen readers -->
      <a href="#main-content" style="position: absolute; left: -9999px; top: -9999px;">Skip to main content</a>
      
      <!-- Header -->
      <div role="banner">
        <img src="logo.png" alt="Proply - Your Learning Platform">
      </div>
      
      <!-- Main content -->
      <div id="main-content" role="main">
        <h1>Email subject reinforced</h1>
        <!-- Content here -->
      </div>
      
      <!-- Footer -->
      <div role="contentinfo">
        <!-- Footer content -->
      </div>
    </td>
  </tr>
</table>
```

### Screen Reader Friendly Elements:
```html
<!-- Tables with proper headers -->
<table>
  <caption>Course completion rates</caption>
  <tr>
    <th scope="col">Course</th>
    <th scope="col">Completion Rate</th>
  </tr>
  <tr>
    <td>JavaScript Basics</td>
    <td>85%</td>
  </tr>
</table>

<!-- Form labels (if using forms in email) -->
<label for="email-input" style="display: block; font-weight: bold;">
  Email Address:
</label>
<input type="email" id="email-input" name="email" required>
```

## Testing for Accessibility

### Automated Testing Tools:
- WAVE (Web Accessibility Evaluation Tool)
- axe DevTools
- Lighthouse accessibility audit
- Pa11y command line tool

### Manual Testing:
1. **Keyboard navigation**: Tab through all interactive elements
2. **Screen reader testing**: Use NVDA, JAWS, or VoiceOver
3. **Color contrast**: Test with contrast analyzer tools
4. **Zoom testing**: Test at 200% zoom level
5. **Mobile accessibility**: Test with mobile screen readers

### Testing Checklist:
- [ ] All images have appropriate alt text
- [ ] Text has sufficient contrast (4.5:1 minimum)
- [ ] Links have descriptive text
- [ ] Heading structure is logical
- [ ] Interactive elements are large enough (44px minimum)
- [ ] Content is readable without images
- [ ] Email works with screen readers
- [ ] Dark mode maintains accessibility
- [ ] Language is declared properly
- [ ] Tables use proper markup

## Common Accessibility Mistakes

### Issues to Avoid:
```html
<!-- DON'T: Missing alt text -->
<img src="chart.jpg" width="300" height="200">

<!-- DO: Descriptive alt text -->
<img src="chart.jpg" alt="Revenue increased 25% from Q1 to Q2" width="300" height="200">

<!-- DON'T: Color as only indicator -->
<span style="color: red;">Error message</span>

<!-- DO: Multiple indicators -->
<span style="color: #d73027; font-weight: bold;">⚠️ Error: Please check your input</span>

<!-- DON'T: Non-descriptive links -->
<a href="#">Click here</a>

<!-- DO: Descriptive links -->
<a href="#">Download your Proply progress report</a>
```

## Email Client Accessibility Support

### Client Support Levels:

**Good Accessibility Support:**
- Apple Mail (iOS/macOS)
- Outlook (desktop versions)
- Thunderbird

**Limited Support:**
- Gmail (web/mobile)
- Yahoo Mail
- Outlook.com

**Best Practices for All Clients:**
- Use semantic HTML structure
- Maintain high contrast
- Include descriptive alt text
- Use large, tappable buttons
- Ensure logical content flow

## Legal and Compliance Considerations

### Standards to Follow:
- **WCAG 2.1 AA**: Web Content Accessibility Guidelines
- **ADA Compliance**: Americans with Disabilities Act
- **Section 508**: U.S. Federal accessibility standard
- **EN 301 549**: European accessibility standard

### Documentation:
Maintain records of:
- Accessibility testing results
- Remediation efforts
- User feedback and improvements
- Compliance verification

Following this accessibility guide ensures Proply's email templates are usable by all recipients, regardless of their abilities or assistive technology needs.