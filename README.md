# The Brillers — Leather Goods Manufacturer

A premium, handcrafted leather goods manufacturing website for **The Brillers**, based in Sialkot, Pakistan. Built with a saddle-brown and brass aesthetic, featuring custom line-art icons, genuine leather badge imagery, and a complete five-step production process.

## 🎯 Features

- **Hero Section** — Genuine leather stamp badge aesthetic with animated text ring
- **Craft Ticker** — Scrolling production capabilities and materials
- **Product Grid** — Six product lines (Jackets featured) with custom icons
- **Latest Articles** — Blog section with leather craftsmanship stories
- **Five-Step Process** — Transparent sourcing → grading → cutting → stitching → inspection workflow
- **Director Profile** — Khawaja Hassan Shaukat bio and philosophy
- **Contact Form** — Front-end ready enquiry form (wire to email/CRM)
- **Responsive Design** — Mobile-first, accessibility-first
- **Premium Typography** — Big Shoulders Display + Libre Franklin

## 📁 File Structure

```
brillers-industries/
├── index.html              # Main website
├── images/
│   ├── logo-badge.jpg      # Embossed leather badge (header, hero, footer, about)
│   ├── article-saddle-stitch.jpg
│   ├── article-full-grain.jpg
│   ├── article-pattern-cutting.jpg
│   ├── article-hardware.jpg
│   ├── article-finishing.jpg
│   └── article-packing.jpg
└── README.md
```

## 🎨 Design System

**Color Palette:**
- **Ink** — `#211710` (Primary text)
- **Saddle** — `#3B2417` (Dark brown)
- **Saddle Dark** — `#241209` (Darkest)
- **Brass** — `#B9843F` (Primary accent)
- **Brass Light** — `#D8AE6E` (Secondary accent)
- **Parchment** — `#F1E8D6` (Light background)
- **Paper** — `#FBF7EE` (White alternative)

**Typography:**
- **Display:** Big Shoulders Display (headings)
- **Body:** Libre Franklin (content)

## 📦 Setup

1. Clone the repository:
```bash
git clone https://github.com/khawajahassan2026-pixel/brillers-industries.git
cd brillers-industries
```

2. Add your images to the `images/` folder:
   - `logo-badge.jpg` — Your embossed leather badge (used in header, hero, footer)
   - Article images (optional — use emoji placeholders if not ready)

3. Deploy directly to any static host:
   - GitHub Pages
   - Netlify
   - Vercel
   - AWS S3
   - Traditional web host

## 🔗 Navigation

- **Products** — Six product lines with descriptions
- **Latest** — Blog/articles section
- **Craftsmanship** — Five-step production process
- **About** — Director profile and company philosophy
- **Contact** — Enquiry form and workshop address

## 💼 Contact Form Integration

The enquiry form is front-end only. To make it functional, connect it to:
- **Email Service:** Formspree, EmailJS, or AWS SES
- **CRM:** HubSpot, Shopify, Pipedrive, or custom backend
- **Webhook:** Zapier, Make, or IFTTT

### Quick Integration (Formspree)

Replace the form `id="enquiry-form"` action:

```html
<form class="enquiry" id="enquiry-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
  <!-- form fields unchanged -->
</form>
```

Then remove the JavaScript form handler or update it accordingly.

## ✨ Customization

### Update Company Info
- Address: 34/134, Budhi Bazar, Sialkot
- Director: Khawaja Hassan Shaukat
- Company name throughout

### Update Product Descriptions
- Product cards and feature copy

### Update Article Content
- Article titles, descriptions, tags, and metadata

### Update Craft Process
- Five steps with descriptions

## 🚀 Performance

- **No build step** — Pure HTML/CSS/JS
- **No external dependencies** — Fonts from Google Fonts only
- **Lazy loading** — Article images load on demand
- **Accessible** — ARIA labels, focus states, reduced-motion support
- **Mobile optimized** — Responsive grid, hamburger menu

## 📱 Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Android)

## 📄 License

© 2026 The Brillers — Manufacturer & Exporter, Sialkot, Pakistan.

## 📞 Contact

For questions about the website or leather goods manufacturing:
- **Address:** 34/134, Budhi Bazar, Near Ahmadia School, Sialkot, Pakistan
- **Director:** Khawaja Hassan Shaukat

---

**Ready to go live?**
1. Add your logo and article images to `/images`
2. Update company info and contact details
3. Wire the form to your email/CRM
4. Deploy to your hosting platform
5. Configure DNS and SSL certificate
