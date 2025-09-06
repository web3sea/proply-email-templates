# Proply Email Templates

This repository contains email templates for Proply's customer engagement sequences. The project is structured to ensure maximum email client compatibility, accessibility, and brand consistency.

## Project Structure

```
proply-email-templates/
├── README.md                          # This file
├── docs/                             # Documentation and guidelines
│   ├── CONTEXT.md                    # Proply business context
│   ├── BRAND_GUIDELINES.md          # Brand standards and guidelines
│   ├── GMAIL_COMPATIBILITY_GUIDE.md  # Gmail-specific requirements
│   ├── RESPONSIVENESS_GUIDE.md       # Mobile/responsive design standards
│   ├── DARK_MODE_GUIDE.md           # Dark mode implementation guide
│   └── ACCESSIBILITY_GUIDE.md        # Accessibility compliance standards
├── templates/                        # Email template files
│   ├── sequence_01_welcome.html     # Welcome email template
│   ├── sequence_02_value.html       # Value proposition email
│   └── sequence_03_cta.html         # Call-to-action email
├── assets/                          # Images and brand resources
│   ├── images/                      # Email images
│   └── logos/                       # Brand logos and assets
└── testing/                         # Testing utilities and checklists
    ├── test_checklist.md           # QA validation checklist
    └── preview_templates/          # Browser preview files
```

## Email Sequence Overview

This project implements a 3-email sequence designed to:

1. **Welcome Email**: Introduce Proply and establish connection
2. **Value Email**: Demonstrate benefits and value proposition
3. **CTA Email**: Drive specific action or conversion

## Development Standards

All email templates follow strict standards for:
- **Gmail Compatibility**: Inline CSS, table-based layouts
- **Mobile Responsiveness**: Single-column designs that adapt to all screen sizes
- **Dark Mode Support**: Proper implementation with fallbacks
- **Accessibility**: WCAG 2.1 AA compliance
- **Brand Consistency**: Cohesive visual identity

## Getting Started

1. Review all documentation in the `docs/` folder
2. Understand Proply's context and brand guidelines
3. Follow technical standards when developing templates
4. Use the testing checklist before finalizing templates

## Template Development Workflow

1. Read CONTEXT.md for business understanding
2. Follow BRAND_GUIDELINES.md for visual consistency
3. Implement using technical guides (Gmail, responsiveness, etc.)
4. Validate using testing/test_checklist.md
5. Test across multiple email clients

For questions or updates, refer to the comprehensive documentation in the `docs/` folder.