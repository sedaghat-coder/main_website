# Sedaghat Art Center Website

A professional, bilingual (English/Persian) art gallery website built with Next.js and Firebase, showcasing the work of Hassan Sedaghat Baghbani.

---

## 🎨 Project Overview

**Live Site** (Coming Soon): https://sedaghat.art  
**Staging**: https://sedaghatartcenter.wordpress.com  
**Repository**: https://github.com/sedaghat-coder/main_website  
**Firebase Project**: sedaghat-art-center

### Mission
"Our goal is to provide an inclusive space for promoting art and education in the community. Sedaghat Art Center aims to create a space where people can come together to learn about art, practice meditation, and explore their creativity."

---

## 🏗️ Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Database**: Firebase Firestore
- **Storage**: Firebase Storage
- **Hosting**: Firebase Hosting
- **CDN**: Firebase CDN
- **Version Control**: Git/GitHub
- **Development**: Google Project IDX

---

## 📚 Complete Documentation

### Getting Started
1. **[Project IDX Migration Guide](docs/06-project-idx-migration.md)** - Start here for Project IDX setup
2. **[Quick Reference](docs/08-quick-reference.md)** - Fast lookup for common tasks
3. **[Getting Started](GETTING-STARTED.md)** - Original setup guide

### Architecture & Design
4. **[Site Structure](docs/01-site-structure.md)** - Complete page hierarchy and navigation
5. **[Design Specifications](docs/02-design-specifications.md)** - Colors, typography, UI components
6. **[Technical Specifications](docs/07-technical-specifications.md)** - Detailed implementation guide

### Implementation
7. **[Implementation Guide](docs/03-implementation-guide.md)** - Step-by-step build instructions
8. **[Bilingual Strategy](docs/04-bilingual-strategy.md)** - English/Persian content management
9. **[Content Migration Plan](docs/05-content-migration-plan.md)** - Migrating from Wix

---

## 🚀 Quick Start (Project IDX)

