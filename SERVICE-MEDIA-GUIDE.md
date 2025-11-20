# Adding Photos & Videos to Service Modals

## How It Works
Each service card (Junk Removal, Furniture Moving, etc.) is clickable and opens a modal popup with photos/videos.

## Adding Your Media

### Step 1: Organize Your Files
Create folders in your website directory:
```
/images/
  /junk-removal/
  /furniture-moving/
  /demolition/
  /etc...

/videos/
  service-video.mp4
```

### Step 2: Edit the JavaScript
Open `index.html` and find the `serviceData` section (around line 1276).

### Adding Photos
Replace the empty `photos: []` array with your image paths:

```javascript
'junk-removal': {
    title: '🗑️ Junk Removal',
    description: 'Professional junk removal services...',
    photos: [
        'images/junk-removal/before-1.jpg',
        'images/junk-removal/after-1.jpg',
        'images/junk-removal/truck.jpg'
    ],
    video: null
},
```

### Adding Videos
Replace `video: null` with your video path:

```javascript
'junk-removal': {
    title: '🗑️ Junk Removal',
    description: 'Professional junk removal services...',
    photos: [...],
    video: 'videos/junk-removal-demo.mp4'
},
```

### Complete Example
```javascript
'demolition': {
    title: '🔨 Demolition',
    description: 'Professional demolition services for interior and exterior projects.',
    photos: [
        'images/demolition/kitchen-before.jpg',
        'images/demolition/kitchen-after.jpg',
        'images/demolition/bathroom-demo.jpg',
        'images/demolition/deck-removal.jpg'
    ],
    video: 'videos/demolition-timelapse.mp4'
},
```

## Features
- **Photos**: Display in a responsive grid gallery
- **Videos**: Show with full controls at the top
- **Click photos**: Opens full size in new tab
- **Call/Text buttons**: Always visible in modal
- **Placeholder**: Shows automatically if no media added yet

## Supported Formats
- **Images**: .jpg, .jpeg, .png, .webp
- **Videos**: .mp4 (recommended), .webm

## Tips
- Keep images under 2MB for fast loading
- Use descriptive filenames: `bathroom-demo-before.jpg`
- Videos should be under 50MB
- Optimize images before uploading
- Add 4-8 photos per service for best results

## Need Help?
Contact your web developer if you need assistance adding media files.
