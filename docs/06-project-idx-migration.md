# Migration Guide to Project IDX (Google Antigravity)

## 🎯 Overview

This document guides you through continuing the Sedaghat Art Center website project in Google's Project IDX with Gemini Pro or Claude Sonnet 4.5.

---

## 📋 Current Project Status

### ✅ Completed
- WordPress.com site created: sedaghatartcenter.wordpress.com
- GitHub repository: github.com/sedaghat-coder/main_website
- Complete documentation (5 comprehensive guides)
- Firebase project created: sedaghat-art-center
- Firebase services enabled: Firestore, Storage, Authentication
- Service account key downloaded

### 🎯 Next Steps
- Build Next.js + Firebase website
- Implement bilingual gallery (English/Persian)
- Deploy to Firebase Hosting
- Connect custom domain: sedaghat.art

---

## 🚀 Quick Start in Project IDX

### Step 1: Open Project IDX

1. Go to https://idx.google.com/
2. Sign in with your Google account
3. Click "Create new workspace"

### Step 2: Import from GitHub

1. Select "Import from GitHub"
2. Authorize GitHub access
3. Choose repository: `sedaghat-coder/main_website`
4. Click "Import"

### Step 3: Select Template

1. Choose: **Next.js** template
2. Or: **Empty** workspace (then install Next.js)
3. Wait for workspace to initialize

### Step 4: Enable Firebase Integration

In Project IDX workspace:
1. Click Extensions → Firebase
2. Connect to project: `sedaghat-art-center`
3. Authenticate with Google account
4. Firebase will auto-configure

---

## 🔥 Firebase Configuration

### Service Account Key

Your service account key is at:
```
C:\Users\sinas\.firebase\sedaghat-art-center-key.json
```

**For Project IDX**:
1. Upload this file to your workspace
2. Store in: `/workspace/.firebase/serviceAccountKey.json`
3. Add to `.gitignore`:
   ```
   .firebase/
   *.json
   !package.json
   ```

### Firebase Config

```javascript
// lib/firebase/config.ts
import { initializeApp } from 'firebase/app';
import { getFirestore } from 'firebase/firestore';
import { getStorage } from 'firebase/storage';
import { getAuth } from 'firebase/auth';

const firebaseConfig = {
  projectId: "sedaghat-art-center",
  storageBucket: "sedaghat-art-center.firebasestorage.app",
  // Add other config from Firebase Console
};

const app = initializeApp(firebaseConfig);
export const db = getFirestore(app);
export const storage = getStorage(app);
export const auth = getAuth(app);
```

---

## 📚 Documentation Files

All documentation is in `/docs`:
1. **01-site-structure.md** - Complete page hierarchy
2. **02-design-specifications.md** - Colors, fonts, layouts
3. **03-implementation-guide.md** - Build instructions
4. **04-bilingual-strategy.md** - English/Persian management
5. **05-content-migration-plan.md** - Wix to WordPress (now to Firebase)

**READ THESE FIRST** before starting development!

---

## 🏗️ Project Architecture

### Tech Stack
- **Frontend**: Next.js 14 (App Router)
- **Styling**: Tailwind CSS
- **Database**: Firebase Firestore
- **Storage**: Firebase Storage
- **Hosting**: Firebase Hosting
- **Auth**: Firebase Authentication (future)
- **Domain**: sedaghat.art

### Folder Structure
```
main_website/
├── app/                    # Next.js app router
│   ├── [locale]/          # Bilingual routing (en/fa)
│   │   ├── page.tsx       # Home
│   │   ├── about/
│   │   ├── portfolio/
│   │   ├── exhibitions/
│   │   ├── shop/
│   │   ├── contact/
│   │   └── classes/
│   └── api/               # API routes
├── components/            # React components
│   ├── ui/               # UI components
│   ├── layout/           # Layout components
│   └── artwork/          # Artwork-specific
├── lib/                  # Utilities
│   ├── firebase/         # Firebase config
│   └── utils/            # Helper functions
├── public/               # Static assets
├── docs/                 # Documentation
└── styles/              # Global styles
```

---

## 🎨 Design System (Quick Reference)

### Colors
- **Primary**: #8B1E3F (Rich Burgundy)
- **Secondary**: #D4AF37 (Soft Gold)
- **Background**: #FAF7F2 (Warm Cream)
- **Text**: #2C2C2C (Deep Charcoal)

### Typography
- **Headings**: Playfair Display
- **Body**: Lato
- **Persian**: Vazirmatn

### Responsive Breakpoints
- Mobile: < 768px
- Tablet: 768px - 1199px
- Desktop: 1200px+

---

## 📊 Firestore Schema

### Collections

**artworks** collection:
```javascript
{
  id: string,
  title: {
    en: string,
    fa: string
  },
  description: {
    en: string,
    fa: string
  },
  category: "people" | "landscapes" | "objects",
  year: number,
  medium: string,
  dimensions: string,
  images: {
    thumbnail: string,  // Storage URL
    medium: string,     // Storage URL
    highRes: string     // Storage URL
  },
  price: number,
  available: boolean,
  featured: boolean,
  createdAt: timestamp,
  updatedAt: timestamp
}
```

