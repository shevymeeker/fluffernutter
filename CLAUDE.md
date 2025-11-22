# CLAUDE.md - AI Assistant Guide for Fluffernutter Repository

**Last Updated:** 2025-11-22
**Repository:** shevymeeker/fluffernutter
**Project:** Clutter Busters Website & Reusable Business Template

---

## 🎯 Project Overview

This repository contains a **professional service business website** built as a single-page application (SPA) with a dual purpose:

1. **Live Production Site**: `index.html` - Active website for Clutter Busters LLC
2. **Reusable Template**: `template-index.html` - Customizable template for other service businesses

### Business Context
- **Client:** Clutter Busters LLC (Junk Removal & Property Services)
- **Owner:** Theron Allen
- **Location:** Owensboro, KY
- **Services:** Junk removal, demolition, landscaping, moving, plumbing, cleanouts
- **Contact:** (270) 315-2503, Tallen.Clutter@gmail.com

---

## 📁 Repository Structure

```
/fluffernutter/
├── index.html                    # PRODUCTION - Live Clutter Busters site
├── thank-you.html                # PRODUCTION - Form success page
├── template-index.html           # TEMPLATE - Reusable for other businesses
├── template-thank-you.html       # TEMPLATE - Success page template
├── manifest.json                 # PWA configuration
├── mascot.png                    # Main logo (8-bit style, 1471KB)
├── mascotold.png                 # Previous version (943KB)
├── ot.png                        # Alternative logo (843KB)
├── favicon.png                   # Browser icon (881KB)
│
├── DOCUMENTATION FILES
├── README.md                     # Basic repo description
├── TEMPLATE-README.md            # Complete template documentation
├── TEMPLATE-SETUP.md             # Detailed setup instructions
├── TEMPLATE-PACKAGE-CONTENTS.md  # Template package overview
├── TEMPLATE-CONFIG-GUIDE.txt     # Search/replace configuration guide
├── QUICK-START-CHECKLIST.md      # Step-by-step customization checklist
├── PHOTO-QUOTE-SETUP.md          # Form & Netlify setup guide
└── SERVICE-MEDIA-GUIDE.md        # Guide for adding photos/videos
```

---

## 🏗️ Architecture & Technical Stack

### Technology Stack
- **HTML5**: Semantic markup, Schema.org structured data
- **CSS3**: Custom properties (CSS variables), Grid, Flexbox, animations
- **Vanilla JavaScript**: No frameworks, ~200 lines of custom JS
- **Netlify Forms**: Form handling with file uploads
- **PWA**: Progressive Web App manifest, installable on mobile

### Key Technical Characteristics
1. **Single File Architecture**: All HTML/CSS/JS in one file (~1,700 lines)
2. **No Build Process**: Direct deployment, no compilation needed
3. **Mobile-First Design**: Responsive from 320px to 4K displays
4. **Self-Contained**: No external dependencies except Google Fonts
5. **Form Integration**: Netlify Forms with multi-file upload support

### File Size & Performance
- `index.html`: ~56KB (highly optimized)
- Total page weight: ~3.3MB (mostly images)
- Images should be optimized for production

---

## 🎨 Design System

### Color Palette (CSS Variables)
```css
--primary: #0f2b46        /* Navy blue - primary brand */
--primary-light: #1a3f63  /* Lighter navy */
--primary-dark: #081828   /* Darker navy */
--accent: #e63946         /* Red - calls to action */
--accent-light: #ff5464   /* Lighter red */
--accent-dark: #d62839    /* Darker red */
--light: #f8f9fa          /* Light background */
--white: #ffffff          /* Pure white */
--dark: #1a1a1a           /* Text color */
--gray: #6c757d           /* Secondary text */
--gray-light: #e9ecef     /* Borders/dividers */
--success: #10b981        /* Success states */
```

### Typography
- **Font Family**: Inter (Google Fonts)
- **Weights**: 400, 500, 600, 700, 800, 900
- **Headings**: 900 weight, negative letter-spacing
- **Body**: 400-500 weight, 1.6 line-height

