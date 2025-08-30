# Repository Structure Guide

## 🎯 Overview

Edge Mining uses **two separate repositories** for the documentation system:

1. **`edge-mining/docs`** → Content repository (Markdown files only)
2. **`edge-mining/edgemining.energy`** → Site repository (VuePress + deployment)

## 📁 Repository Details

### **1. edge-mining/docs (Content Repository)**

**Purpose**: Store only the documentation content in Markdown format.

**Structure**:
```
edge-mining/docs/
├── .github/workflows/
│   └── sync-docs.yml          # Syncs content to edgemining.energy
├── docs/                      # Documentation content ONLY
│   ├── intro.md              # Introduction
│   ├── about-us.md           # About Edge Mining
│   ├── product/              # Product documentation
│   │   └── product-cycle.md
│   ├── modelling/            # Architecture & DDD
│   │   ├── domain-driven-architecture-overview.md
│   │   └── glossary.md
│   ├── contribution.md       # How to contribute
│   └── faq.md               # Frequently asked questions
└── README.md                 # Repository documentation
```

**Workflow**: 
- Push to `main` → Triggers sync to `edgemining.energy/docs/`
- Only syncs the `docs/` directory content

### **2. edge-mining/edgemining.energy (Site Repository)**

**Purpose**: VuePress site with full deployment infrastructure.

**Structure**:
```
edge-mining/edgemining.energy/
├── .github/workflows/
│   └── build-and-deploy.yml   # Builds and deploys the site
├── docs/                      # VuePress site (synced from edge-mining/docs)
│   ├── .vuepress/            # VuePress configuration
│   │   ├── config.js         # Site configuration
│   │   ├── styles/           # Custom CSS styles
│   │   └── public/           # Static assets (logo, favicon)
│   ├── docs/                 # Documentation content (synced from edge-mining/docs)
│   └── README.md             # Homepage content
├── package.json              # Dependencies and scripts
└── CNAME                     # Custom domain configuration
```

**Workflow**:
- Push to `main` → Builds VuePress → Deploys to `edgemining.energy`
- Receives content updates from `edge-mining/docs`

## 🔄 Workflow Process

### **Content Updates (edge-mining/docs):**
1. **Edit** Markdown files in `docs/`
2. **Push** to `edge-mining/docs`
3. **GitHub Action** copies `docs/` to `edge-mining/edgemining.energy/docs/`
4. **Triggers build** in `edgemining.energy`
5. **Deploys** to `edgemining.energy`

### **Site Updates (edge-mining/edgemining.energy):**
1. **Edit** VuePress config, styles, or other site files
2. **Push** to `edge-mining/edgemining.energy`
3. **GitHub Action** builds VuePress
4. **Deploys** to `edgemining.energy`

## 🛠️ Development Workflow

### **For Content Writers:**
- **Repository**: `edge-mining/docs`
- **Work on**: `docs/` directory
- **Result**: Automatic sync and deployment

### **For Site Developers:**
- **Repository**: `edge-mining/edgemining.energy`
- **Work on**: VuePress config, styles, assets
- **Result**: Direct deployment

## 🔐 Required Setup

### **edge-mining/docs:**
- `EDGEMINING_ENERGY_TOKEN` secret for cross-repo access

### **edge-mining/edgemining.energy:**
- GitHub Pages enabled
- Custom domain `edgemining.energy`
- CNAME file configured

## 📋 Benefits of This Structure

1. **Separation of Concerns**: Content vs. presentation
2. **Content Focus**: Writers only deal with Markdown
3. **Site Flexibility**: Developers can modify site without touching content
4. **Automatic Sync**: Content changes automatically update the site
5. **Independent Deployment**: Site changes deploy immediately

## 🎯 Pull Request Strategy

### **Content Changes:**
- **PR to**: `edge-mining/docs`
- **Scope**: Only `docs/` directory changes
- **Result**: Automatic sync to site

### **Site Changes:**
- **PR to**: `edge-mining/edgemining.energy`
- **Scope**: VuePress config, styles, assets
- **Result**: Direct deployment

---

**Note**: This structure ensures clean separation between content management and site development while maintaining automatic synchronization.
