# Implementation Guide - Sedaghat Art Center Website

Step-by-step instructions for building the website on WordPress.com.

## 📋 Prerequisites

- [x] WordPress.com site created: sedaghatartcenter.wordpress.com
- [x] GitHub repository: github.com/sedaghat-coder/main_website
- [ ] Artwork images organized locally
- [ ] Content prepared (English & Persian)
- [ ] Domain: sedaghat.art (on Squarespace)

---

## 🚀 Phase 1: Basic Setup (Day 1)

### Step 1.1: Access WordPress Dashboard
1. Go to https://wordpress.com/
2. Log in
3. Select "Sedaghat Art Center" site
4. Dashboard: `wordpress.com/home/sedaghatartcenter.wordpress.com`

### Step 1.2: Choose and Install Theme

**Recommended: Twenty Twenty-Four** (Modern, flexible)

To Install:
```
Dashboard → Appearance → Themes → Add New 
Search "Twenty Twenty-Four" → Activate
```

### Step 1.3: Configure Basic Settings

**Site Identity**
```
Dashboard → Settings → General
```
- Site Title: Sedaghat Art Center
- Tagline: Where Art Meets Community
- Language: English
- Timezone: America/Los_Angeles
- Click Save Changes

---

## 🎨 Phase 2: Design Customization (Days 2-3)

### Step 2.1: Customize Theme Colors

```
Dashboard → Appearance → Customize → Colors
```
- Primary Color: #8B1E3F (Rich Burgundy)
- Secondary Color: #D4AF37 (Soft Gold)
- Background: #FAF7F2 (Warm Cream)
- Text: #2C2C2C (Deep Charcoal)

### Step 2.2: Add Custom CSS

```
Dashboard → Appearance → Customize → Additional CSS
```

Add this CSS:
```css
/* Import Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Lato:wght@300;400;700&family=Vazirmatn:wght@400;500;700&display=swap');

/* Apply fonts */
h1, h2, h3 {
  font-family: 'Playfair Display', Georgia, serif;
}

body, p, a, li {
  font-family: 'Lato', Arial, sans-serif;
}

/* Persian text */
[lang="fa"], .persian-text {
  font-family: 'Vazirmatn', Tahoma, sans-serif;
  direction: rtl;
  text-align: right;
}

/* Buttons */
.wp-block-button__link {
  background-color: #8B1E3F !important;
  border-radius: 4px;
  text-transform: uppercase;
  padding: 16px 32px;
  transition: all 0.3s ease;
}

.wp-block-button__link:hover {
  transform: scale(1.02);
}
```

---

## 📄 Phase 3: Create Pages (Days 3-5)

### Step 3.1: Create Main Pages

```
Dashboard → Pages → Add New
```

Create these pages (save as Draft initially):
1. Home
2. About
3. Portfolio
4. Exhibitions
5. Shop
6. Contact
7. Classes

### Step 3.2: Set Up Navigation Menu

```
Dashboard → Appearance → Menus → Create New Menu
```

1. Menu Name: "Main Navigation"
2. Add pages in order: Home, About, Portfolio, Exhibitions, Shop, Classes, Contact
3. Check "Primary Menu"
4. Save Menu

### Step 3.3: Home Page Content

```
Dashboard → Pages → Edit "Home"
```

**Use Block Editor:**

1. **Cover Block** (Hero):
   - Add hero image
   - Text: "Sedaghat Art Center" / "Where Art Meets Community"
   - Add buttons: "Explore Portfolio", "View Exhibitions"

2. **Paragraph** (Welcome):
   ```
   Welcome to Sedaghat Art Center
   
   Our goal is to provide an inclusive space for promoting art 
   and education in the community.
   ```

3. **Gallery Block** (Featured Artworks):
   - Upload 6 featured artworks
   - Set to 3 columns

4. **Button** (Call to Action):
   - "Contact Us" → Links to /contact

Publish when complete.

### Step 3.4: About Page Content

```
Dashboard → Pages → Edit "About"
```

1. **Heading**: "About Sedaghat Art Center"

2. **Mission Section**:
   ```
   Our Mission
   
   Our goal is to provide an inclusive space for promoting art and 
   education in the community. We aim to create a space where people 
   can come together to learn about art, practice meditation, and 
   explore their creativity.
   ```