### Layout System
- **Max Width**: 1400px for content containers
- **Breakpoint**: 768px (mobile/desktop)
- **Grid**: CSS Grid with auto-fit for responsive services
- **Spacing**: Consistent rem-based spacing

---

## 🔧 Major Components

### 1. Navigation Bar
- Fixed position, backdrop blur effect
- Smooth scroll anchor links
- Mobile hamburger menu (not yet implemented)
- CTA button in nav

### 2. Hero Section
- Gradient background with overlay effects
- Animated mascot (float animation)
- Primary CTA button (call to action)
- Gradient text effect on title

### 3. Image Carousel
- Auto-rotating (4s intervals)
- Dot navigation
- Currently displays placeholders
- Ready for before/after photos

### 4. Quote Section (Primary Conversion Point)
**Key Feature**: Clickable mascot CTA that opens modal form
- Photo upload form (multiple files)
- Name, phone, email fields
- Netlify Forms integration
- Redirects to thank-you.html on success

### 5. Services Grid
- 8 service cards with hover effects
- Each opens a modal on click
- Modal supports photos, videos, or placeholder
- Dynamic content via JavaScript object

### 6. FAQ Accordion
- 6 questions (expandable/collapsible)
- One active at a time
- Smooth animations
- Icon rotation on expand

### 7. Contact Section
- Split layout: info + form
- Gradient background
- Contact form (separate from quote form)
- Email/phone/location display

### 8. Footer
- Multi-column layout
- Business information
- Quick links
- License/legal info placeholders

### 9. Modals (2 types)
- **Service Modal**: Displays service details, media
- **Quote Modal**: Photo upload form
- Click outside or ESC to close
- Prevent body scroll when open

---

## 📋 Forms & Data Handling

### Photo Quote Form (`photo-quote`)
**Location**: Modal triggered by mascot click
**Method**: POST to Netlify Forms
**Encoding**: `multipart/form-data`
**Redirect**: `/thank-you`

**Fields:**
- `name` (text, required)
- `phone` (tel, optional)
- `email` (email, optional)
- `notes` (textarea, optional)
- `photos[]` (file, multiple, required)

**Note**: Either phone or email should be provided (not enforced in HTML)

### Contact Form (`contact`)
**Location**: Contact section
**Method**: POST to Netlify Forms

**Fields:**
- `name` (text, required)
- `phone` (tel, required)
- `email` (email, optional)
- `message` (textarea, required)

### Netlify Forms Configuration
- Both forms have `data-netlify="true"` attribute
- Hidden `form-name` input for Netlify detection
- File upload limit: 10MB per file (Netlify free tier)
- Email notifications configured in Netlify dashboard

---

## 🎯 Key User Workflows

### Primary Conversion Flow
1. User lands on site
2. Scrolls to "Get Your FREE Quote" section
3. Clicks mascot image with overlay text
4. Modal opens with photo upload form
5. User fills name, contact info, uploads photos
6. Submits form
7. Redirects to thank-you.html
8. Owner receives email with photos

### Alternative Contact Flows
- Click "Call Now" → Opens phone dialer
- Click "Text Me" → Opens SMS with pre-filled message
- Fill contact form → Email notification
- Click service card → View details modal → Call/text from modal

---

## 🔄 Development Workflows

### Working with Production Site (`index.html`)
**IMPORTANT**: This is the LIVE site. Changes affect production immediately upon deployment.

**Before Making Changes:**
1. Always read the file first
2. Understand current state
3. Test locally if possible
4. Make targeted, minimal changes

**Common Tasks:**
- Update phone number: Search `2703152503` and `(270) 315-2503`
- Update email: Search `Tallen.Clutter@gmail.com`
- Change colors: Edit CSS variables in `:root` selector
- Add service: Copy service card HTML + add to `serviceData` object
- Update FAQ: Modify FAQ HTML structure

### Working with Template (`template-index.html`)
**Purpose**: Create new sites for other businesses

**Template Customization Process:**
1. Copy `template-index.html` to new folder
2. Rename to `index.html`
3. Follow `TEMPLATE-CONFIG-GUIDE.txt` for search/replace
4. Update CSS variables for brand colors
5. Replace `mascot.png` with new logo
6. Edit services array in JavaScript
7. Update FAQ content
8. Deploy to Netlify

