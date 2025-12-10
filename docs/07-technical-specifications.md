# Technical Specifications for Project IDX

Complete technical implementation details for building the Sedaghat Art Center website in Next.js + Firebase.

---

## 🏗️ Architecture Overview

### Stack
- **Framework**: Next.js 14.2+ (App Router)
- **Language**: TypeScript 5.0+
- **Styling**: Tailwind CSS 3.4+
- **Database**: Firebase Firestore
- **Storage**: Firebase Storage
- **Hosting**: Firebase Hosting
- **CDN**: Firebase CDN (automatic)

---

## 📦 Dependencies

### Core Dependencies
```json
{
  "dependencies": {
    "next": "^14.2.0",
    "react": "^18.3.0",
    "react-dom": "^18.3.0",
    "firebase": "^10.12.0",
    "typescript": "^5.4.0"
  }
}
```

### UI & Styling
```json
{
  "dependencies": {
    "tailwindcss": "^3.4.0",
    "autoprefixer": "^10.4.0",
    "postcss": "^8.4.0",
    "@tailwindcss/typography": "^0.5.10",
    "@tailwindcss/forms": "^0.5.7"
  }
}
```

### Firebase Services
```json
{
  "dependencies": {
    "firebase": "^10.12.0",
    "firebase-admin": "^12.1.0"
  }
}
```

### Additional Libraries
```json
{
  "dependencies": {
    "next-intl": "^3.14.0",
    "framer-motion": "^11.2.0",
    "react-icons": "^5.2.0",
    "sharp": "^0.33.0"
  }
}
```

---

## 🗂️ Complete Folder Structure

```
main_website/
├── .firebase/                      # Firebase cache (gitignored)
├── .next/                          # Next.js build (gitignored)
├── app/                            # Next.js App Router
│   ├── [locale]/                   # Internationalization
│   │   ├── layout.tsx              # Root layout
│   │   ├── page.tsx                # Home page
│   │   ├── about/
│   │   │   └── page.tsx
│   │   ├── portfolio/
│   │   │   ├── page.tsx            # Portfolio grid
│   │   │   ├── [category]/         # Category pages
│   │   │   │   └── page.tsx
│   │   │   └── [id]/               # Individual artwork
│   │   │       └── page.tsx
│   │   ├── exhibitions/
│   │   │   ├── page.tsx
│   │   │   └── [id]/
│   │   │       └── page.tsx
│   │   ├── shop/
│   │   │   ├── page.tsx
│   │   │   └── [id]/
│   │   │       └── page.tsx
│   │   ├── contact/
│   │   │   └── page.tsx
│   │   └── classes/
│   │       └── page.tsx
│   ├── api/                        # API Routes
│   │   ├── contact/
│   │   │   └── route.ts
│   │   └── artworks/
│   │       └── route.ts
│   ├── globals.css                 # Global styles
│   └── layout.tsx                  # Root layout
├── components/                     # React Components
│   ├── layout/
│   │   ├── Header.tsx
│   │   ├── Footer.tsx
│   │   ├── Navigation.tsx
│   │   └── LanguageSwitch.tsx
│   ├── artwork/
│   │   ├── ArtworkCard.tsx
│   │   ├── ArtworkGrid.tsx
│   │   ├── ArtworkDetail.tsx
│   │   ├── ArtworkFilter.tsx
│   │   └── Lightbox.tsx
│   ├── ui/
│   │   ├── Button.tsx
│   │   ├── Card.tsx
│   │   ├── Input.tsx
│   │   ├── Modal.tsx
│   │   └── Loading.tsx
│   └── forms/
│       ├── ContactForm.tsx
│       └── ClassInquiry.tsx
├── lib/                            # Utilities
│   ├── firebase/
│   │   ├── config.ts               # Firebase initialization
│   │   ├── firestore.ts            # Firestore helpers
│   │   ├── storage.ts              # Storage helpers
│   │   └── admin.ts                # Admin SDK (server-side)
│   ├── utils/
│   │   ├── date.ts
│   │   ├── image.ts
│   │   └── i18n.ts
│   └── constants/
│       ├── colors.ts
│       └── routes.ts
├── public/                         # Static files
│   ├── images/
│   ├── fonts/
│   └── favicon.ico
├── messages/                       # i18n translations
│   ├── en.json
│   └── fa.json
├── types/                          # TypeScript types
│   ├── artwork.ts
│   ├── exhibition.ts
│   └── global.d.ts
├── docs/                           # Documentation
│   ├── 01-site-structure.md
│   ├── 02-design-specifications.md
│   ├── 03-implementation-guide.md
│   ├── 04-bilingual-strategy.md
│   ├── 05-content-migration-plan.md
│   └── 06-project-idx-migration.md
├── .gitignore
├── .env.local                      # Environment variables
├── next.config.js
├── tailwind.config.js
├── tsconfig.json
├── firebase.json                   # Firebase config
├── firestore.rules                 # Firestore security
├── storage.rules                   # Storage security
├── package.json
└── README.md
```

---

