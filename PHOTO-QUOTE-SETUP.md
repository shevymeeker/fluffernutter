# Photo Quote Form Setup Guide

## How It Works

The photo quote form now sends submissions directly to Theron via **Netlify Forms**.

### What Changed:
1. **✅ Removed camera-only restriction** - Customers can now choose photos from their gallery OR take new photos
2. **✅ Multiple photo support** - Customers can select and upload multiple photos at once
3. **✅ Added Name field** - So you know who's requesting the quote
4. **✅ Added Email field (optional)** - Alternative contact method
5. **✅ Clearer labels** - "Upload Photos (Choose Multiple)" and "Send to Theron!"

## On Mobile Devices

When customers tap "📸 Upload Photos":
- **iPhone**: Shows options for "Photo Library", "Take Photo", "Browse"
- **Android**: Shows "Camera", "Gallery", "Files"
- They can select multiple photos at once from their gallery
- Selected count shows: "✓ 3 photos selected"

## How You Receive Submissions

### Netlify Forms (Current Setup)
When a customer submits photos:

1. **Email Notification** sent to the Netlify account email with:
   - Customer name
   - Customer phone number
   - Customer email (if provided)
   - Links to download all uploaded photos

2. **Netlify Dashboard** also stores all submissions at:
   - Log into Netlify
   - Go to your site
   - Click "Forms" tab
   - View all submissions and download photos

### Setup Required:

**Step 1: Verify Netlify Form Notifications**
1. Log into [Netlify](https://app.netlify.com)
2. Go to your Clutter Busters site
3. Click **Settings** → **Forms** → **Form notifications**
4. Make sure notifications are sent to: **Tallen.Clutter@gmail.com**

**Step 2: Enable File Uploads**
1. In Netlify Settings → Forms
2. Verify "Enable form detection" is ON
3. File uploads are included (free tier: 10MB/month, paid: unlimited)

**Step 3: Test the Form**
1. Visit your live site on your phone
2. Fill out the form with test data
3. Upload 2-3 test photos
4. Submit
5. Check your email for Netlify notification

### Email Format You'll Receive:

```
Subject: New form submission: photo-quote

From: Netlify Forms

Customer Name: John Smith
Customer Phone: 270-555-1234
Customer Email: john@example.com

Attachments:
- photo-1.jpg (Download Link)
- photo-2.jpg (Download Link)
- photo-3.jpg (Download Link)
```

## Alternative: Email-Only Setup

If you want submissions sent directly to your email without Netlify:

**Option 1: Use Formspree (Free)**
1. Sign up at [formspree.io](https://formspree.io)
2. Create a form pointing to Tallen.Clutter@gmail.com
3. Replace the form action with Formspree endpoint
4. Submissions go straight to your email

**Option 2: Use Gmail + Google Forms**
- Create a Google Form with file upload
- Embed on your site
- Receives files in Google Drive + email notification

## SMS Setup (Advanced)

To receive photo quotes via SMS/Text:

**Option 1: Use Zapier**
1. Connect Netlify Forms → Zapier → SMS service (Twilio)
2. When form submitted → Send SMS to 270-315-2503
3. Photos sent as links in SMS

**Option 2: Use IFTTT**
- Similar workflow to Zapier
- Free tier available

## Troubleshooting

**Photos not being received?**
- Check Netlify form submissions dashboard
- Verify email notifications are enabled
- Check spam folder for Netlify emails

**Multiple photo selection not working on mobile?**
- This is fixed now (removed `capture="environment"`)
- Customers should see gallery option
- Test on your own phone to verify

**Want to change notification email?**
- Netlify Settings → Forms → Notifications
- Add/change email address
- Can add multiple notification emails

## Current Form Fields:

```
- Customer Name (required)
- Customer Phone (required)
- Customer Email (optional)
- Photos (required, multiple allowed)
```

## File Upload Limits:

- **Max file size**: 10MB per file
- **Max files**: No limit (but total size matters)
- **Formats**: JPG, PNG, HEIC (iPhone photos)
- **Recommended**: Ask customers to send 3-5 photos

## Need Help?

If you need to:
- Change how notifications work
- Add SMS notifications
- Switch to different form provider
- Adjust form fields

Just let me know and I can update it!
