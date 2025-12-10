# Content Migration Plan - Wix to WordPress.com

Complete guide for migrating content from your existing Wix site to WordPress.com.

## 📊 Migration Overview

**Source**: sedaghatart.wixsite.com/home
**Destination**: sedaghatartcenter.wordpress.com

**Content Volume**:
- 6 main pages
- 40+ artworks
- 7 shop products
- Multiple portfolio collections

---

## 🎯 Migration Strategy

### Phase Approach

**Phase 1**: Structure & Design (Week 1)
- Set up WordPress site
- Configure theme
- Create empty pages

**Phase 2**: Content Migration (Week 2)
- Export content from Wix
- Import to WordPress
- Upload images

**Phase 3**: Testing (Week 3)
- Verify all content
- Fix broken links
- Test functionality

**Phase 4**: Launch (Week 4)
- Final QA
- Go live

---

## 📋 Content Inventory

### From Wix Site

#### Main Pages (6)
1. Home (`/home`)
2. About (`/about`)
3. Portfolio (`/portfolio`)
4. Exhibitions (`/exhibition`)
5. Contact (`/contact`)
6. Shop (`/category/all-products`)

#### Portfolio Collections
- **All Paintings**: 40+ items
- **People**: ~16 items
- **Landscapes**: ~4 items
- **Objects**: ~4 items

#### Shop Products (7)
1. Yalda's Pomegranate
2. Lemons
3. Yalda's Pomegranate 2
4. Lemons and Glass
5. Syrian Kid in the Camp
6. Smiles of a Boy and a Girl
7. Afghan Girl

---

## 📥 Step-by-Step Migration

### Step 1: Export Content from Wix

**Manual Export** (Recommended):

1. Open each Wix page
2. Copy all text content
3. Paste into Word/Google Docs
4. Organize by page
5. Note formatting

### Step 2: Download Images

**Bulk Download Options**:

**Option A: Manual**
- Right-click each image
- "Save image as..."
- Organize in folders

**Option B: Browser Extension**
- Install "Image Downloader" (Chrome)
- Visit Wix site
- Select and download all images

**Organize downloads**:
```
/artwork-images/
  /people/
    saqqa.jpg
    girl-and-horse.jpg
  /landscapes/
    melody-of-the-night.jpg
  /objects/
    clay-dish-and-fruit.jpg
  /shop-products/
    yaldas-pomegranate.jpg
```

---

### Step 3: Prepare Images

**For Each Image:**

1. **Resize** (if needed):
   - Max 2000px width for artworks
   - Max 1200px for general photos

2. **Compress**:
   - Use TinyPNG.com
   - Target: Under 500KB per image

3. **Rename**:
   ```
   Before: DSC_1234.jpg
   After: artwork-saqqa-hassan-sedaghat.jpg
   ```

---

### Step 4: Content Mapping

Create mapping document:

```
WIX → WORDPRESS

HOME PAGE
---------
Wix: sedaghatart.wixsite.com/home
WP: sedaghatartcenter.wordpress.com/

Sections:
1. Hero Image → Cover Block
2. Welcome Text → Paragraph Block
3. Featured Works → Gallery Block
4. Contact CTA → Button Block

ABOUT PAGE
----------
Wix: /about
WP: /about

Sections:
1. Artist Bio → Paragraph
2. Artist Photo → Image Block
3. Mission → Quote Block
```

---

### Step 5: Migrate Page Content

**For Each Page:**

1. **Create WordPress Page**
   ```
   Dashboard → Pages → Add New
   ```

2. **Recreate Layout**
   - Use WordPress blocks
   - Match Wix layout

3. **Add Content**
   - Copy text from Wix
   - Paste into WordPress
   - Reformat as needed

4. **Upload Images**
   ```
   Add Block → Image → Upload
   ```

5. **Save as Draft**

---

### Step 6: Migrate Portfolio Items

**Use Posts for Artworks:**

```
Dashboard → Posts → Categories
```

Create categories:
- People
- Landscapes
- Objects
- Featured

**For Each Artwork:**

