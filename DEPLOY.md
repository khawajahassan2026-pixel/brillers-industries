# Deployment Guide — The Brillers Website

Complete step-by-step instructions for deploying The Brillers website to production.

## 🚀 Quick Deploy Options

### **Option 1: GitHub Pages (Fastest — Free)**
Perfect for static websites. Deploys directly from your GitHub repo.

**Steps:**
1. Go to your repo: https://github.com/khawajahassan2026-pixel/brillers-industries
2. Click **Settings** → **Pages**
3. Under "Source", select **Deploy from a branch**
4. Choose branch: **main**
5. Choose folder: **/ (root)**
6. Click **Save**

**Your site will be live at:**
```
https://khawajahassan2026-pixel.github.io/brillers-industries
```

**Custom domain (optional):**
1. Buy a domain (Namecheap, GoDaddy, etc.)
2. Settings → Pages → Custom domain: `thebrillersco.com`
3. Update DNS records (instructions provided by GitHub)

---

### **Option 2: Netlify (Recommended — Free + Easy)**
Faster builds, better performance, easy form integration.

**Steps:**
1. Go to https://app.netlify.com/signup
2. Sign up with GitHub
3. Click **Add new site** → **Import an existing project**
4. Select repository: `brillers-industries`
5. Branch: `main`
6. Build command: (leave empty)
7. Publish directory: `/` (root)
8. Click **Deploy site**

**Your site will be live at:**
```
https://[random-name].netlify.app
```

**Custom domain:**
1. Go to **Site settings** → **Domain management**
2. Click **Add custom domain**
3. Enter your domain: `thebrillersco.com`
4. Update DNS records (Netlify provides instructions)

**Form Integration (Bonus):**
Change form in `index.html` from:
```html
<form class="enquiry" id="enquiry-form">
```

To:
```html
<form class="enquiry" id="enquiry-form" name="contact" method="POST" netlify>
```

Netlify automatically handles form submissions!

---

### **Option 3: Vercel (Fast — Free)**
Optimized for performance. Great if you plan to add backend later.

**Steps:**
1. Go to https://vercel.com/signup
2. Sign up with GitHub
3. Click **Add new project**
4. Import repository: `brillers-industries`
5. Leave settings as default
6. Click **Deploy**

**Your site will be live at:**
```
https://brillers-industries.vercel.app
```

**Custom domain:**
1. Project settings → **Domains**
2. Add your domain: `thebrillersco.com`
3. Update DNS records

---

### **Option 4: AWS S3 + CloudFront (Professional)**
Best for high traffic, advanced caching, and analytics.

**Steps:**
1. Create AWS account: https://aws.amazon.com
2. Create S3 bucket named `thebrillersco.com`
3. Enable static website hosting
4. Upload all files to S3
5. Create CloudFront distribution pointing to S3
6. Update DNS to CloudFront URL

**Estimated cost:** $2–10/month (depends on traffic)

---

### **Option 5: Traditional Web Host (Bluehost, SiteGround, etc.)**
If you already have hosting with a provider.

**Steps:**
1. Log in to your hosting control panel (cPanel, Plesk, etc.)
2. Create FTP/SFTP account
3. Download all files locally
4. Upload via FTP to `public_html/` folder
5. Visit your domain

---

## 📋 Pre-Deployment Checklist

Before deploying, verify:

- [ ] **Logo added** — `images/logo-badge.jpg` exists and displays correctly
- [ ] **Article images added** — Or confirm emoji fallbacks are acceptable
- [ ] **Contact info updated** — Address, director name, email
- [ ] **Form wired** — If using Formspree, Netlify, or custom backend
- [ ] **Meta tags updated** — Title, description in `<head>`
- [ ] **Links working** — Test all navigation links
- [ ] **Mobile responsive** — Test on phone (Chrome DevTools)
- [ ] **Images optimized** — Compressed to <100KB each
- [ ] **Accessibility check** — Run through axe DevTools or Lighthouse
- [ ] **Performance check** — Run Lighthouse audit (target: >90)

---

## 🔧 Setup Guide by Platform

### GitHub Pages Setup (Detailed)

**Enable GitHub Pages:**
1. Go to repo Settings
2. Scroll to **Pages** section
3. Source: **Deploy from a branch**
4. Branch: **main**, folder: **/ (root)**
5. Save

**Verify deployment:**
- Go to **Actions** tab
- Should see green checkmark for latest commit
- Click it to see deployment log

**Custom domain with GitHub Pages:**
1. Buy domain from Namecheap/GoDaddy
2. Settings → Pages → **Custom domain**: `thebrillersco.com`
3. GitHub creates `CNAME` file automatically
4. Update DNS settings at your registrar:
   ```
   CNAME: www.thebrillersco.com → khawajahassan2026-pixel.github.io
   A: thebrillersco.com → 185.199.108.153
   ```
5. Wait 24 hours for DNS propagation

---

### Netlify Setup (Detailed)

**Connect GitHub:**
1. https://app.netlify.com/signup
2. Choose "GitHub"
3. Authorize Netlify to access your GitHub account
4. Select `brillers-industries` repo
5. Settings auto-filled (build command empty, publish dir `/`)
6. Click **Deploy site**

**Enable form submissions:**
1. Edit `index.html` form tag:
   ```html
   <form class="enquiry" name="contact" method="POST" netlify>
   ```
2. Remove the JavaScript form handler:
   ```javascript
   // Delete the form event listener code
   ```