## 🔧 Configuration Files

### next.config.js
```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  images: {
    domains: [
      'firebasestorage.googleapis.com',
      'sedaghat-art-center.firebasestorage.app'
    ],
    formats: ['image/webp', 'image/avif'],
  },
  i18n: {
    locales: ['en', 'fa'],
    defaultLocale: 'en',
  },
  experimental: {
    serverActions: true,
  },
}

module.exports = nextConfig
```

### tailwind.config.js
```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    './app/**/*.{js,ts,jsx,tsx,mdx}',
    './components/**/*.{js,ts,jsx,tsx,mdx}',
  ],
  theme: {
    extend: {
      colors: {
        primary: '#8B1E3F',
        secondary: '#D4AF37',
        background: '#FAF7F2',
        text: '#2C2C2C',
      },
      fontFamily: {
        serif: ['Playfair Display', 'Georgia', 'serif'],
        sans: ['Lato', 'Arial', 'sans-serif'],
        persian: ['Vazirmatn', 'Tahoma', 'sans-serif'],
      },
    },
  },
  plugins: [
    require('@tailwindcss/typography'),
    require('@tailwindcss/forms'),
  ],
}
```

### firebase.json
```json
{
  "hosting": {
    "public": "out",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ],
    "rewrites": [
      {
        "source": "**",
        "destination": "/index.html"
      }
    ],
    "headers": [
      {
        "source": "**/*.@(jpg|jpeg|gif|png|webp|avif)",
        "headers": [
          {
            "key": "Cache-Control",
            "value": "public, max-age=31536000, immutable"
          }
        ]
      }
    ]
  },
  "firestore": {
    "rules": "firestore.rules",
    "indexes": "firestore.indexes.json"
  },
  "storage": {
    "rules": "storage.rules"
  }
}
```

### .env.local (Template)
```bash
# Firebase Config
NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=sedaghat-art-center.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=sedaghat-art-center
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=sedaghat-art-center.firebasestorage.app
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id

# Admin SDK (Server-side only)
FIREBASE_SERVICE_ACCOUNT_KEY=./serviceAccountKey.json
```

---

## 🔥 Firebase Implementation

### lib/firebase/config.ts
```typescript
import { initializeApp, getApps } from 'firebase/app';
import { getFirestore } from 'firebase/firestore';
import { getStorage } from 'firebase/storage';
import { getAuth } from 'firebase/auth';

const firebaseConfig = {
  apiKey: process.env.NEXT_PUBLIC_FIREBASE_API_KEY,
  authDomain: process.env.NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN,
  projectId: process.env.NEXT_PUBLIC_FIREBASE_PROJECT_ID,
  storageBucket: process.env.NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET,
  messagingSenderId: process.env.NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID,
  appId: process.env.NEXT_PUBLIC_FIREBASE_APP_ID,
};

// Initialize Firebase (only once)
const app = getApps().length === 0 ? initializeApp(firebaseConfig) : getApps()[0];

export const db = getFirestore(app);
export const storage = getStorage(app);
export const auth = getAuth(app);
export default app;
```

### lib/firebase/firestore.ts
```typescript
import { 
  collection, 
  doc, 
  getDocs, 
  getDoc, 
  query, 
  where, 
  orderBy,
  limit 
} from 'firebase/firestore';
import { db } from './config';
import type { Artwork } from '@/types/artwork';

// Get all artworks
export async function getArtworks(): Promise<Artwork[]> {
  const artworksRef = collection(db, 'artworks');
  const snapshot = await getDocs(artworksRef);
  return snapshot.docs.map(doc => ({
    id: doc.id,
    ...doc.data()
  })) as Artwork[];
}

// Get artwork by ID
export async function getArtwork(id: string): Promise<Artwork | null> {
  const docRef = doc(db, 'artworks', id);
  const docSnap = await getDoc(docRef);
  
  if (docSnap.exists()) {
    return { id: docSnap.id, ...docSnap.data() } as Artwork;
  }
  return null;
}

// Get artworks by category
export async function getArtworksByCategory(
  category: string
): Promise<Artwork[]> {
  const q = query(
    collection(db, 'artworks'),
    where('category', '==', category),
    orderBy('createdAt', 'desc')
  );
  const snapshot = await getDocs(q);
  return snapshot.docs.map(doc => ({
    id: doc.id,
    ...doc.data()
  })) as Artwork[];
}

// Get featured artworks
export async function getFeaturedArtworks(): Promise<Artwork[]> {
  const q = query(
    collection(db, 'artworks'),
    where('featured', '==', true),
    limit(6)
  );
  const snapshot = await getDocs(q);
  return snapshot.docs.map(doc => ({
    id: doc.id,
    ...doc.data()
  })) as Artwork[];
}
```