3. **Artist Bio** (Use Columns Block - 2 columns):
   - Left: Artist photo
   - Right: Biography text (see full bio in docs)

Publish when complete.

---

## 🖼️ Phase 4: Portfolio Setup (Days 5-8)

### Step 4.1: Create Categories

```
Dashboard → Posts → Categories → Add New
```

Create:
- People
- Landscapes
- Objects
- Featured

### Step 4.2: Add Artwork Posts

For each artwork:
```
Dashboard → Posts → Add New
```

Template:
```
Title: [Artwork Name]

Featured Image: [Upload artwork]

Content:
[Large image]

Medium: Oil on Canvas
Year: [Year]
Dimensions: [Size]

[Description]

Status: Available for Purchase

Categories: [Select appropriate]
Tags: oil painting, realism, [others]

Publish
```

Repeat for all 40+ artworks.

---

## 🌍 Phase 5: Bilingual Setup (Days 10-12)

### Step 5.1: Create Persian Pages

For each main page, create Persian version:
```
Dashboard → Pages → Add New
```

- Title: "درباره ما" (About - Persian)
- URL Slug: Set parent to "fa"
- Result: `/fa/about`

### Step 5.2: Add Language Switcher

In both English and Persian menus:
```
Dashboard → Appearance → Menus
```

Add Custom Link:
- English menu: URL `/fa`, Text "فارسی"
- Persian menu: URL `/`, Text "English"

### Step 5.3: Configure RTL for Persian

Add to Custom CSS:
```css
.persian-page {
  direction: rtl;
  text-align: right;
}

.persian-page * {
  font-family: 'Vazirmatn', Tahoma, sans-serif !important;
}
```

Apply class "persian-page" to all Persian pages.

---

## 📧 Phase 6: Contact Forms (Day 13)

### Step 6.1: Add Contact Form

```
Dashboard → Pages → Edit "Contact"
```

Add Block → Contact Form

Fields:
- Name (required)
- Email (required)
- Subject (dropdown)
- Message (required)

Settings:
- Email to: artist.hassan@sedaghat.art
- Success message: "Thank you! We'll respond within 24 hours."

---

## ✅ Phase 7: Testing (Days 14-16)

### Test Checklist

- [ ] All pages display correctly
- [ ] All images load
- [ ] All links work
- [ ] Contact forms submit
- [ ] Mobile responsive
- [ ] Cross-browser (Chrome, Firefox, Safari)
- [ ] Language switcher works
- [ ] Persian displays correctly (RTL)

### Performance Testing

Use Google PageSpeed Insights:
1. Go to https://pagespeed.web.dev/
2. Enter: sedaghatartcenter.wordpress.com
3. Target: Mobile 70+, Desktop 90+

---

## 🚀 Phase 8: Launch (Days 17-20)

### Step 8.1: Final Settings

```
Dashboard → Settings → Reading
```
- Set home page: Select "Home"
- Uncheck "Discourage search engines"

```
Dashboard → Settings → Permalinks
```
- Select: "Post name"

### Step 8.2: Launch

1. Remove "Coming Soon" mode
2. Test final time
3. Announce on social media!

---

## 🌐 Phase 9: Domain Connection (When Ready)

**Note**: Requires upgrade to paid plan

### Upgrade Plan

```
Dashboard → Upgrades → Plans
```

Choose Personal ($4/mo) or Premium ($8/mo)

### Connect Domain

```
Dashboard → Domains → Add Domain
```

Enter: sedaghat.art
Follow verification steps

---

## 🆘 Troubleshooting

### Images Not Displaying
- Check file size (reduce if > 1MB)
- Clear browser cache

### Contact Form Not Working
- Verify email in Jetpack settings
- Check spam folder

### Slow Loading
- Optimize images (TinyPNG.com)
- Remove unused plugins

### Persian Text Issues
- Verify RTL direction set
- Check Vazirmatn font loaded

---

## 📅 Timeline Summary

- **Week 1**: Setup & Design (10 hours)
- **Week 2**: Content Migration (20 hours)
- **Week 3**: Bilingual Setup (10 hours)
- **Week 4**: Testing & Launch (5 hours)

**Total**: ~45 hours over 4 weeks

---

## 📞 Support Resources

- WordPress.com Help: https://wordpress.com/support
- Forums: https://forums.wordpress.com
- Community support available

---

**Document Version**: 1.0
**Last Updated**: December 9, 2024
