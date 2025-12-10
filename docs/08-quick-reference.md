# Project IDX Quick Reference

Fast reference guide for working on Sedaghat Art Center website in Project IDX.

---

## 🚀 Quick Start Commands

```bash
# Clone and setup
git clone https://github.com/sedaghat-coder/main_website.git
cd main_website
npm install

# Development
npm run dev              # Start dev server (localhost:3000)
npm run build            # Build for production
npm run lint             # Lint code

# Firebase
firebase login           # Login to Firebase
firebase init            # Initialize Firebase
firebase deploy          # Deploy everything
firebase deploy --only hosting  # Deploy hosting only
```

---

## 📁 Key Files & Locations

### Configuration
- **Firebase Config**: `lib/firebase/config.ts`
- **Next.js Config**: `next.config.js`
- **Tailwind Config**: `tailwind.config.js`
- **Environment**: `.env.local`

### Documentation
- **Site Structure**: `docs/01-site-structure.md`
- **Design Specs**: `docs/02-design-specifications.md`
- **Implementation**: `docs/03-implementation-guide.md`
- **Bilingual**: `docs/04-bilingual-strategy.md`
- **Migration**: `docs/06-project-idx-migration.md`
- **Technical**: `docs/07-technical-specifications.md`

### Components
- **Layout**: `components/layout/`
- **Artwork**: `components/artwork/`
- **UI**: `components/ui/`
- **Forms**: `components/forms/`

---

## 🎨 Design Tokens

### Colors
```javascript
primary: '#8B1E3F'      // Rich Burgundy
secondary: '#D4AF37'    // Soft Gold
background: '#FAF7F2'   // Warm Cream
text: '#2C2C2C'         // Deep Charcoal
```

### Fonts
```
Headings: Playfair Display
Body: Lato
Persian: Vazirmatn
```

### Breakpoints
```
sm: 640px    // Small devices
md: 768px    // Tablets
lg: 1024px   // Laptops
xl: 1280px   // Desktops
2xl: 1536px  // Large screens
```

---

## 🔥 Firebase Collections

### artworks
```typescript
{
  id: string
  title: { en: string, fa: string }
  description: { en: string, fa: string }
  category: 'people' | 'landscapes' | 'objects'
  year: number
  medium: string
  dimensions: string
  images: { thumbnail, medium, highRes }
  price: number
  available: boolean
  featured: boolean
}
```

### exhibitions
```typescript
{
  id: string
  title: { en: string, fa: string }
  description: { en: string, fa: string }
  startDate: Date
  endDate: Date
  location: string
  artworks: string[]
  status: 'current' | 'upcoming' | 'past'
}
```

---

## 🌍 Routes

### English
```
/en                    # Home
/en/about              # About
/en/portfolio          # Portfolio grid
/en/portfolio/people   # People category
/en/portfolio/[id]     # Individual artwork
/en/exhibitions        # Exhibitions
/en/shop               # Shop
/en/contact            # Contact
/en/classes            # Classes
```

### Persian (Mirror structure)
```
/fa/*                  # All above routes in Persian
```

---

## 🛠️ Common Tasks

### Add New Artwork
```typescript
// In Firestore
await addDoc(collection(db, 'artworks'), {
  title: { en: 'Title', fa: 'عنوان' },
  description: { en: 'Desc', fa: 'توضیحات' },
  category: 'people',
  year: 2024,
  medium: 'Oil on Canvas',
  dimensions: '60x80cm',
  images: {
    thumbnail: 'url',
    medium: 'url',
    highRes: 'url'
  },
  price: 5000,
  available: true,
  featured: false,
  createdAt: new Date(),
  updatedAt: new Date()
});
```

### Upload Image
```typescript
import { uploadImage } from '@/lib/firebase/storage';

const url = await uploadImage(
  file,
  `artworks/${artworkId}/image.jpg`
);
```

### Query Artworks
```typescript
import { getArtworksByCategory } from '@/lib/firebase/firestore';

const artworks = await getArtworksByCategory('people');
```

---

## 🐛 Common Issues & Fixes

### Build Error: Module not found
```bash
rm -rf .next node_modules
npm install
npm run dev
```

### Firebase Connection Failed
```bash
# Check environment variables
cat .env.local

# Re-login to Firebase
firebase logout
firebase login
```

### Image Not Loading
```javascript
// Check next.config.js domains
images: {
  domains: ['firebasestorage.googleapis.com']
}
```

### TypeScript Errors
```bash
# Regenerate types
npm run type-check
```

---

## 📝 Git Workflow

```bash
# Create feature branch
git checkout -b feature/artwork-gallery

# Make changes, then
git add .
git commit -m "Add artwork gallery component"
git push origin feature/artwork-gallery

# In GitHub, create Pull Request
```

---

## 🔐 Security

### Never Commit
- `.env.local`
- `serviceAccountKey.json`
- `.firebase/`
- `node_modules/`

### Always Add to .gitignore
```
.env*.local
*.json (except package.json)
.firebase/
```

---

## 📦 Package Scripts

```json
{
  "dev": "next dev",
  "build": "next build",
  "start": "next start",
  "lint": "next lint",
  "export": "next build && next export",
  "deploy": "npm run build && firebase deploy"
}
```

---

## 🎯 Performance Checklist

- [ ] Images optimized (WebP format)
- [ ] Lazy loading enabled
- [ ] Code split by route
- [ ] Fonts preloaded
- [ ] Firestore queries indexed
- [ ] Storage rules configured
- [ ] CDN enabled
- [ ] Lighthouse score > 90

---

## 📞 Getting Help

### Ask AI in Project IDX
```
"How do I implement [feature] using the docs?"
"Debug this error: [paste error]"
"Review this component for best practices"
```

### Check Documentation
1. Read relevant doc in `/docs`
2. Check technical specs
3. Review code examples

### Firebase Console
- Firestore: Check data structure
- Storage: Verify file uploads
- Hosting: Check deployment status

---

## 🎨 Component Patterns

### Page Component
```typescript
export default function Page() {
  return (
    <div className="container mx-auto px-4 py-8">
      <h1 className="font-serif text-4xl mb-8">Title</h1>
      {/* Content */}
    </div>
  );
}
```

### Bilingual Text
```typescript
import { useTranslations } from 'next-intl';

export default function Component() {
  const t = useTranslations('namespace');
  return <h1>{t('key')}</h1>;
}
```

### Firestore Query
```typescript
'use server';
import { collection, getDocs } from 'firebase/firestore';
import { db } from '@/lib/firebase/config';

export async function getData() {
  const snapshot = await getDocs(collection(db, 'artworks'));
  return snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
}
```

---

## ✅ Pre-Launch Checklist

- [ ] All pages created
- [ ] Content populated
- [ ] Images uploaded
- [ ] Forms working
- [ ] Bilingual complete
- [ ] Mobile tested
- [ ] SEO optimized
- [ ] Domain connected
- [ ] SSL enabled
- [ ] Backup created

---

**Quick Links**:
- GitHub: https://github.com/sedaghat-coder/main_website
- Firebase: https://console.firebase.google.com
- Project IDX: https://idx.google.com

**Last Updated**: December 10, 2024