```
Dashboard → Posts → Add New

Title: [Artwork Name]
Featured Image: [Upload]

Content:
Medium: Oil on Canvas
Year: [Year]
Dimensions: [Size]

[Description]

Status: Available

Categories: [Select]
Tags: oil painting, realism

Publish
```

---

### Step 7: Migrate Shop Products

Create product posts:

```
Dashboard → Posts → Add New
Category: Shop

Title: [Product Name]
Featured Image: [Product photo]

Content:
Price: [Amount]
Medium: Oil on Canvas
Dimensions: [Size]

[Description]

Availability: Available

[Contact Form or Button]

Publish
```

---

### Step 8: Update Links

After migration, update all internal links:

**Old Links (Wix)**:
```
sedaghatart.wixsite.com/home/about
```

**New Links (WordPress)**:
```
sedaghatartcenter.wordpress.com/about
```

**How to Update:**
- Edit each page/post
- Find links
- Update to new URL
- Save

---

### Step 9: Set Up Redirects

**Wix Site Banner:**

Add to Wix site:
> "We've moved! Visit us at sedaghatartcenter.wordpress.com"

Keep Wix live for 1-3 months during transition.

---

## ✅ Migration Checklist

### Pre-Migration
- [ ] Document Wix site structure
- [ ] Screenshot all pages
- [ ] Download all content
- [ ] Download all images
- [ ] Create inventory spreadsheet

### WordPress Setup
- [ ] Site created
- [ ] Theme configured
- [ ] Basic settings done
- [ ] Categories created

### Content Migration
- [ ] Home page migrated
- [ ] About page migrated
- [ ] Portfolio structure created
- [ ] All artwork posts created
- [ ] Shop pages created
- [ ] Contact forms added
- [ ] All images uploaded
- [ ] Alt text added

### Testing
- [ ] All pages display correctly
- [ ] All images load
- [ ] All links work
- [ ] Forms submit
- [ ] Mobile responsive
- [ ] Cross-browser tested

### Launch
- [ ] Content proofread
- [ ] Final design review
- [ ] SEO titles/descriptions
- [ ] Launch!

---

## 🛠️ Tools & Resources

### Image Optimization
- **TinyPNG**: https://tinypng.com/
- **Squoosh**: https://squoosh.app/

### Content Organization
- **Google Sheets**: Inventory tracking
- **Trello**: Progress tracking

### Testing
- **PageSpeed Insights**: Speed test
- **WAVE**: Accessibility check

---

## ⏱️ Estimated Timeline

**Total**: 3-4 weeks part-time

### Week 1: Preparation (10 hours)
- Export content from Wix
- Download images
- WordPress setup

### Week 2: Migration (20 hours)
- Main pages
- Portfolio artworks
- Shop products

### Week 3: Refinement (10 hours)
- Link updates
- Testing
- Design polish

### Week 4: Launch (5 hours)
- Final review
- Go live
- Monitor

---

## 🆘 Common Issues

### Images Don't Transfer
**Problem**: Wix proprietary URLs
**Solution**: Must download and re-upload

### Links Break
**Problem**: URL structure changed
**Solution**: Update all internal links

### SEO Rankings Drop
**Problem**: New domain, fresh site
**Solution**:
- Submit sitemap to Google
- Keep Wix live during transition
- Build backlinks
- Be patient (3-6 months)

---

## 💡 Pro Tips

1. **Work in Drafts**: Don't publish until complete
2. **Keep Wix Live**: Don't delete until stable
3. **Backup Everything**: Save all Wix content offline
4. **Test Thoroughly**: Better to delay than launch broken
5. **Get Feedback**: Have others review

---

## 📊 Progress Tracking

| Content Type | Total | Completed | Status |
|--------------|-------|-----------|--------|
| Main Pages | 6 | 0 | Not Started |
| Artworks | 40+ | 0 | Not Started |
| Shop Products | 7 | 0 | Not Started |
| Images | 50+ | 0 | Not Started |

Update as you progress!

---

**Document Version**: 1.0
**Last Updated**: December 9, 2024
