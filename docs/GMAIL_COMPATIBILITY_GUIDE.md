# Gmail Compatibility Guide

## Overview

Gmail has specific requirements and limitations that must be addressed to ensure proper email rendering. This guide outlines critical Gmail compatibility requirements for Proply email templates.

## CSS Requirements

### Inline Styles Only
Gmail strips `<style>` blocks and external stylesheets. All CSS must be inline.

**✅ Correct:**
```html
<td style="background-color: #ffffff; padding: 20px; font-family: Arial, sans-serif;">
```

**❌ Incorrect:**
```html
<style>
  .header { background-color: #ffffff; }
</style>
<td class="header">
```

### Supported CSS Properties
Gmail supports limited CSS properties. Use only these safe properties:

**Typography:**
- `font-family`, `font-size`, `font-weight`
- `color`, `text-align`, `line-height`
- `text-decoration`

**Layout:**
- `width`, `height`
- `padding`, `margin` (limited support)
- `background-color`
- `border`, `border-radius` (limited)

**Display:**
- `display: block`, `display: inline-block`
- `vertical-align`

### Avoid These CSS Properties
- `float`
- `position`
- `z-index`
- `background-image` (use VML for Outlook)
- `box-shadow`
- `transform`

## HTML Structure Requirements

### Table-Based Layout
Use tables with `role="presentation"` for layout structure:

```html
<table role="presentation" cellpadding="0" cellspacing="0" border="0" width="100%">
  <tr>
    <td align="center">
      <!-- Content here -->
    </td>
  </tr>
</table>
```

### Email DOCTYPE
Always use this DOCTYPE:
```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

### Meta Tags
Include these essential meta tags:
```html
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="x-apple-disable-message-reformatting">
```

## Font Requirements

### Email-Safe Font Stack
Always use email-safe fonts with fallbacks:

```css
/* Headers */
font-family: 'Trebuchet MS', Arial, Helvetica, sans-serif;

/* Body text */
font-family: Arial, Helvetica, sans-serif;

/* Fallback stack */
font-family: Arial, Helvetica, 'Lucida Sans Unicode', sans-serif;
```

### Font Size Guidelines
- Minimum body text: 14px
- Headlines: 18px - 24px
- Small text/disclaimers: 12px minimum

## Button Implementation

### Bulletproof Button Structure
Use nested tables for reliable button rendering:

```html
<table role="presentation" cellspacing="0" cellpadding="0" border="0">
  <tr>
    <td style="border-radius: 4px; background-color: #007bff;">
      <a href="#" style="display: inline-block; padding: 12px 24px; font-family: Arial, sans-serif; font-size: 16px; color: #ffffff; text-decoration: none; border-radius: 4px;">
        Call to Action
      </a>
    </td>
  </tr>
</table>
```

### Button Best Practices
- Use `display: inline-block` on the link
- Include `text-decoration: none`
- Minimum 44px height for mobile
- High contrast colors
- Fallback background color

## Image Handling

### Image Requirements
- Use PNG or JPG formats
- Include `alt` attributes for all images
- Set explicit `width` and `height`
- Use `display: block` to prevent spacing issues

```html
<img src="https://example.com/image.png" 
     alt="Descriptive alt text" 
     width="200" 
     height="100" 
     style="display: block; border: 0;">
```

### Background Images
Gmail blocks background images. Use solid background colors as fallbacks:

```html
<td style="background-color: #f0f0f0;">
  <!-- Content here -->
</td>
```

## Link Handling

### Link Best Practices
- Use full absolute URLs (https://)
- Include `target="_blank"` for external links
- Add `rel="noopener"` for security

```html
<a href="https://proply.com" 
   target="_blank" 
   rel="noopener" 
   style="color: #007bff; text-decoration: underline;">
  Visit Proply
</a>
```

## Gmail-Specific Issues

### Common Problems and Solutions

**Problem: Extra spacing around images**
```html
<!-- Solution: Use display: block -->
<img src="image.jpg" style="display: block;" alt="Image">
```

**Problem: Unwanted blue links**
```html
<!-- Solution: Explicit link styling -->
<a href="#" style="color: #333333; text-decoration: none;">Text</a>
```

**Problem: Table cell spacing**
```html
<!-- Solution: Use cellpadding="0" cellspacing="0" -->
<table role="presentation" cellpadding="0" cellspacing="0" border="0">
```

## Testing Requirements

### Gmail Testing Checklist
- [ ] Test in Gmail web interface
- [ ] Test in Gmail mobile app (iOS/Android)
- [ ] Test with images blocked
- [ ] Test in different Gmail themes
- [ ] Verify link functionality
- [ ] Check mobile responsiveness
- [ ] Validate HTML structure

### Testing Tools
- Gmail's HTML email testing
- Litmus Gmail previews
- Email on Acid Gmail tests
- Send actual test emails to Gmail accounts

## Mobile Considerations

### Gmail Mobile App
- Single column layouts work best
- Minimum 14px font size
- Touch-friendly button sizes (44px minimum)
- Simplified navigation

### Responsive Design
Use media queries that Gmail mobile supports:
```html
<style type="text/css">
  @media screen and (max-width: 600px) {
    .mobile-width { width: 100% !important; }
    .mobile-padding { padding: 10px !important; }
  }
</style>
```

## Validation

### HTML Validation
- Use W3C HTML validator
- Check for proper table structure
- Verify all tags are properly closed
- Ensure XHTML compliance

### Final Gmail Test
Before deploying any email template:
1. Send test email to multiple Gmail accounts
2. Check rendering in Gmail web and mobile
3. Verify all links work correctly
4. Confirm images display properly
5. Test with images blocked scenario

Following these guidelines ensures maximum compatibility with Gmail's rendering engine and provides the best user experience for Gmail recipients.