3. Commit and push to GitHub
4. Netlify redeploys automatically
5. Go to **Forms** tab in Netlify dashboard to see submissions

**Custom domain:**
1. Site settings → **Domain management**
2. **Add custom domain** → `thebrillersco.com`
3. Update DNS at your registrar:
   ```
   CNAME: www → [your-netlify-domain].netlify.app
   A: [root] → 75.2.60.5
   ```

---

## 🌐 Domain & DNS Setup

### Buy a Domain

Popular registrars:
- **Namecheap** — $8.88/year (cheap, reliable)
- **GoDaddy** — $0.99/year first year (then ~$15)
- **Google Domains** — $12/year (simple, integrated)
- **Porkbun** — $8/year (privacy included)

**Recommended:** Namecheap or Google Domains

---

### Update DNS Records

Generic DNS setup for most hosts:

**For GitHub Pages:**
```
Type: A
Name: @
Value: 185.199.108.153

Type: CNAME
Name: www
Value: khawajahassan2026-pixel.github.io
```

**For Netlify:**
```
Type: CNAME
Name: www
Value: [your-netlify-site].netlify.app

Type: A
Name: @
Value: 75.2.60.5
```

**For Vercel:**
```
Type: CNAME
Name: www
Value: cname.vercel-dns.com

Type: A
Name: @
Value: 76.76.19.165
```

---

## 📧 Email Configuration

If you want enquiries sent to your email:

### Option 1: Formspree (Easiest)
```html
<form class="enquiry" id="enquiry-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

1. Go to https://formspree.io
2. Sign up
3. Create new form
4. Copy form ID
5. Replace `YOUR_FORM_ID` in HTML
6. Remove JavaScript form handler

### Option 2: Netlify Forms (Recommended)
Already covered above. Just add `netlify` attribute to form.

### Option 3: EmailJS
```javascript
emailjs.init('PUBLIC_KEY');

form.addEventListener('submit', function(e) {
  e.preventDefault();
  emailjs.sendForm('SERVICE_ID', 'TEMPLATE_ID', form)
    .then(response => status.textContent = 'Email sent!');
});
```

1. Sign up at https://www.emailjs.com
2. Create email template
3. Get SERVICE_ID, TEMPLATE_ID, PUBLIC_KEY
4. Add EmailJS script to `<head>`
5. Update form handler

### Option 4: Zapier Webhook
1. Create Zap at https://zapier.com
2. Trigger: "Webhook Catch Hook"
3. Action: "Send Email" or save to spreadsheet
4. Post form data to webhook URL

---

## ⚡ Performance Optimization

### After deployment, run Lighthouse audit:
1. Open your site
2. Press F12 (DevTools)
3. Click **Lighthouse** tab
4. Run **Mobile** and **Desktop** audits
5. Target scores: >90 for all categories

### Quick wins:
- ✅ Images already optimized in code
- ✅ No build step = instant load
- ✅ CSS inlined = no extra requests
- ✅ Fonts cached by Google
- ✅ Mobile-first responsive design

### Further optimization (optional):
- Add `<link rel="preconnect">` for fonts (already included)
- Enable Gzip compression (automatic on Netlify/Vercel)
- Add 404 redirect for SPA (not needed for static site)
- Set up CDN caching (Cloudflare free tier)

---

## 🔒 Security & SSL

- ✅ **GitHub Pages** — SSL automatic (HTTPS enabled)
- ✅ **Netlify** — SSL automatic (HTTPS enabled)
- ✅ **Vercel** — SSL automatic (HTTPS enabled)
- ✅ **AWS S3 + CloudFront** — Use AWS Certificate Manager (free)
- ⚠️ **Traditional hosting** — May need to enable HTTPS in control panel

---

## 📊 Analytics & Monitoring

### Google Analytics
1. Create account: https://analytics.google.com
2. Create property for your domain
3. Get tracking ID: `G-XXXXXXXXXX`
4. Add to `<head>` of `index.html`:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Netlify Analytics
- Automatic if using Netlify
- Go to Site analytics to see traffic

---

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| Images not loading | Check file paths in `index.html` match actual file names (case-sensitive) |
| Custom domain not working | DNS may take 24-48 hours to propagate. Check DNS status at mxtoolbox.com |
| Form not submitting | Verify form integration (Netlify, Formspree, etc.). Check browser console (F12) |
| Site loads slowly | Run Lighthouse audit. Compress images further. Enable CDN caching. |
| Mobile menu not working | Clear browser cache. Check JavaScript in console for errors. |

---

## 📞 Support Resources

- **GitHub Pages Docs** — https://docs.github.com/en/pages
- **Netlify Docs** — https://docs.netlify.com
- **Vercel Docs** — https://vercel.com/docs
- **DNS Help** — https://mxtoolbox.com (check DNS propagation)
- **SSL Certificate** — https://letsencrypt.org (free)

---

## ✅ Final Checklist Before Going Live

- [ ] Domain purchased and DNS updated
- [ ] SSL certificate working (green 🔒 in address bar)
- [ ] All pages load without 404 errors
- [ ] Forms submit without errors
- [ ] Mobile layout looks good
- [ ] Lighthouse score >90
- [ ] Analytics configured
- [ ] Contact info correct
- [ ] Images all loading
- [ ] Links all working
- [ ] Share on social media
- [ ] Email contacts with new website

---

**You're ready to go live! 🎉**

Questions? Check the README.md or deployment platform docs.

**Last updated:** September 2026
