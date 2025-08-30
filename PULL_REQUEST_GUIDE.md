# Pull Request Guide

## 🎯 Overview

This repository (`edge-mining/docs`) contains **only the documentation content** for the Edge Mining website. The VuePress site and deployment infrastructure are in `edge-mining/edgemining.energy`.

## 📋 Pull Request Checklist

### **For `edge-mining/docs` (Content Repository):**

#### **Files to Include:**
- [ ] `.github/workflows/sync-docs.yml` - Content sync workflow
- [ ] `docs/` - All documentation content
- [ ] `README.md` - Repository documentation
- [ ] `REPOSITORY_STRUCTURE.md` - Structure explanation
- [ ] `LICENSE` - MIT license
- [ ] `.gitignore` - Git ignore rules

#### **Files NOT to Include:**
- ❌ `package.json` (not needed for content repo)
- ❌ `node_modules/` (not needed for content repo)
- ❌ VuePress configuration (goes in edgemining.energy repo)
- ❌ Build files (handled by edgemining.energy repo)

#### **Setup Required:**
- [ ] Add `EDGEMINING_ENERGY_TOKEN` secret to repository
- [ ] Configure repository permissions for cross-repo access

### **For `edge-mining/edgemining.energy` (Site Repository):**

#### **Files to Include:**
- [ ] `.github/workflows/build-and-deploy.yml` - Build and deploy workflow
- [ ] `docs/.vuepress/` - VuePress configuration
- [ ] `docs/docs/` - Documentation content (synced from edge-mining/docs)
- [ ] `package.json` - Dependencies and scripts
- [ ] `CNAME` - Custom domain configuration
- [ ] `.gitignore` - Git ignore rules

#### **Setup Required:**
- [ ] Enable GitHub Pages
- [ ] Configure custom domain `edgemining.energy`
- [ ] Set up CNAME file

## 🔄 Workflow Process

### **Content Updates:**
1. **Edit** Markdown files in `docs/`
2. **Push** to `edge-mining/docs`
3. **GitHub Action** copies `docs/` to `edge-mining/edgemining.energy/docs/`
4. **Triggers build** in `edgemining.energy`
5. **Deploys** to `edgemining.energy`

### **Site Updates:**
1. **Edit** VuePress config, styles, or other site files
2. **Push** to `edge-mining/edgemining.energy`
3. **GitHub Action** builds VuePress
4. **Deploys** to `edgemining.energy`

## 📝 PR Messages

### **For edge-mining/docs:**
```markdown
# 📚 Documentation Content Setup

## Overview
This PR sets up the content repository for Edge Mining documentation with automatic sync to the site repository.

## What's Included
- Documentation content structure (intro, about, product, modelling, contribution, FAQ)
- GitHub Actions workflow for content synchronization
- Repository documentation and structure guide

## Workflow
- Push to `main` → Syncs content to `edge-mining/edgemining.energy`
- Content writers work only with Markdown files
- Automatic deployment via cross-repository sync

## Setup Required
1. Add `EDGEMINING_ENERGY_TOKEN` secret
2. Configure repository permissions
3. Test content sync workflow

## Next Steps
1. Create PR for `edge-mining/edgemining.energy` (VuePress site)
2. Configure deployment infrastructure
3. Test complete workflow
```

### **For edge-mining/edgemining.energy:**
```markdown
# 🌐 VuePress Site Setup

## Overview
This PR sets up the VuePress site repository for Edge Mining with automatic deployment to edgemining.energy.

## What's Included
- VuePress 2 configuration with custom styling
- GitHub Actions workflow for build and deployment
- Custom CSS with Edge Mining brand colors
- Logo and favicon from Edge Mining organization
- Responsive design for mobile and desktop

## Workflow
- Push to `main` → Builds VuePress → Deploys to edgemining.energy
- Receives content updates from `edge-mining/docs`
- Independent deployment for site changes

## Setup Required
1. Enable GitHub Pages
2. Configure custom domain `edgemining.energy`
3. Set up CNAME file
4. Test deployment workflow

## Next Steps
1. Configure content sync from `edge-mining/docs`
2. Test complete deployment workflow
3. Review and finalize content
```

## 🎯 Repository Structure

### **edge-mining/docs (Content):**
```
docs/
├── intro.md
├── about-us.md
├── product/
├── modelling/
├── contribution.md
└── faq.md
```

### **edge-mining/edgemining.energy (Site):**
```
docs/
├── .vuepress/          # VuePress configuration
├── docs/              # Content (synced from edge-mining/docs)
└── README.md          # Homepage
```

---

**Note**: This guide ensures proper separation between content management and site development.