### 1. Open in Project IDX
```bash
# Go to https://idx.google.com/
# Import from GitHub: sedaghat-coder/main_website
# Select Next.js template
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Configure Firebase
```bash
# Copy service account key to workspace
# Update .env.local with Firebase config
```

### 4. Run Development Server
```bash
npm run dev
```

### 5. Build & Deploy
```bash
npm run build
firebase deploy
```

---

## 📁 Project Structure

```
main_website/
├── app/                      # Next.js App Router
│   └── [locale]/            # Bilingual pages (en/fa)
├── components/              # React components
│   ├── layout/             # Header, Footer, Nav
│   ├── artwork/            # Gallery components
│   └── ui/                 # Reusable UI
├── lib/                    # Utilities
│   ├── firebase/           # Firebase config
│   └── utils/              # Helper functions
├── public/                 # Static assets
├── docs/                   # Documentation
│   ├── 01-site-structure.md
│   ├── 02-design-specifications.md
│   ├── 03-implementation-guide.md
│   ├── 04-bilingual-strategy.md
│   ├── 05-content-migration-plan.md
│   ├── 06-project-idx-migration.md
│   ├── 07-technical-specifications.md
│   └── 08-quick-reference.md
└── types/                  # TypeScript types
```

---

## 🎨 Design System

### Colors
- **Primary**: #8B1E3F (Rich Burgundy) - Buttons, links, highlights
- **Secondary**: #D4AF37 (Soft Gold) - Accents, icons
- **Background**: #FAF7F2 (Warm Cream) - Main background
- **Text**: #2C2C2C (Deep Charcoal) - All text

### Typography
- **Headings**: Playfair Display (Elegant serif)
- **Body**: Lato (Clean sans-serif)
- **Persian**: Vazirmatn (Persian-optimized)

### Responsive Breakpoints
- Mobile: < 768px
- Tablet: 768px - 1199px
- Desktop: 1200px+

---

## 🌍 Features

### Core Features
✅ Bilingual (English/Persian) with RTL support  
✅ 40+ artwork portfolio with filtering  
✅ High-resolution image optimization  
✅ Exhibition management  
✅ Online shop with Stripe integration  
✅ Contact forms  
✅ Class information & registration  
✅ Responsive design (mobile-first)  
✅ SEO optimized  
✅ Fast performance (Firebase CDN)  

### Coming Soon
🔄 Admin panel for content management  
🔄 User authentication  
🔄 Newsletter subscription  
🔄 Blog/News section  
🔄 Virtual gallery tours  
🔄 Online class booking  

---

## 👨‍🎨 About the Artist

**Hassan Sedaghat Baghbani**
- Main Artist and Teacher
- Email: artist.hassan@sedaghat.art
- Born: April 1970, Iran
- Specialization: Oil Painting
- Master Teacher: Khoshsefat (3 years)
- Member: Mashhad Visual Arts Association
- Education: Espehbadi School, Iran

Hassan blends realism and expressionism in his oil paintings, drawing inspiration from Persian masters while developing his unique style. He teaches private oil painting classes and believes in the continuous journey of artistic growth.

---

## 🤝 Team

- **Hassan Sedaghat Baghbani** - Main Artist & Teacher
- **Sina Sedaghat** - Website Developer & Maintainer
- **Artistic Advisor** - TBD

---

## 📊 Project Status

### ✅ Completed
- [x] Repository initialized
- [x] Complete documentation (8 guides)
- [x] Design system defined
- [x] Firebase project created
- [x] Technical architecture planned
- [x] Migration to Project IDX prepared

### 🚧 In Progress
- [ ] Next.js project setup
- [ ] Firebase integration
- [ ] Component development
- [ ] Content migration

### 📅 Timeline
- **Week 1**: Core structure & design implementation
- **Week 2**: Gallery & Firestore integration
- **Week 3**: Additional pages & bilingual setup
- **Week 4**: Testing, optimization & launch

---

## 💰 Cost Estimate

### Firebase Free Tier (Expected)
- **Storage**: ~300MB (under 10GB limit) - **FREE**
- **Bandwidth**: ~30GB/month - **FREE** (under 360MB/day limit)
- **Hosting**: Unlimited - **FREE**
- **Firestore**: 50K reads/day - **FREE**

**Expected Cost**: $0/month  
**Worst Case**: ~$5/month with high traffic

---

## 🚀 Deployment

### Development
```bash
npm run dev
# Open http://localhost:3000
```

### Production Build
```bash
npm run build
npm run start
```

### Deploy to Firebase
```bash
firebase login
firebase use sedaghat-art-center
firebase deploy
```

### Custom Domain
Once deployed, connect `sedaghat.art` through Firebase Hosting settings.

---

## 📝 Content Management

### Adding Artworks
1. Upload images to Firebase Storage: `/artworks/[id]/`
2. Add document to Firestore: `artworks` collection
3. Include both English and Persian metadata

### Updating Exhibitions
1. Add document to Firestore: `exhibitions` collection
2. Link artwork IDs
3. Set status: current/upcoming/past

### Managing Content
- Use Firebase Console for data management
- Admin panel (coming soon) for easier updates
- Direct Firestore access for bulk operations

---

## 🔐 Security

### Environment Variables
Never commit:
- `.env.local`
- `serviceAccountKey.json`
- `.firebase/` directory

### Firestore Rules
- Public read access for artworks and exhibitions
- Authenticated write access only
- See `firestore.rules` for details

### Storage Rules
- Public read access for artwork images
- Authenticated write access only
- See `storage.rules` for details

---

## 🐛 Troubleshooting

### Common Issues

**Firebase Connection Failed**
- Check `.env.local` configuration
- Verify Firebase project ID
- Ensure service account key is valid

**Build Errors**
```bash
rm -rf .next node_modules
npm install
npm run dev
```

**Images Not Loading**
- Check Firebase Storage rules
- Verify image URLs in Firestore
- Add domain to `next.config.js`

---

## 📞 Support

### Documentation
All documentation is in `/docs` directory - start there!

### Firebase Console
- **Firestore**: https://console.firebase.google.com/project/sedaghat-art-center/firestore
- **Storage**: https://console.firebase.google.com/project/sedaghat-art-center/storage
- **Hosting**: https://console.firebase.google.com/project/sedaghat-art-center/hosting

### Getting Help
- Check documentation first
- Use AI assistant in Project IDX
- Review code examples in technical specs
- Ask specific questions with context

---

## 📄 License

This project is proprietary and confidential.  
© 2024-2025 Sedaghat Art Center. All rights reserved.

---

## 🙏 Acknowledgments

- **Artist**: Hassan Sedaghat Baghbani
- **Development**: Built with Claude (Anthropic)
- **Tools**: Next.js, Firebase, Tailwind CSS
- **Platform**: Google Project IDX
- **Hosting**: Firebase Hosting

---

## 🔗 Links

- **GitHub**: https://github.com/sedaghat-coder/main_website
- **Firebase Console**: https://console.firebase.google.com/project/sedaghat-art-center
- **Project IDX**: https://idx.google.com/
- **Current Wix Site**: https://sedaghatart.wixsite.com/home
- **WordPress Staging**: https://sedaghatartcenter.wordpress.com

---

**Built with ❤️ for art and community**

**Last Updated**: December 10, 2024  
**Version**: 1.0.0  
**Status**: 🚧 In Development