**exhibitions** collection:
```javascript
{
  id: string,
  title: {
    en: string,
    fa: string
  },
  description: {
    en: string,
    fa: string
  },
  startDate: timestamp,
  endDate: timestamp,
  location: string,
  artworks: string[],  // artwork IDs
  images: string[],    // Storage URLs
  status: "current" | "upcoming" | "past"
}
```

---

## 🚀 Development Workflow

### 1. Initial Setup
```bash
# Install dependencies
npm install

# Install required packages
npm install firebase @firebase/firestore @firebase/storage
npm install next@14 react react-dom
npm install tailwindcss postcss autoprefixer
npm install @types/node @types/react typescript

# Initialize Tailwind
npx tailwindcss init -p
```

### 2. Run Development Server
```bash
npm run dev
```

### 3. Build for Production
```bash
npm run build
```

### 4. Deploy to Firebase
```bash
firebase deploy
```

---

## 🌍 Bilingual Implementation

### Route Structure
- English: `/en/*`
- Persian: `/fa/*`
- Default: Redirect to `/en`

### Language Switcher Component
```typescript
// components/LanguageSwitch.tsx
'use client';
import { usePathname, useRouter } from 'next/navigation';

export default function LanguageSwitch() {
  const pathname = usePathname();
  const router = useRouter();
  
  const toggleLanguage = () => {
    const newLocale = pathname.startsWith('/fa') ? 'en' : 'fa';
    const newPath = pathname.replace(/^\/(en|fa)/, `/${newLocale}`);
    router.push(newPath);
  };

  return (
    <button onClick={toggleLanguage}>
      {pathname.startsWith('/fa') ? 'EN' : 'فا'}
    </button>
  );
}
```

---

## 📝 Key Features to Implement

### Phase 1: Core Structure (Week 1)
- [x] Project setup
- [ ] Design system implementation
- [ ] Layout components (header, footer)
- [ ] Home page
- [ ] About page
- [ ] Bilingual routing

### Phase 2: Gallery (Week 2)
- [ ] Firestore integration
- [ ] Storage integration
- [ ] Portfolio page with filtering
- [ ] Individual artwork pages
- [ ] Image optimization

### Phase 3: Additional Pages (Week 3)
- [ ] Exhibitions page
- [ ] Shop page (with Stripe)
- [ ] Contact form
- [ ] Classes page

### Phase 4: Polish & Deploy (Week 4)
- [ ] SEO optimization
- [ ] Performance tuning
- [ ] Testing
- [ ] Deploy to Firebase Hosting
- [ ] Connect sedaghat.art domain

---

## 🔐 Security Rules

### Firestore Rules
```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Public read access
    match /artworks/{artwork} {
      allow read: if true;
      allow write: if request.auth != null; // Admin only
    }
    
    match /exhibitions/{exhibition} {
      allow read: if true;
      allow write: if request.auth != null;
    }
  }
}
```

### Storage Rules
```javascript
rules_version = '2';
service firebase.storage {
  match /b/{bucket}/o {
    match /artworks/{allPaths=**} {
      allow read: if true;
      allow write: if request.auth != null; // Admin only
    }
  }
}
```

---

## 💡 Pro Tips for Project IDX

1. **Use Built-in Terminal**: Split terminal for dev server + commands
2. **Firebase Emulator**: Test locally before deploying
3. **Hot Reload**: Changes reflect instantly
4. **AI Assistance**: Use Gemini/Claude in IDE for help
5. **Version Control**: Commit frequently to GitHub

---

## 🆘 Troubleshooting

### Firebase Connection Issues
- Check project ID is correct
- Verify service account key is valid
- Ensure Firebase services are enabled

### Next.js Build Errors
- Clear `.next` folder: `rm -rf .next`
- Reinstall dependencies: `rm -rf node_modules && npm install`
- Check Node.js version: `node -v` (should be 18+)

### Deployment Issues
- Run `firebase login` first
- Check `firebase.json` configuration
- Verify project is selected: `firebase use sedaghat-art-center`

---

## 📞 Getting Help

**Ask AI Assistant in Project IDX**:
- "Help me implement [feature] based on the documentation"
- "Review my code for [component]"
- "Debug this error: [error message]"

**Reference Documentation**:
- Read `/docs/03-implementation-guide.md` for detailed steps
- Check `/docs/02-design-specifications.md` for design details
- Use `/docs/04-bilingual-strategy.md` for i18n help

---

## 🎯 Success Criteria

You'll know you're on track when:
- [x] Project opens in IDX without errors
- [ ] Dev server runs on localhost
- [ ] Firebase connection works
- [ ] Can query Firestore
- [ ] Can upload to Storage
- [ ] Bilingual routing works
- [ ] Design matches specifications

---

**Next Action**: Open this project in Project IDX and start with Phase 1!

**Last Updated**: December 10, 2024
