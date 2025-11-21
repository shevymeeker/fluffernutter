# 🚀 Professional Service Business Website Template

A complete, mobile-first website template perfect for service-based businesses. Based on a premium $5000+ design, now free to use for your business!

![Template Preview](mascot.png)

## ✨ Features

- 📱 **Mobile-First Design** - Looks perfect on phones, tablets, and desktops
- 📸 **Photo Quote Form** - Customers can send photos for instant quotes
- 🎨 **Easy Customization** - Change colors, text, and services in minutes
- 💼 **Professional Design** - Premium animations, gradients, and effects
- 📧 **Netlify Forms** - Get quote requests via email automatically
- ⚡ **Fast & Lightweight** - No build process, just HTML/CSS/JavaScript
- 🔍 **SEO Optimized** - Structured data for better Google rankings
- 📱 **PWA Ready** - Installable as an app on mobile devices

## 🎯 Perfect For

- Junk Removal Services
- Landscaping Companies
- Plumbing & HVAC
- Handyman Services
- Moving Companies
- Cleaning Services
- Contractors
- Any service-based local business

## 📦 What's Included

```
template/
├── template-index.html          # Main website file
├── template-thank-you.html      # Form success page
├── manifest.json                # PWA configuration
├── TEMPLATE-SETUP.md           # Detailed setup guide
├── TEMPLATE-CONFIG-GUIDE.txt   # Search & replace guide
└── logo.png                     # Replace with your logo
```

## 🚀 Quick Start (5 Minutes)

### 1. Download Files
Get all the template files:
- `template-index.html`
- `template-thank-you.html`
- `manifest.json`
- Setup guides

### 2. Customize Using Search & Replace

Open `TEMPLATE-CONFIG-GUIDE.txt` and follow the search/replace instructions:

```plaintext
Find:    Clutter Busters
Replace: Your Business Name

Find:    (270) 315-2503
Replace: (555) 123-4567

Find:    #0f2b46    (primary color)
Replace: #1e40af    (your color)
```

### 3. Replace Logo

- Create or get your logo (500x500px recommended)
- Save as `logo.png`
- Or keep filename and update all references

### 4. Deploy to Netlify

