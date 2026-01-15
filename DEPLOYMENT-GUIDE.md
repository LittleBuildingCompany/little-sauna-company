# The Little Sauna Company - Website Deployment Guide

## 🚀 Quick Overview
This guide will help you:
1. Upload your photos and videos
2. Deploy your website for FREE on Netlify
3. Connect your domain (littlesaunacompany.ca)
4. Set up Google Analytics & Search Console
5. Optimize for SEO

**Total Time:** 1-2 hours
**Cost:** $0/month (or $19/month for Netlify Pro with better analytics)

---

## 📁 Step 1: Organize Your Files

### Create this folder structure on your computer:

```
little-sauna-company-website/
├── index.html                    (your main website file)
├── favicon.png                   (your logo as favicon, 32x32px)
├── apple-touch-icon.png         (your logo, 180x180px)
├── images/
│   ├── og-image.jpg             (social media preview, 1200x630px)
│   ├── logo.png                 (your logo)
│   ├── hero-video.mp4           (optional: hero section video)
│   ├── hero-video.webm          (optional: backup format)
│   ├── hero-fallback.jpg        (hero image if no video)
│   ├── sauna-1.jpg              (your actual sauna photos)
│   ├── sauna-2.jpg
│   ├── custom-sauna-1.jpg
│   ├── cold-plunge-1.jpg
│   ├── hot-tub-1.jpg
│   ├── shower-1.jpg
│   ├── about-1.jpg              (your team/workshop photos)
│   ├── about-2.jpg
│   └── about-3.jpg
└── videos/                      (optional: additional videos)
    └── showcase.mp4
```

### Image Requirements:
- **Format:** JPG for photos, PNG for logos
- **Size:** 
  - Hero images: 1920x1080px (Full HD)
  - Service cards: 800x600px minimum
  - Keep file sizes under 500KB each (compress at tinypng.com if needed)
- **Video:** Keep under 10MB, 15 seconds max, 1920x1080px

---

## 🎨 Step 2: Replace Placeholder Images in HTML

Open your `index.html` file and replace these URLs with your local images:

### Hero Section:
```html
<!-- Replace this line: -->
<img src="https://images.unsplash.com/photo-1544161515-4ab6ce6db874..." 

<!-- With this: -->
<img src="images/hero-fallback.jpg" 
```

### For Video Hero (optional):
```html
<!-- Uncomment and update: -->
<video autoplay muted loop playsinline class="hero-bg video" aria-label="Sauna wellness experience video">
    <source src="images/hero-video.mp4" type="video/mp4">
    <source src="images/hero-video.webm" type="video/webm">
</video>
```

### Service Cards:
Replace each service card image:
```html
<!-- Prefabricated Saunas -->
<img src="images/sauna-1.jpg" alt="Prefabricated barrel sauna..." 

<!-- Custom Saunas -->
<img src="images/custom-sauna-1.jpg" alt="Custom built outdoor sauna..."

<!-- Rentals -->
<img src="images/rental-sauna-1.jpg" alt="Rental sauna setup..."

<!-- Cold Plunge -->
<img src="images/cold-plunge-1.jpg" alt="Cold plunge therapy tub..."

<!-- Hot Tubs -->
<img src="images/hot-tub-1.jpg" alt="Wood-burning hot tub..."

<!-- Outdoor Showers -->
<img src="images/shower-1.jpg" alt="Premium outdoor shower..."
```

### About Section:
```html
<img src="images/about-1.jpg" alt="Expert carpenter crafting custom sauna..." 
<img src="images/about-2.jpg" alt="Beautiful cedar wood sauna interior..." 
<img src="images/about-3.jpg" alt="Outdoor sauna installation..." 
```

---

## 🌐 Step 3: Deploy to Netlify (FREE)

### Option A: Drag & Drop (Easiest - 5 minutes)

1. Go to https://www.netlify.com/
2. Sign up for FREE account (use your business email)
3. Click "Add new site" → "Deploy manually"
4. Drag your entire `little-sauna-company-website` folder into the upload area
5. Wait 30 seconds - Done! You'll get a URL like: `happy-sauna-123456.netlify.app`

### Option B: GitHub (Recommended for updates)

1. Create a FREE GitHub account at https://github.com
2. Create a new repository called "little-sauna-company"
3. Upload all your files to this repository
4. Go to Netlify → "Add new site" → "Import from Git"
5. Connect to GitHub and select your repository
6. Click "Deploy site"

**Benefits:** Every time you update files on GitHub, your site auto-updates!

---

## 🔗 Step 4: Connect Your Domain

### In Netlify:
1. Go to "Site settings" → "Domain management"
2. Click "Add custom domain"
3. Enter: `littlesaunacompany.ca`
4. Netlify will give you DNS settings

### Update Your Domain DNS:
1. Log into your domain registrar (where you bought littlesaunacompany.ca)
2. Find DNS settings
3. Add these records:

```
Type: A
Name: @
Value: 75.2.60.5

Type: CNAME  
Name: www
Value: [your-site-name].netlify.app
```

