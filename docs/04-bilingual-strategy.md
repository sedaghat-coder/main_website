# Bilingual Strategy - English/Persian Implementation

Comprehensive guide for managing bilingual content on WordPress.com free tier.

## 🌍 Overview

Since WordPress.com free tier doesn't support multilingual plugins, we'll implement a manual bilingual strategy.

---

## 📁 URL Structure

### English Pages (Default)
```
/                      (Home)
/about                 (About)
/portfolio             (Portfolio)
/exhibitions           (Exhibitions)
/shop                  (Shop)
/contact               (Contact)
/classes               (Classes)
```

### Persian Pages
```
/fa                    (خانه - Home)
/fa/about              (درباره ما - About)
/fa/portfolio          (نمونه کارها - Portfolio)
/fa/exhibitions        (نمایشگاه‌ها - Exhibitions)
/fa/shop               (فروشگاه - Shop)
/fa/contact            (تماس با ما - Contact)
/fa/classes            (کلاس‌ها - Classes)
```

**Rationale**:
- `/fa/` prefix clearly indicates Persian content
- Mirrors English structure
- SEO-friendly
- Easy to remember

---

## 🔧 Technical Implementation

### Step 1: Create Persian Parent Page

```
Dashboard → Pages → Add New
```

- Title: "فارسی"
- URL Slug: `fa`
- This becomes your Persian homepage

### Step 2: Create Persian Child Pages

For each page:
```
Dashboard → Pages → Add New
```

- Title: Persian title (e.g., "درباره ما")
- Slug: Same as English (e.g., "about")
- Parent: Select "فارسی" 
- Result: `/fa/about`

### Step 3: Set RTL Direction

**Method A: Custom CSS (Site-wide)**
```css
/* Persian pages RTL */
.persian-page {
  direction: rtl;
  text-align: right;
}

.persian-page * {
  font-family: 'Vazirmatn', Tahoma, sans-serif !important;
}
```

**Method B: Per-Page CSS Class**

For each Persian page:
1. Page Settings → Advanced → Additional CSS Class(es)
2. Add: `persian-page`

---

## 🔄 Language Switcher

### Method 1: Header Menu (Recommended)

**In English Menu:**
```
Custom Link
URL: /fa
Link Text: فارسی
```

**In Persian Menu:**
```
Custom Link
URL: /
Link Text: English
```

**Style with CSS:**
```css
.menu-item-language {
  border: 1px solid #8B1E3F;
  border-radius: 4px;
  padding: 5px 10px;
  margin-left: 10px;
}

.menu-item-language a {
  color: #8B1E3F;
  font-weight: bold;
}
```

---

## 📝 Content Management Workflow

### Translation Process

**Step 1: Create English Content First**
1. Write/design English page
2. Publish and test
3. Note images, structure, links

**Step 2: Duplicate Structure**
1. Create corresponding Persian page
2. Copy page structure (blocks, layout)
3. Use same images (no duplication needed)

**Step 3: Translate Text**
1. Translate all text content
2. Adjust for cultural appropriateness
3. Ensure Persian typography correct

**Step 4: Update Links**
1. Change internal links to Persian versions
2. Example: `/about` → `/fa/about`

**Step 5: Test**
1. Verify RTL display
2. Check all links
3. Test language switcher
4. Verify on mobile

---

## 🎨 Design Considerations

### Typography

**English:**
- Headings: Playfair Display
- Body: Lato
- Line Height: 1.7
- Font Size: 16px

**Persian:**
- All text: Vazirmatn
- Line Height: 1.8 (slightly taller)
- Font Size: 17px (slightly larger for readability)

**CSS Implementation:**
```css
/* English default */
body {
  font-family: 'Lato', Arial, sans-serif;
  font-size: 16px;
  line-height: 1.7;
}

/* Persian overrides */
.persian-page {
  font-family: 'Vazirmatn', Tahoma, sans-serif !important;
  font-size: 17px;
  line-height: 1.8;
  direction: rtl;
  text-align: right;
}
```

---

## 🔍 SEO for Bilingual Sites

### Meta Tags Per Language

**English Pages:**
```html
<meta name="language" content="en">
```

**Persian Pages:**
```html
<meta name="language" content="fa">
```

### URL Best Practices

**Do:**
- Use `/fa/` prefix consistently
- Keep URLs short
- Keep English and Persian URLs parallel

**Don't:**
- Mix languages in same URL
- Change URL structure once established

---

## 📱 Mobile Considerations

### Mobile Menu

Ensure both menus work on mobile:

```css
@media (max-width: 768px) {
  .mobile-menu {
    direction: ltr;
  }
  
  .mobile-menu.persian-menu {
    direction: rtl;
  }
}
```

---

## 🧪 Testing Checklist

### Visual Testing
- [ ] Persian text displays correctly
- [ ] RTL direction works
- [ ] Persian font loads
- [ ] Images display correctly
- [ ] Layouts don't break

### Functional Testing
- [ ] Language switcher works
- [ ] Links point to correct versions
- [ ] Forms work in both languages
- [ ] Navigation functions properly

---

## 🆘 Common Issues & Solutions

### Issue: Persian Text Appears as Boxes
**Solution:** Font doesn't support Persian. Use Vazirmatn.

### Issue: Text Flows LTR Instead of RTL
**Solution:** Add `direction: rtl` and `text-align: right` to CSS.

### Issue: Forms Don't Work in RTL
**Solution:** Add form-specific RTL CSS rules.

---

## 📊 Content Parity Matrix

Track which pages exist in both languages:

| Page | English | Persian | Status |
|------|---------|---------|--------|
| Home | ✅ | 🔄 | In Progress |
| About | ✅ | ❌ | Pending |
| Portfolio | ✅ | ❌ | Pending |

**Legend:**
- ✅ Complete
- 🔄 In Progress
- ❌ Not Started

---

## 💡 Best Practices

### Content Strategy
1. Keep both versions synchronized
2. Adapt for cultural relevance
3. Update both languages simultaneously

### Design Strategy
1. Design with RTL in mind from start
2. Test with real Persian content
3. Invest in quality Persian fonts

### Maintenance Strategy
1. Document page pairs (English ↔ Persian)
2. Establish translation workflow
3. Have native speakers review

---

**Document Version**: 1.0
**Last Updated**: December 9, 2024
