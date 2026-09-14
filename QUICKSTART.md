# Quick Start Guide — The Brillers Website

Get your website up and running in 5 minutes.

---

## ⚡ 5-Minute Setup

### Step 1: Clone the Repository (1 min)
```bash
git clone https://github.com/khawajahassan2026-pixel/brillers-industries.git
cd brillers-industries
```

### Step 2: Add Your Logo (2 min)
1. Rename your logo file to: `logo-badge.jpg`
2. Place it in the `images/` folder
3. File should be ~500×500px (JPEG or PNG)

### Step 3: Deploy (2 min)

**Choose ONE:**

#### A. GitHub Pages (Easiest)
```bash
git add images/logo-badge.jpg
git commit -m "Add logo"
git push origin main
```
Then:
1. Go to repo Settings → Pages
2. Source: **Deploy from a branch** → **main** → **/ (root)**
3. Your site is live at: `https://khawajahassan2026-pixel.github.io/brillers-industries`

#### B. Netlify (Recommended)
1. Go to https://app.netlify.com/signup
2. Sign up with GitHub
3. Click **Add new site** → Select `brillers-industries`
4. Deploy! (automatic)
5. Your site is live in seconds

#### C. Vercel
1. Go to https://vercel.com/signup
2. Sign up with GitHub
3. Click **Add new project** → Select repo
4. Deploy! Your site is live

---

## 📝 Customization (Next Steps)

### Update Company Info
Edit `index.html`:

**Line 1157 — Address:**
```html
<strong>The Brillers</strong>
34/134, Budhi Bazar          <!-- CHANGE THIS -->
Near Ahmadia School
Sialkot, Pakistan
```

**Line 1160 — Director:**
```html
Director: Khawaja Hassan Shaukat     <!-- CHANGE THIS -->
```

**Line 1171 — Email/Phone (optional):**
Add your contact info in the contact section.

### Update Product Descriptions
Edit `index.html` lines 387–455 for product cards.

### Update Article Titles & Content
Edit `index.html` lines 489–573 for blog articles.

### Add Article Images
1. Add to `images/` folder:
   - `article-saddle-stitch.jpg`
   - `article-full-grain.jpg`
   - `article-pattern-cutting.jpg`
   - `article-hardware.jpg`
   - `article-finishing.jpg`
   - `article-packing.jpg`
2. Commit and push
3. Images display automatically

---

## 🔧 Wire Up the Contact Form

### Option 1: Netlify (Easiest)
1. Edit `index.html` form tag (line 1086):
   ```html
   <form class="enquiry" name="contact" method="POST" netlify>
   ```
2. Remove lines 1260–1270 (JavaScript form handler)
3. Commit and push
4. Forms automatically submit to Netlify dashboard

### Option 2: Formspree
1. Go to https://formspree.io
2. Create new form, get `YOUR_FORM_ID`
3. Edit form action (line 1086):
   ```html
   <form class="enquiry" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```
4. Formspree emails you submissions

### Option 3: EmailJS
See `DEPLOY.md` for detailed setup.

---

## 🌐 Connect Custom Domain

### Buy a Domain
- Namecheap: $8.88/year (recommended)
- Google Domains: $12/year
- GoDaddy: $0.99 first year

### Connect Domain

**If using GitHub Pages:**
1. Settings → Pages → **Custom domain**: `yourdomainname.com`
2. Update DNS at your registrar:
   ```
   A: @ → 185.199.108.153
   CNAME: www → khawajahassan2026-pixel.github.io
   ```

**If using Netlify:**
1. Site settings → **Domain management**
2. **Add custom domain**: `yourdomainname.com`
3. Update DNS at your registrar:
   ```
   CNAME: www → [your-netlify-site].netlify.app
   A: @ → 75.2.60.5
   ```

**If using Vercel:**
1. Project settings → **Domains**
2. Add: `yourdomainname.com`
3. Update DNS at your registrar:
   ```
   CNAME: www → cname.vercel-dns.com
   A: @ → 76.76.19.165
   ```

---

## 📱 Test Your Site

### Desktop
1. Open your deployed site in Chrome/Firefox/Safari
2. Test all navigation links
3. Run Lighthouse audit (F12 → Lighthouse)
4. Target score: >90

### Mobile
1. Open on phone or use Chrome DevTools (F12 → Toggle device)
2. Test hamburger menu
3. Verify images load correctly
4. Test form submission

### Troubleshooting
| Issue | Fix |
|-------|-----|
| Images not loading | Check `images/` folder has files. File names must match HTML exactly (case-sensitive) |
| Custom domain shows error | DNS takes 24-48 hours. Use mxtoolbox.com to check |
| Form not working | Verify form integration (Netlify/Formspree). Check browser console (F12) |
| Slow load | Run Lighthouse. Compress images. Enable CDN. |

---

## 📊 Monitor & Iterate

### Analytics
Add Google Analytics (optional):
1. Go to https://analytics.google.com
2. Create property
3. Copy tracking ID
4. Add to `<head>` of `index.html`:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXX');
</script>
```

### Check Form Submissions
- **Netlify:** Forms tab in dashboard
- **Formspree:** Email inbox + dashboard
- **EmailJS:** Check email forwarding

---

## 🎯 Deployment Checklist

Before going live:

- [ ] Logo added to `images/logo-badge.jpg`
- [ ] Company address updated
- [ ] Director name updated
- [ ] Contact form wired (Netlify/Formspree/EmailJS)
- [ ] All images optimized (<100KB each)
- [ ] Mobile layout tested
- [ ] All links working
- [ ] Lighthouse score >90
- [ ] Custom domain purchased & DNS updated
- [ ] Analytics configured (optional)

---

## 📚 Full Documentation

- **Setup & Customization:** `README.md`
- **Deployment Guide:** `DEPLOY.md`
- **Image Setup:** `images/README.md`

---

## 🆘 Common Questions

**Q: Can I use a different domain name?**
A: Yes! Buy any domain and update DNS records to point to your hosting platform (GitHub Pages, Netlify, Vercel, etc.).

**Q: How do I add more products/articles?**
A: Edit `index.html` and duplicate product card or article card HTML, update content.

**Q: Can I change the colors?**
A: Yes! Edit CSS variables in `<style>` tag:
```css
:root{
  --brass: #B9843F;        /* Change this */
  --saddle: #3B2417;       /* Or this */
  /* etc. */
}
```

**Q: Is there a build step or dependencies?**
A: No! Pure HTML/CSS/JS. Just upload and go.

**Q: Can I add e-commerce?**
A: Not in this version. For shopping, use Shopify, WooCommerce, or add a cart later.

**Q: How do I update the website?**
A: Edit files locally, commit to GitHub, push. Your site updates automatically.

**Q: Can I use my own hosting?**
A: Yes! Upload all files via FTP to any traditional web host.

---

## 🚀 Next Steps

1. **Add logo** → Deploy → Share link
2. **Update company info** → Commit → Redeploy
3. **Add article images** → Commit → Redeploy
4. **Wire contact form** → Test → Go live
5. **Buy custom domain** → Update DNS → Done!

---

## 💬 Need Help?

1. Check `README.md` for setup details
2. Check `DEPLOY.md` for deployment options
3. Check `images/README.md` for image specs
4. Check browser console (F12) for errors
5. Search platform docs (GitHub Pages, Netlify, Vercel)

---

**You've got this! The website is ready to launch. 🎉**

**Last updated:** September 2026