### lib/firebase/storage.ts
```typescript
import { ref, uploadBytes, getDownloadURL } from 'firebase/storage';
import { storage } from './config';

// Upload image
export async function uploadImage(
  file: File,
  path: string
): Promise<string> {
  const storageRef = ref(storage, path);
  await uploadBytes(storageRef, file);
  return await getDownloadURL(storageRef);
}

// Get image URL
export async function getImageURL(path: string): Promise<string> {
  const storageRef = ref(storage, path);
  return await getDownloadURL(storageRef);
}

// Generate responsive image URLs
export function getResponsiveImageURLs(basePath: string) {
  return {
    thumbnail: `${basePath}_400x400`,
    medium: `${basePath}_800x800`,
    large: `${basePath}_1600x1600`,
    original: basePath,
  };
}
```

---

## 📝 TypeScript Types

### types/artwork.ts
```typescript
export interface Artwork {
  id: string;
  title: {
    en: string;
    fa: string;
  };
  description: {
    en: string;
    fa: string;
  };
  category: 'people' | 'landscapes' | 'objects';
  year: number;
  medium: string;
  dimensions: string;
  images: {
    thumbnail: string;
    medium: string;
    highRes: string;
  };
  price?: number;
  available: boolean;
  featured: boolean;
  tags?: string[];
  createdAt: Date;
  updatedAt: Date;
}

export interface ArtworkFilter {
  category?: string;
  featured?: boolean;
  available?: boolean;
  minYear?: number;
  maxYear?: number;
}
```

### types/exhibition.ts
```typescript
export interface Exhibition {
  id: string;
  title: {
    en: string;
    fa: string;
  };
  description: {
    en: string;
    fa: string;
  };
  startDate: Date;
  endDate: Date;
  location: string;
  artworks: string[]; // Artwork IDs
  images: string[];
  status: 'current' | 'upcoming' | 'past';
  createdAt: Date;
  updatedAt: Date;
}
```

---

## 🌍 Internationalization

### messages/en.json
```json
{
  "nav": {
    "home": "Home",
    "about": "About",
    "portfolio": "Portfolio",
    "exhibitions": "Exhibitions",
    "shop": "Shop",
    "contact": "Contact",
    "classes": "Classes"
  },
  "home": {
    "hero": "Where Art Meets Community",
    "featured": "Featured Artworks",
    "latest": "Latest Exhibitions"
  }
}
```

### messages/fa.json
```json
{
  "nav": {
    "home": "خانه",
    "about": "درباره ما",
    "portfolio": "نمونه کارها",
    "exhibitions": "نمایشگاه‌ها",
    "shop": "فروشگاه",
    "contact": "تماس با ما",
    "classes": "کلاس‌ها"
  },
  "home": {
    "hero": "جایی که هنر با جامعه ملاقات می‌کند",
    "featured": "آثار ویژه",
    "latest": "آخرین نمایشگاه‌ها"
  }
}
```

---

## 🎨 Component Examples

### components/artwork/ArtworkCard.tsx
```typescript
import Image from 'next/image';
import Link from 'next/link';
import type { Artwork } from '@/types/artwork';

interface ArtworkCardProps {
  artwork: Artwork;
  locale: 'en' | 'fa';
}

export default function ArtworkCard({ artwork, locale }: ArtworkCardProps) {
  return (
    <Link href={`/${locale}/portfolio/${artwork.id}`}>
      <div className="group relative overflow-hidden rounded-lg shadow-md hover:shadow-xl transition-shadow">
        <Image
          src={artwork.images.medium}
          alt={artwork.title[locale]}
          width={400}
          height={400}
          className="object-cover w-full h-full group-hover:scale-105 transition-transform duration-300"
        />
        <div className="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity">
          <div className="absolute bottom-0 left-0 right-0 p-4 text-white">
            <h3 className="font-serif text-xl mb-1">{artwork.title[locale]}</h3>
            <p className="text-sm opacity-90">{artwork.year} • {artwork.medium}</p>
          </div>
        </div>
      </div>
    </Link>
  );
}
```

---

## 🔐 Security Rules

### firestore.rules
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Artworks - public read, auth write
    match /artworks/{artwork} {
      allow read: if true;
      allow write: if request.auth != null;
    }
    
    // Exhibitions - public read, auth write
    match /exhibitions/{exhibition} {
      allow read: if true;
      allow write: if request.auth != null;
    }
    
    // Contact submissions - auth only
    match /contacts/{contact} {
      allow create: if true;
      allow read, update, delete: if request.auth != null;
    }
  }
}
```

### storage.rules
```
rules_version = '2';
service firebase.storage {
  match /b/{bucket}/o {
    match /artworks/{allPaths=**} {
      allow read: if true;
      allow write: if request.auth != null;
    }
    
    match /exhibitions/{allPaths=**} {
      allow read: if true;
      allow write: if request.auth != null;
    }
  }
}
```

---

## 🚀 Deployment Commands

```bash
# Build for production
npm run build

# Export static files
npm run export

# Deploy to Firebase
firebase deploy

# Deploy hosting only
firebase deploy --only hosting

# Deploy Firestore rules
firebase deploy --only firestore:rules

# Deploy Storage rules
firebase deploy --only storage
```

---

**Last Updated**: December 10, 2024
