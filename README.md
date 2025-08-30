# Edge Mining Documentation Repository

This repository contains **only the documentation content** (Markdown files) for the Edge Mining website. The live site at [edgemining.energy](https://edgemining.energy) is automatically built and deployed via GitHub Actions.

## 🏗️ Repository Structure

### **This Repository (`bitsalv/edgemining-docs`):**
```
edgemining-docs/
├── docs/                      # Documentation content ONLY
│   ├── intro.md              # Introduction
│   ├── about-us.md           # About Edge Mining
│   ├── product/              # Product documentation
│   │   └── product-cycle.md
│   ├── modelling/            # Architecture & DDD
│   │   ├── README.md
│   │   ├── domain-driven-architecture-overview.md
│   │   └── glossary.md
│   ├── contribution.md       # How to contribute
│   └── faq.md               # Frequently asked questions
├── images/                   # Documentation images
└── .github/workflows/        # Sync workflow
```

### **Site Repository (`bitsalv/edgemining.energy`):**
```
edgemining.energy/
├── docs/                     # VuePress site (synced from this repo)
│   ├── .vuepress/           # VuePress configuration
│   │   ├── config.js        # Site configuration
│   │   ├── styles/          # Custom CSS styles
│   │   └── public/          # Static assets (logo, favicon)
│   ├── docs/                # Documentation content (synced from this repo)
│   └── README.md            # Homepage content
├── package.json             # Dependencies and scripts
└── .github/workflows/       # Build and deploy workflows
```

## 🔄 Automatic Deployment Workflow

### **Two-Way Sync Process:**

#### **1. Content Changes (this repo):**
- **Push to `bitsalv/edgemining-docs`** → Triggers sync workflow
- **Copies `docs/`** → `bitsalv/edgemining.energy/docs/`
- **Triggers build** → Deploys to `edgemining.energy`

#### **2. Site Changes (edgemining.energy repo):**
- **Push to `bitsalv/edgemining.energy`** → Triggers build workflow
- **Builds VuePress** → Deploys to `edgemining.energy`

## 🛠️ Setup Required

### **1. Repository Token**
In the `bitsalv/edgemining-docs` repository, add this secret:
```
EDGEMINING_ENERGY_TOKEN = Personal Access Token with permissions on edgemining.energy
```

### **2. Repository Permissions**
The token must have access to:
- `bitsalv/edgemining-docs` (read)
- `bitsalv/edgemining.energy` (read/write)

## 📝 Current Status

### **✅ Completed:**
- [x] Documentation content structure (intro, about, product, modelling, contribution, FAQ)
- [x] GitHub Actions workflow for content sync
- [x] VuePress site configuration (in edgemining.energy)
- [x] Custom CSS styling with Edge Mining brand colors
- [x] Logo and favicon from Edge Mining organization
- [x] Navigation structure (Home, Docs, Discord, GitHub)
- [x] Fixed broken links in documentation
- [x] Synchronized content between repositories

### **⚠️ Pending:**
- [ ] Configure `EDGEMINING_ENERGY_TOKEN` secret for automatic sync
- [ ] Test deployment workflow
- [ ] Content review and finalization

## 🔧 Local Development

### **For Content Development (this repo):**
```bash
# Edit Markdown files in docs/
# Push to trigger automatic sync (when token is configured)
```

### **For Site Development (edgemining.energy repo):**
```bash
cd edgemining.energy
npm run docs:dev      # Development server
npm run docs:build    # Production build
npm run docs:clean    # Clean build
```

### **Access:**
- **Development**: `http://localhost:8080/` (from edgemining.energy repo)
- **Production**: `https://edgemining.energy`

## 📋 Setup Checklist

### **For `bitsalv/edgemining-docs`:**
- [x] Repository structure corrected
- [x] Documentation links fixed
- [ ] Add `EDGEMINING_ENERGY_TOKEN` secret
- [ ] Configure repository permissions
- [ ] Test content sync workflow

### **For `bitsalv/edgemining.energy`:**
- [x] VuePress configuration complete
- [x] Build workflow functional
- [ ] Enable GitHub Pages
- [ ] Configure custom domain `edgemining.energy`
- [ ] Set up CNAME file

## 🎯 Next Steps

1. **Configure GitHub Secrets** for automatic sync
2. **Test deployment workflow**
3. **Review and finalize content**
4. **Enable GitHub Pages** with custom domain

## 📚 Documentation Files

- **`docs/`** → All documentation content (this repo)
- **VuePress configuration** → In edgemining.energy repo
- **Deployment workflows** → In both repositories

---

**Note**: This repository contains ONLY the documentation content. The VuePress site and deployment infrastructure are in the `bitsalv/edgemining.energy` repository. 