#### Option A: Drag & Drop
1. Go to [app.netlify.com](https://app.netlify.com)
2. Drag your folder to the drop zone
3. Done! ✅

#### Option B: Git Deploy
1. Push files to GitHub repo
2. Connect Netlify to your repo
3. Deploy automatically on every commit

### 5. Enable Form Notifications

1. After first deployment, go to Netlify Dashboard
2. Click "Forms" → "Settings & Usage"
3. Add Email Notification
4. Choose `photo-quote` form
5. Enter your email

## 🎨 Customization Guide

### Change Brand Colors

Find this in the `<style>` section (line ~43):

```css
:root {
    --primary: #0f2b46;    /* Main brand color */
    --accent: #e63946;     /* Accent color */
}
```

**Recommended Color Combos:**

| Business Type | Primary   | Accent   |
|--------------|-----------|----------|
| Blue         | `#1e40af` | `#3b82f6` |
| Green        | `#065f46` | `#10b981` |
| Purple       | `#581c87` | `#a855f7` |
| Orange       | `#9a3412` | `#f97316` |
| Red          | `#991b1b` | `#ef4444` |

🎨 Generate colors: [coolors.co](https://coolors.co)

### Edit Services

Find the services grid (around line 1253):

```html
<div class="service-card" data-service="your-service" onclick="openServiceModal(this)">
    <h3>🔧 Your Service Name</h3>
</div>
```

**Popular Service Emojis:**
🗑️ 🚚 🔨 🚿 🌳 🔧 🏠 🏡 🧹 🪴 ⚡ 💡 🎨 📦 🏗️ 🧰 ⚙️

### Edit FAQ

Find FAQ section (around line 1288):

```html
<div class="faq-item">
    <button class="faq-question">
        <span>Your Question Here?</span>
        <span class="faq-icon">+</span>
    </button>
    <div class="faq-answer">
        <p>Your answer here.</p>
    </div>
</div>
```

### Change Font

Line 40 - Replace `Inter` with any Google Font:

```css
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;600;700;800;900&display=swap');
```

Popular fonts:
- **Roboto** - Clean, modern
- **Montserrat** - Bold, geometric
- **Poppins** - Friendly, rounded
- **Open Sans** - Classic, readable

Browse: [fonts.google.com](https://fonts.google.com)

## 📸 Adding Your Photos

### Before/After Carousel

Find carousel section (line ~1202):

```html
<div class="carousel-slide" style="background-image: url('photos/before-after-1.jpg')">
</div>
```

Add 2-5 photos, recommended size: 1200x600px

### Service Photos

Not included in quick setup - see `TEMPLATE-SETUP.md` for advanced guide

## 🔧 Technical Details

### Built With
- Vanilla HTML5
- CSS3 (Custom Properties, Grid, Flexbox)
- Vanilla JavaScript (ES6+)
- Netlify Forms
- Google Fonts (Inter)

### Browser Support
- Chrome/Edge (last 2 versions)
- Firefox (last 2 versions)
- Safari (last 2 versions)
- iOS Safari 12+
- Chrome Mobile

### Performance
- First Contentful Paint: <1.5s
- Time to Interactive: <3s
- Lighthouse Score: 95+ (Mobile)
- No external dependencies except Google Fonts

## 📧 Form Configuration

The photo quote form:
- **Max file size:** 10MB per photo (Netlify free tier)
- **Total upload:** 10MB per submission
- **File types:** All image formats (jpg, png, heic, webp, etc.)
- **Multiple photos:** Yes, unlimited
- **Mobile gallery:** Full access to camera roll

### Form Fields
- Name (required)
- Phone OR Email (at least one required)
- Notes (optional)
- Photos (required, multiple)

## 🐛 Troubleshooting

### Forms not working?
- Forms only work on Netlify (not local testing)
- Make sure `data-netlify="true"` is in form tag
- Wait 5 minutes after deployment
- Check Netlify dashboard → Forms tab

### Colors not changing?
- Edit the `:root` CSS variables
- Clear browser cache (Ctrl+Shift+R)
- Check you're editing the right file

### Logo not showing?
- Filename must match exactly
- Check file is in same folder as index.html
- Try `logo.png` instead of `mascot.png`

### Phone/email links not working?
- Make sure no spaces in phone numbers for `tel:` links
- Use format: `tel:5551234567`
- Email format: `mailto:you@email.com`

## 💰 Pricing & License

**This template is FREE!**

✅ Use for unlimited client projects
✅ Modify and customize as needed
✅ No attribution required
✅ Commercial use allowed

❌ Don't resell the template itself
❌ Don't claim you created the original design

## 📞 Support

For issues with:
- **Template Setup:** Check `TEMPLATE-SETUP.md`
- **Customization:** Check `TEMPLATE-CONFIG-GUIDE.txt`
- **Netlify:** [docs.netlify.com](https://docs.netlify.com)
- **Forms:** [netlify.com/docs/forms](https://docs.netlify.com/forms)

## 🎉 Success Stories

Used this template for your business? Great! Consider:
- ⭐ Starring this template repo
- 📸 Sharing your customized site
- 💬 Leaving feedback
- 🤝 Recommending to other business owners

## 📚 Additional Resources

- [Netlify Docs](https://docs.netlify.com)
- [Google Fonts](https://fonts.google.com)
- [Color Palette Generator](https://coolors.co)
- [Free Stock Photos](https://unsplash.com)
- [Compress Images](https://tinypng.com)
- [Remove Background](https://remove.bg)

## 🔄 Updates

**v1.0** (Current)
- Initial release
- Mobile-first responsive design
- Netlify Forms integration
- Photo quote system
- Service modals
- FAQ accordion
- Contact forms
- PWA support

---

## 🚀 Ready to Launch?

1. ✅ Customize text (5 min)
2. ✅ Change colors (2 min)
3. ✅ Replace logo (1 min)
4. ✅ Edit services (5 min)
5. ✅ Deploy to Netlify (2 min)
6. ✅ Enable form notifications (2 min)

**Total time: ~15-20 minutes** ⚡

Your professional business website is ready!

---

Made with ❤️ for small business owners who need affordable, professional websites.

**Questions?** Check the setup guides included with this template.
