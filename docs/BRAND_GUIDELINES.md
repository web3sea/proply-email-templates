# Proply Brand Guidelines

## Brand Identity Overview

Proply is a modern AI-powered personalized learning platform that combines technology with human-centered design to create engaging educational experiences. Our brand reflects innovation, trust, accessibility, and growth through a clean, professional, yet approachable visual identity.

## Color Palette

### Primary Colors
- **Primary Brand Color**: `#0A9ADD` - Bright blue for main CTAs, headers, key accents
- **Secondary Brand Color**: `#164344` - Deep teal for supporting elements, secondary CTAs
- **Light Accent**: `#D2EEFB` - Soft blue for highlights, backgrounds, gentle emphasis

### Supporting Colors
- **Success/Confirmation**: `#BBF7D0` - Soft green for success states, positive feedback
- **Success Background**: `#EEFDF4` - Very light green for success sections, confirmations
- **Information/Neutral**: `#F8FAFC` - Near white for clean backgrounds, content areas
- **Secondary Text**: `#727D8C` - Medium gray for secondary text, subtle elements

### Color Usage Guidelines
- **Primary Blue (#0A9ADD)**: Use for primary CTAs, links, key interactive elements
- **Deep Teal (#164344)**: Use for headlines, important text, secondary buttons
- **Light Blue (#D2EEFB)**: Use for section backgrounds, hover states, gentle highlights
- **Success Green (#BBF7D0)**: Use for success messages, completed states, positive indicators
- **Light Gray (#F8FAFC)**: Use for main backgrounds, content containers
- **Medium Gray (#727D8C)**: Use for secondary text, descriptions, subtle borders

### Email-Safe Color Considerations
- Ensure 4.5:1 minimum contrast ratio for accessibility
- Test colors across different email clients
- Provide fallback colors for dark mode
- Consider color-blind accessibility

## Typography

### Email-Safe Font Stack
**Primary Font (Headers/Headlines)**
```css
font-family: 'Trebuchet MS', Arial, Helvetica, sans-serif;
```

**Secondary Font (Body Text)**
```css
font-family: Arial, Helvetica, sans-serif;
```

**Fallback Font Stack**
```css
font-family: Arial, Helvetica, 'Lucida Sans Unicode', 'Lucida Grande', sans-serif;
```

### Typography Hierarchy
- **H1 Headlines**: 28-32px, bold, color: #164344 (Deep Teal) or #0A9ADD (Primary Blue)
- **H2 Subheadings**: 22-24px, bold, color: #164344 (Deep Teal)
- **H3 Subheadings**: 18-20px, bold, color: #164344 (Deep Teal)
- **Body Text**: 16px, regular, line-height: 1.5-1.6, color: #164344
- **Secondary Text**: 14-16px, regular, color: #727D8C (Medium Gray)
- **Small Text**: 12-14px, regular, color: #727D8C (for disclaimers, footers)
- **Button Text**: 16-18px, bold, color: #FFFFFF (on colored buttons)

## Logo Usage

### Logo Specifications
- **Primary logo**: Clean, modern wordmark "Proply" in sans-serif font
- **File format**: PNG with transparent background for emails
- **Minimum width**: 150px for email headers, 120px minimum in any context
- **Clear space**: Minimum padding equal to the height of the "P" in Proply on all sides
- **Light backgrounds**: Use #164344 (Deep Teal) or #0A9ADD (Primary Blue)
- **Dark backgrounds**: Use #FFFFFF (White) or #D2EEFB (Light Blue)

### Email Logo Guidelines
- Use PNG format with transparent background
- Maximum width: 200px for email headers
- Ensure logo scales properly on mobile devices
- Include alt text: "Proply [logo description]"
- Host logos on reliable CDN with HTTPS

## Button Design Standards

### Primary Call-to-Action Buttons
```css
/* Primary CTA Button Styles */
background-color: #0A9ADD;
color: #FFFFFF;
font-family: Arial, sans-serif;
font-size: 16-18px;
font-weight: bold;
padding: 14px 28px;
border-radius: 6px;
text-decoration: none;
display: inline-block;
border: none;
```

### Secondary Buttons
```css
/* Secondary Button Styles */
background-color: transparent;
color: #0A9ADD;
border: 2px solid #0A9ADD;
font-family: Arial, sans-serif;
font-size: 14-16px;
font-weight: bold;
padding: 12px 24px;
border-radius: 6px;
text-decoration: none;
display: inline-block;
```

### Alternative CTA (Deep Teal)
```css
/* Alternative Primary CTA */
background-color: #164344;
color: #FFFFFF;
/* Same padding and typography as primary */
```

### Button Guidelines
- Minimum 44px height for mobile accessibility
- Use bulletproof button structure (nested tables)
- Include fallback colors for Outlook
- Ensure sufficient contrast ratios

## Visual Elements

### Layout Principles
- **Content width**: 600px maximum for email templates
- **Margin standards**: 30px horizontal padding on desktop, 15px on mobile
- **Section spacing**: 40px between major sections, 24px between related elements
- **Single-column layouts**: Stack naturally on mobile devices
- **Clean, minimalist design**: Ample white space using #F8FAFC backgrounds

### Image Guidelines
- **Maximum file size**: 100KB per image, 500KB total email size
- **Format**: PNG for graphics with transparency, JPG for photos
- **Aspect ratios**: 16:9 for hero images, 1:1 for profile/icon images
- **Alt text**: Descriptive and meaningful for all images
- **Fallback colors**: Use #D2EEFB for missing images
- **Hosting**: Reliable CDN with HTTPS required

## Brand Voice & Tone

### Voice Characteristics
- **Professional level**: Conversational yet authoritative
- **Personality traits**: Friendly, innovative, supportive, trustworthy
- **Communication style**: Clear, encouraging, solution-focused
- **Technical complexity**: Accessible to all education levels, avoid jargon

### Tone Guidelines
- **Email greetings**: Warm and welcoming ("Welcome to Proply!", "Hi [Name]!")
- **Call-to-action language**: Action-oriented and benefit-focused ("Start Learning Now", "Discover Your Path")
- **Messaging style**: Encouraging growth, emphasizing personalization
- **Urgency language**: Use sparingly, focus on opportunity rather than scarcity

## Dark Mode Specifications

### Dark Mode Color Palette
- **Dark background**: `#164344` (Deep Teal) or `#1a1a1a` (Very Dark Gray)
- **Dark content background**: `#2d2d2d` (Dark Gray)
- **Dark mode text**: `#FFFFFF` (White) for primary text
- **Dark mode secondary text**: `#D2EEFB` (Light Blue) for secondary text
- **Dark mode accents**: `#0A9ADD` (Primary Blue) maintains visibility
- **Success elements**: `#BBF7D0` (Success Green) remains effective

### Implementation Requirements
- CSS media queries: `@media (prefers-color-scheme: dark)`
- Meta tags for dark mode support
- Image alternatives for dark backgrounds
- Fallback strategies for unsupported clients

## Accessibility Requirements

### Color Contrast Standards
- Text contrast ratio: minimum 4.5:1
- Large text contrast ratio: minimum 3:1
- Interactive element contrast requirements

### Additional Accessibility Features
- Descriptive alt text for all images
- Semantic HTML structure
- Readable font sizes (minimum 14px)
- Clear focus indicators for interactive elements

---

## Email Template Application

### Color Mapping for Email Templates
- **Primary CTA buttons**: `#0A9ADD` background, `#FFFFFF` text
- **Secondary CTAs**: `transparent` background, `#0A9ADD` text and border
- **Headlines**: `#164344` (Deep Teal)
- **Body text**: `#164344` (Deep Teal) 
- **Secondary text**: `#727D8C` (Medium Gray)
- **Success elements**: `#BBF7D0` backgrounds with `#164344` text
- **Section backgrounds**: `#F8FAFC` or `#D2EEFB` for variety
- **Footer backgrounds**: `#F8FAFC`

### Accessibility Compliance
- All color combinations meet WCAG 2.1 AA standards (4.5:1 contrast ratio minimum)
- Touch targets minimum 44px for mobile accessibility
- Semantic HTML structure with proper heading hierarchy
- Descriptive alt text for all images

### Implementation Checklist
✅ **Brand colors defined with specific hex codes**
✅ **Typography hierarchy established**
✅ **Button styles specified**
✅ **Dark mode color palette created**
✅ **Voice and tone guidelines established**
✅ **Layout principles defined**
✅ **Accessibility requirements documented**

This comprehensive brand guideline document serves as the definitive source for all Proply email template design and messaging decisions.