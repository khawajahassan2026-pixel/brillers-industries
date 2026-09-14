# Images Setup Guide

This folder contains all images used on The Brillers website. Follow this guide to add your images.

## Required Images

### 1. **logo-badge.jpg** (Primary Logo)
**Used in:**
- Header (top-left, 44×44px)
- Hero section (featured, ~280px)
- Footer (28×28px)
- About section (220px)

**Specifications:**
- Format: JPEG or PNG
- Recommended size: 500×500px (will scale down)
- Your embossed leather badge with "THE BRILLERS" text
- Should work at small sizes (44×44px minimum)
- Background: transparent or white (will display properly in dark header)

**Upload:** `images/logo-badge.jpg`

---

## Article Images (Optional)

The article section uses 6 product imagery cards. You can either:
- **Option A:** Add real images (recommended for professional look)
- **Option B:** Use emoji placeholders (current fallback)

If adding images, create these files:

### 2. **article-saddle-stitch.jpg**
- Topic: "The art of saddle stitching"
- Suggested: Close-up of hand-stitched leather seams
- Size: 800×600px minimum
- Upload: `images/article-saddle-stitch.jpg`

### 3. **article-full-grain.jpg**
- Topic: "Full-grain vs. nappa: What's the difference?"
- Suggested: Leather texture samples or swatches
- Size: 800×600px minimum
- Upload: `images/article-full-grain.jpg`

### 4. **article-pattern-cutting.jpg**
- Topic: "Pattern cutting: From hide to garment"
- Suggested: Leather patterns laid out or being cut
- Size: 800×600px minimum
- Upload: `images/article-pattern-cutting.jpg`

### 5. **article-hardware.jpg**
- Topic: "Choosing the right zipper and buckle"
- Suggested: Brass zips, buckles, rivets, and hardware collection
- Size: 800×600px minimum
- Upload: `images/article-hardware.jpg`

### 6. **article-finishing.jpg**
- Topic: "Edge burnishing and sealing"
- Suggested: Edge finishing tools or burnished leather close-up
- Size: 800×600px minimum
- Upload: `images/article-finishing.jpg`

### 7. **article-packing.jpg**
- Topic: "Export-ready packing and shipping"
- Suggested: Finished products being packed or boxed for export
- Size: 800×600px minimum
- Upload: `images/article-packing.jpg`

---

## Image Optimization Tips

✅ **Do:**
- Use JPEG for photos (smaller file size)
- Use PNG for logos/graphics with transparency
- Optimize images to 50–100KB each
- Use descriptive alt text (already included in HTML)
- Keep aspect ratio consistent across articles (16:9 or 4:3)

❌ **Don't:**
- Use oversized images (>2MB per image)
- Use blurry or low-quality photos
- Use images that don't relate to leather craftsmanship
- Forget to compress before uploading

---

## Compression Tools

Free online tools to optimize images before uploading:
- **TinyJPG/TinyPNG** — https://tinyjpg.com
- **ImageOptim** — https://imageoptim.com (Mac)
- **OptiPNG** — http://optipng.sourceforge.net (PNG)
- **ImageMagick** — https://imagemagick.org (CLI)

---

## Directory Structure

After adding all images, your folder should look like:

```
images/
├── logo-badge.jpg              # ✅ Required
├── article-saddle-stitch.jpg   # Optional (emoji fallback if missing)
├── article-full-grain.jpg      # Optional (emoji fallback if missing)
├── article-pattern-cutting.jpg # Optional (emoji fallback if missing)
├── article-hardware.jpg        # Optional (emoji fallback if missing)
├── article-finishing.jpg       # Optional (emoji fallback if missing)
└── article-packing.jpg         # Optional (emoji fallback if missing)
```

---

## Fallback Behavior

If an article image is missing, the website will display:
- A gradient background color
- An emoji placeholder (🧥, 🌾, ✂️, ⚙️, 🧵, 📦)
- The article content remains fully readable

This means you can **launch with just the logo** and add article images later.

---

## How to Upload

### Option 1: Git (Recommended)
```bash
# Add images locally, then push
git add images/
git commit -m "Add product and article images"
git push origin main
```

### Option 2: GitHub Web UI
1. Go to your repo: https://github.com/khawajahassan2026-pixel/brillers-industries
2. Click **Add file** → **Upload files**
3. Drag images into the uploader
4. Choose `images/` folder
5. Commit changes

### Option 3: Direct URL (CDN/Hosting)
If hosting images externally, update `index.html` image paths:
```html
<img src="https://your-cdn.com/images/logo-badge.jpg" alt="...">
```

---

## Image Dimensions Quick Reference

| Location | Recommended Size | Format |
|----------|------------------|--------|
| Header logo | 44×44px | JPEG/PNG |
| Hero badge | 280×280px | JPEG/PNG |
| Footer logo | 28×28px | JPEG/PNG |
| About badge | 220×220px | JPEG/PNG |
| Article cards | 800×600px | JPEG |

---

## Questions?

If images aren't displaying:
1. Check file names match exactly (case-sensitive)
2. Verify files are in `/images/` folder
3. Clear browser cache (Ctrl+Shift+Del)
4. Check browser console for 404 errors (F12)
5. Verify file format (JPEG vs PNG)

---

**Last updated:** September 2026
