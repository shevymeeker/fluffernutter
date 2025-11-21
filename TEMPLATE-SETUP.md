# 🎨 Business Website Template - Setup Guide

This template is based on the Clutter Busters website and can be easily customized for any service-based business.

## 📋 Quick Setup Checklist

- [ ] Edit `template-index.html` configuration section (lines 40-120)
- [ ] Replace `logo.png` with your business logo/mascot
- [ ] Update `manifest.json` with your business name
- [ ] Customize `template-thank-you.html`
- [ ] Deploy to Netlify
- [ ] Enable Netlify Forms
- [ ] Test the photo quote form

---

## 🎯 Step 1: Edit Configuration (5 minutes)

Open `template-index.html` and find the **TEMPLATE CONFIGURATION** section at the top of the `<style>` tag (around line 40).

### A. Edit Colors
```css
/* ===== TEMPLATE: EDIT YOUR COLORS HERE ===== */
--primary: #0f2b46;        /* Main brand color (dark blue) */
--accent: #e63946;         /* Accent color (red) */
```

**Color Examples:**
- **Blue Business**: `--primary: #1e40af;` `--accent: #3b82f6;`
- **Green Business**: `--primary: #065f46;` `--accent: #10b981;`
- **Purple Business**: `--primary: #581c87;` `--accent: #a855f7;`
- **Orange Business**: `--primary: #9a3412;` `--accent: #f97316;`

### B. Edit Business Information

Search for `/* ===== TEMPLATE: BUSINESS INFO =====` and update:

```javascript
const BUSINESS_CONFIG = {
    name: 'Your Business Name',
    tagline: 'Your Service Description',
    phone: '(555) 123-4567',
    phoneRaw: '5551234567',
    email: 'you@business.com',
    city: 'Your City',
    state: 'YS',
    owner: 'Owner Name',
    license: 'LICENSE-NUMBER',
    ein: 'XX-XXXXXXX'
};
```

### C. Edit Services

Find the `SERVICES` array and customize:

```javascript
const SERVICES = [
    {
        id: 'service-1',
        icon: '🔧',
        title: 'Your Service 1',
        description: 'Description of service 1'
    },
    {
        id: 'service-2',
        icon: '💼',
        title: 'Your Service 2',
        description: 'Description of service 2'
    }
    // Add up to 8 services
];
```

**Icon Options:** 🔧 🛠️ 💼 🏠 🚚 🧹 🪴 🔨 ⚡ 💡 🎨 📦 🏗️ 🧰 ⚙️

### D. Edit FAQ Questions

Find the `FAQ` array:

```javascript
const FAQ = [
    {
        question: 'Your question here?',
        answer: 'Your answer here.'
    }
    // Add as many as you need
];
```

---

## 🖼️ Step 2: Add Your Logo (2 minutes)

1. Create a logo/mascot image (PNG with transparent background recommended)
2. Size: 500x500px minimum
3. Save as `logo.png` in the same folder
4. The template will automatically use it

**Need a logo?** Try:
- Canva.com (free templates)
- Remove.bg (remove background)
- Pixelart.com (8-bit style like Clutter Busters)

---

## 📱 Step 3: Update PWA Settings (1 minute)

Edit `manifest.json`:

```json
{
  "name": "Your Business Name",
  "short_name": "YourBusiness",
  "icons": [
    {
      "src": "logo.png",
      "sizes": "192x192"
    }
  ]
}
```

---

## ✅ Step 4: Customize Thank You Page (2 minutes)

Edit `template-thank-you.html`:

- Line 6: Update business name in title
- Line 17: Replace `logo.png` reference if needed
- Line 20: Update confirmation message
- Line 21: Update owner name and contact promise

---

## 🚀 Step 5: Deploy to Netlify (5 minutes)

### Option A: Drag & Drop (Easiest)
1. Go to [netlify.com](https://netlify.com) and sign in
2. Drag your folder to the deploy area
3. Done!

### Option B: Git Deploy (Recommended)
1. Push code to GitHub repository
2. Go to Netlify → "Add new site" → "Import from Git"
3. Select your repository
4. **Build settings:**
   - Base directory: *(leave empty)*
   - Build command: *(leave empty)*
   - Publish directory: `/`
5. Click "Deploy"

---

## 📧 Step 6: Enable Netlify Forms (3 minutes)

After first deployment:

1. Go to your site in Netlify dashboard
2. Click **"Forms"** in the left menu
3. After someone submits the form, you'll see it appear here
4. Click **"Settings & Usage"** → **"Form notifications"**
5. Click **"Add notification"** → **"Email notification"**
6. Enter your email address
7. Select the form: `photo-quote`
8. Save!

**Testing:**
- Submit a test quote with 2-3 photos
- Check your email (may take 2-3 minutes)
- Photos will be downloadable links in the email

---

## 🎨 Common Customizations

### Change Font
Find this line (around line 40):
```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap');
```

Replace `Inter` with any Google Font:
- **Roboto** (clean, modern)
- **Montserrat** (bold, geometric)
- **Poppins** (friendly, rounded)
- **Open Sans** (classic, readable)

Browse fonts: [fonts.google.com](https://fonts.google.com)

### Add Your Before/After Photos

Find the carousel section (around line 1200):
```html
<div class="carousel-slide" style="background-image: url('before-after-1.jpg')"></div>
<div class="carousel-slide" style="background-image: url('before-after-2.jpg')"></div>
```

Add your images and update the paths.

### Add Service Photos/Videos

In the `SERVICES` array, add `photos` and `video`:
```javascript
{
    id: 'service-1',
    icon: '🔧',
    title: 'Repair Service',
    description: 'We fix things',
    photos: ['photos/repair1.jpg', 'photos/repair2.jpg'],
    video: 'videos/repair-demo.mp4'
}
```

---

## 🐛 Troubleshooting

### Forms not working?
- Make sure you deployed to Netlify (forms don't work locally)
- Check that `data-netlify="true"` is in the form tag
- Wait 5 minutes after first deployment for Netlify to detect forms

### Colors not changing?
- Make sure you edited the `:root` variables
- Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)

### Logo not showing?
- Check filename matches exactly: `logo.png`
- Make sure it's in the same folder as index.html
- Try uploading as `mascot.png` instead

### Photos not uploading?
- File size limit: 10MB per photo
- Netlify free tier: 10MB per submission total
- For larger files, consider upgrading Netlify plan

---

## 📞 Need Help?

Common issues:
1. **"My colors are wrong"** → Edit `:root` variables in CSS
2. **"Form doesn't work"** → Must be deployed to Netlify
3. **"Logo won't show"** → Check filename and path
4. **"How do I add more services?"** → Add objects to `SERVICES` array

---

## 🎉 You're Done!

Your professional service business website is ready!

**What you get:**
- ✅ Mobile-first responsive design
- ✅ Photo quote form with Netlify integration
- ✅ Service modals for showcasing work
- ✅ FAQ accordion
- ✅ Contact form
- ✅ Professional animations and effects
- ✅ PWA-ready (installable on phones)

**Share your site:**
- Update your Google Business profile
- Add to social media bios
- Print on business cards
- Add to email signatures

Good luck with your business! 🚀