**DO NOT**: Edit `template-index.html` directly when making changes for Clutter Busters. Edit `index.html` instead.

---

## 🚀 Deployment & Hosting

### Platform: Netlify
**Site URL**: (To be determined - check Netlify dashboard)

### Deployment Process
1. **From GitHub**:
   - Netlify auto-deploys on push to main branch
   - No build command needed
   - Publish directory: `/`

2. **Manual**:
   - Drag folder to netlify.com/drop
   - Wait ~30 seconds for deployment

### Netlify Configuration
```
Base directory:    [empty]
Build command:     [empty]
Publish directory: /
```

### Post-Deployment Steps
1. Enable Netlify Forms in dashboard
2. Configure email notifications
3. Test photo upload form
4. Verify form submissions appear in dashboard

---

## 🎨 Customization Guide for AI Assistants

### When Customizing Colors
1. Locate `:root` selector (around line 42-58)
2. Modify `--primary` and `--accent` variables
3. Other color variants auto-calculate (don't change)
4. Test contrast for accessibility

### When Adding Services
**HTML Structure** (lines ~1310-1334):
```html
<div class="service-card" data-service="service-id" onclick="openServiceModal(this)">
    <h3>🔧 Service Name</h3>
</div>
```

**JavaScript Data** (lines ~1659-1708):
```javascript
serviceData['service-id'] = {
    title: '🔧 Service Name',
    description: 'Service description',
    photos: [],  // Optional: ['path/to/photo.jpg']
    video: null  // Optional: 'path/to/video.mp4'
};
```

### When Modifying Forms
1. Keep `data-netlify="true"` attribute
2. Keep hidden `form-name` input
3. Maintain `name` attributes on inputs
4. Update `action` attribute if changing redirect
5. Test after deployment (forms don't work locally)

### When Adding Images
**Carousel Images** (lines ~1258-1272):
```html
<div class="carousel-slide" style="background-image: url('path/to/image.jpg')"></div>
```

**Service Photos**:
- Add to `serviceData` object in JavaScript
- Format: `photos: ['img1.jpg', 'img2.jpg']`

**Logo/Mascot**:
- Replace `mascot.png` file (500x500px+ recommended)
- Keep transparent background PNG format

---

## 🐛 Common Issues & Solutions

### Forms Not Working
**Symptoms**: Form submits but nothing happens
**Cause**: Netlify Forms not enabled or detected
**Solution**:
1. Ensure deployed to Netlify (not localhost)
2. Wait 5 minutes after first deployment
3. Submit test form to trigger detection
4. Check Netlify dashboard → Forms

### Photos Not Uploading on Mobile
**Symptoms**: Can't select multiple photos or access gallery
**Cause**: Previous `capture="environment"` attribute
**Solution**: Already fixed - removed camera-only restriction

### Logo Not Showing
**Symptoms**: Broken image icon
**Cause**: File path or name mismatch
**Solution**:
1. Verify file is named exactly `mascot.png`
2. Check file is in same directory as index.html
3. Check browser console for 404 errors

### Colors Not Changing
**Symptoms**: CSS edits don't appear
**Cause**: Browser cache
**Solution**:
1. Hard refresh (Ctrl+Shift+R / Cmd+Shift+R)
2. Clear browser cache
3. Verify CSS variables in `:root` selector

---

## 📝 Code Conventions

### CSS
- Use CSS custom properties (variables) for colors
- Mobile-first media queries
- BEM-like naming (component-element)
- Animations prefer `transform` over position
- Use `rem` for spacing, `px` for borders

### JavaScript
- No external libraries or frameworks
- Vanilla ES5+ syntax (widely compatible)
- Event listeners on DOMContentLoaded equivalents
- Functions in global scope (small project)
- Constants in UPPER_CASE (if needed)

### HTML
- Semantic HTML5 elements
- ARIA attributes where needed
- Schema.org structured data for SEO
- Comments to mark major sections
- Inline CSS/JS in single file

---

## 🔒 Important Files - DO NOT DELETE

### Critical Production Files
- `index.html` - LIVE WEBSITE
- `thank-you.html` - Form success page
- `manifest.json` - PWA configuration
- `mascot.png` - Primary logo

### Critical Template Files
- `template-index.html` - Reusable template
- `template-thank-you.html` - Template success page
- All `TEMPLATE-*.md` files - Documentation

### Safe to Modify
- Documentation files (for updates)
- Old mascot images (mascotold.png, ot.png)
- favicon.png (can be regenerated)

---

## 🎯 Project Goals & Constraints

### Goals
1. Professional appearance for service business
2. Mobile-first, responsive design
3. Easy photo quote submission for customers
4. Simple customization for multiple businesses
5. No-code deployment process
6. Low maintenance, high reliability

### Constraints
1. Single file architecture (no build process)
2. Netlify-specific form handling
3. No backend server/database
4. Image optimization handled manually
5. Limited to static content (no dynamic data)

### Future Considerations
- Add testimonials section
- Implement mobile navigation menu
- Add real before/after photos to carousel
- Add Google Analytics/tracking
- Consider adding blog section
- Add more service detail photos

---

## 🚨 Critical Warnings for AI Assistants

### NEVER Do These Things
1. ❌ Delete `index.html` or `thank-you.html`
2. ❌ Remove `data-netlify="true"` from forms
3. ❌ Change form `name` attributes without updating Netlify
4. ❌ Break the single-file architecture (keep CSS/JS inline)
5. ❌ Remove Schema.org structured data
6. ❌ Change phone/email without explicit user request
7. ❌ Edit template files when user means production files

### ALWAYS Do These Things
1. ✅ Read files before editing
2. ✅ Preserve existing functionality when adding features
3. ✅ Test forms after deployment changes
4. ✅ Maintain mobile responsiveness
5. ✅ Keep accessibility in mind
6. ✅ Update documentation when making structural changes
7. ✅ Ask for clarification: production vs. template

### When in Doubt
- **Production changes** → Edit `index.html`
- **Template changes** → Edit `template-index.html`
- **Unclear** → Ask user which file to edit
- **Breaking change** → Warn user before proceeding
- **Multiple files affected** → List all files before editing

---

## 📞 Business Contact Information

**IMPORTANT**: These are real business details. Always verify before changing.

### Current Production Values
- **Business Name**: Clutter Busters LLC
- **Phone**: (270) 315-2503
- **SMS**: 2703152503
- **Email**: Tallen.Clutter@gmail.com
- **Owner**: Theron Allen
- **City**: Owensboro
- **State**: KY
- **License**: KY-CB-2025-001 (placeholder - needs update)
- **EIN**: XX-XXXXXXX (placeholder - needs update)

**Before modifying contact info**:
1. Confirm with user
2. Update ALL instances (use search/replace)
3. Test all `tel:` and `mailto:` links
4. Verify SMS links work correctly

---

## 🔍 Search/Replace Patterns

### For Template Customization
When helping users customize the template, use these search patterns:

```
Business Name Variations:
- "Clutter Busters" → [New Business Name]
- "CLUTTER BUSTERS" → [NEW BUSINESS NAME]
- "ClutterBusters" → [NewBusinessName]

Contact Info:
- "(270) 315-2503" → [New Phone Formatted]
- "2703152503" → [New Phone Raw]
- "Tallen.Clutter@gmail.com" → [New Email]

Owner:
- "Theron Allen" → [New Owner Name]
- "Theron" → [New First Name]

Location:
- "Owensboro" → [New City]
- ", KY" → [, New State]
- "KY" → [New State Code]

Tagline:
- "Junk Removal & Property Services" → [New Tagline]
```

---

## 📊 Analytics & Monitoring

### Current Setup
- No analytics currently installed
- Netlify provides basic traffic stats
- Form submissions tracked in Netlify dashboard

### Recommended Additions
- Google Analytics 4
- Google Search Console
- Facebook Pixel (if using ads)
- Hotjar or similar (heatmaps)

**How to Add Google Analytics**:
1. Get GA4 tracking ID
2. Add script to `<head>` section
3. Test with GA debugger

---

## 🎓 Learning Resources

### For Understanding This Codebase
- Netlify Forms Docs: [docs.netlify.com/forms](https://docs.netlify.com/forms/)
- CSS Grid Guide: [css-tricks.com/snippets/css/complete-guide-grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- Schema.org: [schema.org/LocalBusiness](https://schema.org/LocalBusiness)

### For Customization
- Google Fonts: [fonts.google.com](https://fonts.google.com)
- Color Palettes: [coolors.co](https://coolors.co)
- Emoji Reference: [emojipedia.org](https://emojipedia.org)

---

## 🏁 Quick Reference for Common Tasks

### Change Business Name
```bash
# In template-index.html or index.html
Find: "Clutter Busters"
Replace: "New Business Name"
```

### Change Colors
```css
/* In <style> section, :root selector */
--primary: #YourColor;
--accent: #YourColor;
```

### Add New Service
```html
<!-- 1. Add card in HTML (around line 1310) -->
<div class="service-card" data-service="new-service" onclick="openServiceModal(this)">
    <h3>🔧 New Service</h3>
</div>
```
```javascript
// 2. Add data in JavaScript (around line 1659)
'new-service': {
    title: '🔧 New Service',
    description: 'Service description',
    photos: [],
    video: null
}
```

### Update Phone Number
```bash
# Update all instances
Find: "(270) 315-2503"
Replace: "Your formatted number"

Find: "2703152503"
Replace: "Your raw number"

# Update SMS links
Find: "sms:2703152503"
Replace: "sms:YourNumber"

# Update tel links
Find: "tel:2703152503"
Replace: "tel:YourNumber"
```

### Deploy to Netlify
```bash
# If using git
git add .
git commit -m "Update website"
git push origin main

# Netlify auto-deploys
# Wait ~30 seconds
# Check deployment in Netlify dashboard
```

---

## 📅 Recent Changes & History

### Recent Commits (from git log)
- `26710c7` - Add files via upload
- `fd2c9b9` - Rename Mascot.png to ot.png
- `74fd8a1` - Add template package contents overview
- `4409abd` - Add comprehensive website template package
- `2481835` - Replace main page form with clickable mascot CTA and modal
- `0c06359` - Fix photo quote form - gallery access and multiple photos
- `f96e8c2` - Premium visual redesign - professional appearance upgrade

### Major Features Added
1. Clickable mascot CTA with modal form
2. Multiple photo upload capability
3. Mobile gallery access (removed camera-only restriction)
4. Template package with documentation
5. Premium visual design with gradients and animations
6. Service modal system
7. FAQ accordion

---

## 🤝 Collaboration Guidelines

### When Working on This Project
1. **Understand the dual purpose**: Production site + Template
2. **Ask which file to edit**: Always clarify with user
3. **Test forms on Netlify**: They don't work locally
4. **Preserve mobile-first design**: Test responsive breakpoints
5. **Document changes**: Update this CLAUDE.md if structure changes
6. **Follow existing patterns**: Match current code style
7. **Think about reusability**: Changes should work for template too

### Communication with User
- Confirm file before editing (production vs template)
- Warn about breaking changes
- Explain form limitations (Netlify-specific)
- Suggest testing after deployment
- Ask about business info before changing

---

## ✅ Pre-Deployment Checklist

Before deploying changes:
- [ ] All contact info is correct
- [ ] Forms have `data-netlify="true"`
- [ ] Form `name` attributes match Netlify config
- [ ] Images are optimized (under 500KB each if possible)
- [ ] Mobile responsive (test at 375px width)
- [ ] All links work (tel:, mailto:, sms:, anchors)
- [ ] No broken image references
- [ ] CSS variables properly set
- [ ] JavaScript has no syntax errors (check console)
- [ ] README/docs updated if needed

---

## 🎉 Success Metrics

### What Good Looks Like
- Fast page load (< 3 seconds)
- Mobile-friendly (Google test passes)
- Forms submit successfully
- Photos upload without issues
- All CTAs work (call, text, email)
- Professional appearance
- Easy to customize for new businesses

---

**End of CLAUDE.md**

This document should be updated whenever:
- Project structure changes
- New features are added
- Forms/APIs change
- Deployment process changes
- Important files are added/removed

**Questions?** Read the other documentation files in this repository.