4. Wait 1-24 hours for DNS to propagate
5. Netlify will automatically add FREE SSL certificate (https://)

---

## 📊 Step 5: Set Up Google Tools (Essential for SEO)

### Google Search Console (FREE)
1. Go to https://search.google.com/search-console
2. Click "Add Property" → Enter `https://littlesaunacompany.ca`
3. Verify ownership:
   - Download verification file
   - Upload to your website root folder
   - Re-deploy on Netlify
4. Submit your sitemap: `https://littlesaunacompany.ca/sitemap.xml`

### Google Analytics (FREE)
1. Go to https://analytics.google.com
2. Create account for "The Little Sauna Company"
3. Get your tracking ID (looks like: G-XXXXXXXXXX)
4. Add this code to your HTML before `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Google Business Profile (FREE & Critical for Local SEO)
1. Go to https://business.google.com
2. Claim/update your business listing
3. Add photos, hours, services
4. Verify your address
5. **This is crucial for local Peterborough/Kawartha searches!**

---

## 🎯 Step 6: Create a Sitemap (Helps Google Find Your Pages)

Create a file called `sitemap.xml` in your root folder:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://littlesaunacompany.ca/</loc>
    <lastmod>2026-01-15</lastmod>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```

Upload this with your other files.

---

## 🤖 Step 7: AI SEO Tools Setup

### Free Tools to Use Regularly:

**1. Google Search Console** (already set up above)
   - Monitor what keywords bring people to your site
   - Check for errors
   - See which pages perform best

**2. Ubersuggest** (ubersuggest.com - FREE tier)
   - Research keywords like "sauna installation Peterborough"
   - Find what competitors rank for
   - Get content ideas

**3. AnswerThePublic** (answerthepublic.com - FREE tier)
   - Find questions people ask about saunas
   - Create content/FAQs based on real searches

**4. Use ChatGPT/Claude for:**
   - Writing SEO-optimized blog posts
   - Creating meta descriptions
   - Generating FAQs
   - Social media content

### Content Strategy:
Create these pages over time (helps SEO):
- Blog posts: "Benefits of Cold Plunge Therapy", "Choosing the Right Sauna Size"
- FAQ page
- Customer showcase/portfolio
- Installation process page

---

## ✅ Step 8: Final SEO Checklist

### Before Going Live:
- [ ] All images have descriptive alt tags
- [ ] Page title includes key location: "Peterborough"
- [ ] Meta description is compelling (155 characters)
- [ ] Phone number & address on every page
- [ ] Fast loading (test at pagespeed.google.com)
- [ ] Mobile-friendly (test on your phone)
- [ ] All links work
- [ ] Forms submit properly

### Within First Week:
- [ ] Submit to Google Search Console
- [ ] Set up Google Analytics
- [ ] Update Google Business Profile with new website
- [ ] Post on social media about new website
- [ ] Email existing customers about new site

### Ongoing Monthly:
- [ ] Check Google Search Console for issues
- [ ] Review Analytics to see what's working
- [ ] Add 1-2 new customer photos per month
- [ ] Update with seasonal promotions
- [ ] Respond to Google Business reviews

---

## 💰 Cost Breakdown

### Your Setup (Recommended):
- **Netlify Hosting:** $0/month (FREE tier)
- **Domain:** ~$15/year (you already own this)
- **SSL Certificate:** $0 (included with Netlify)
- **Google Tools:** $0 (all free)
- **Total:** $0/month vs $20-50/month for WordPress!

### Optional Upgrades:
- **Netlify Pro:** $19/month (better analytics, forms, more bandwidth)
- **Cloudinary Images:** $0-$89/month (faster image delivery, not needed initially)

---

## 🚨 Troubleshooting

### Images Not Showing?
- Check file paths are correct: `images/photo.jpg` not `Images/photo.jpg`
- Ensure images are in the right folder when you upload
- Try absolute paths in development, relative in production

### Domain Not Working?
- DNS changes take 1-24 hours
- Check nameservers at your domain registrar
- Try clearing browser cache

### Site Slow?
- Compress all images at tinypng.com
- Keep videos under 10MB
- Enable Netlify's asset optimization

### Form Not Working?
Your contact form needs a backend. Two options:
1. **Netlify Forms** (Pro plan, $19/month)
2. **Formspree** (FREE for 50 submissions/month) - Just add to your form:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```

---

## 📞 Need Help?

### Free Resources:
- **Netlify Docs:** https://docs.netlify.com
- **Google Search Central:** https://developers.google.com/search
- **Web.dev Learn:** https://web.dev/learn

### Community Support:
- Netlify Community Forums
- Web development subreddits
- Local Peterborough tech meetups

---

## 🎉 You're Ready to Launch!

Remember:
1. **Upload all your images first**
2. **Update HTML with your image paths**
3. **Deploy to Netlify**
4. **Connect domain**
5. **Set up Google tools**
6. **Monitor and improve!**

Your new site will be:
- ✅ 90% cheaper than WordPress
- ✅ Faster loading
- ✅ Better SEO
- ✅ More professional
- ✅ Easier to update

Good luck! 🚀

---

*Last updated: January 2026*
