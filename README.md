# Edge Mining Documentation Repository

This repository contains **only the documentation content** (Markdown files) for the Edge Mining website. The live site at [edgemining.energy](https://edgemining.energy) is automatically built and deployed via GitHub Actions.

## 🏗️ Repository Structure

### **This Repository (`edge-mining/docs`):**
```
edge-mining/docs/
└── docs/                      # Documentation content ONLY
    ├── intro.md              # Introduction
    ├── about-us.md           # About Edge Mining
    ├── product/              # Product documentation
    │   └── product-cycle.md
    ├── modelling/            # Architecture & DDD
    │   ├── domain-driven-architecture-overview.md
    │   └── glossary.md
    ├── contribution.md       # How to contribute
    └── faq.md               # Frequently asked questions
```

### **Site Repository (`edge-mining/edgemining.energy`):**
```
edge-mining/edgemining.energy/
├── docs/                     # VuePress site (copied from this repo)
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
- **Push to `edge-mining/docs`** → Triggers sync workflow
- **Copies `docs/`** → `edge-mining/edgemining.energy/docs/`
- **Triggers build** → Deploys to `edgemining.energy`

#### **2. Site Changes (edgemining.energy repo):**
- **Push to `edge-mining/edgemining.energy`** → Triggers build workflow
- **Builds VuePress** → Deploys to `edgemining.energy`

## 🛠️ Setup Required

### **1. Repository Token**
In the `edge-mining/docs` repository, add this secret:
```
EDGEMINING_ENERGY_TOKEN = Personal Access Token with permissions on edgemining.energy
```

### **2. Repository Permissions**
The token must have access to:
- `edge-mining/docs` (read)
- `edge-mining/edgemining.energy` (read/write)

## 📝 Current Status

### **✅ Completed:**
- [x] Documentation content structure (intro, about, product, modelling, contribution, FAQ)
- [x] GitHub Actions workflow for content sync
- [x] VuePress site configuration (in edgemining.energy)
- [x] Custom CSS styling with Edge Mining brand colors
- [x] Logo and favicon from Edge Mining organization
- [x] Navigation structure (Home, Docs, Discord, GitHub)

### **⚠️ Pending:**
- [ ] Content review and finalization
- [ ] Visual design improvements
- [ ] Testing of deployment workflow

## 🔧 Local Development

### **For Content Development (this repo):**
```bash
# Edit Markdown files in docs/
# Push to trigger automatic sync
```

### **For Site Development (edgemining.energy repo):**
```bash
npm run docs:dev      # Development server
npm run docs:build    # Production build
npm run docs:clean    # Clean build
```

### **Access:**
- **Development**: `http://localhost:8080/` (from edgemining.energy repo)
- **Production**: `https://edgemining.energy`

## 📋 Pull Request Checklist

### **For `edge-mining/docs`:**
- [ ] Add `EDGEMINING_ENERGY_TOKEN` secret
- [ ] Configure repository permissions
- [ ] Test content sync workflow

### **For `edge-mining/edgemining.energy`:**
- [ ] Enable GitHub Pages
- [ ] Configure custom domain `edgemining.energy`
- [ ] Set up CNAME file
- [ ] Configure repository permissions

## 🎯 Next Steps

1. **Create Pull Request** for `edge-mining/docs` (content only)
2. **Create Pull Request** for `edge-mining/edgemining.energy` (VuePress site)
3. **Configure secrets** and permissions
4. **Test deployment workflow**
5. **Review and finalize content**

## 📚 Documentation Files

- **`docs/docs/`** → All documentation content (this repo)
- **VuePress configuration** → In edgemining.energy repo
- **Deployment workflows** → In both repositories

---

**Note**: This repository contains ONLY the documentation content. The VuePress site and deployment infrastructure are in the `edge-mining/edgemining.energy` repository. 