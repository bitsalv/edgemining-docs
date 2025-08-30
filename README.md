# Edge Mining Documentation Repository

This repository contains **only the documentation content** (Markdown files) for the Edge Mining website. The live site at [edgemining.energy](https://edgemining.energy) is automatically built and deployed from the [edge-mining/edgemining.energy](https://github.com/edge-mining/edgemining.energy) repository.

## 🎯 For Documentation Editors

This repository is specifically for **editing and maintaining the documentation content**. All documentation changes should be made here and will be automatically synced to the website repository.

> **📝 For Editors**: This repository is for **content editing** - writing, updating, and maintaining documentation. If you're a **developer** making technical changes to the website, use the [edge-mining/edgemining.energy](https://github.com/edge-mining/edgemining.energy) repository instead.

## 📁 Repository Structure

```
docs/
├── intro.md              # Introduction
├── about-us.md           # About Edge Mining
├── product/              # Product documentation
│   └── product-cycle.md
├── modelling/            # Architecture & DDD
│   ├── README.md
│   ├── domain-driven-architecture-overview.md
│   └── glossary.md
├── contribution.md       # How to contribute
└── faq.md               # Frequently asked questions
```

## 🔄 Workflow for Documentation Changes

### **How to Contribute:**

1. **Edit Documentation**: Modify Markdown files in the `docs/` directory
2. **Test Locally**: Use the VuePress site to preview changes
3. **Commit Changes**: Push to this repository
4. **Automatic Sync**: Changes are automatically synced to [edge-mining/edgemining.energy](https://github.com/edge-mining/edgemining.energy)
5. **Live Update**: Website is automatically updated at [edgemining.energy](https://edgemining.energy)

### **Repository Relationships:**

```
Documentation Repository (edge-mining/docs) - FOR EDITORS
    ↓ (Auto-sync)
Website Repository (edge-mining/edgemining.energy) - FOR DEVELOPERS
    ↓ (Auto-deploy)
Live Site (edgemining.energy)
```

## 🛠️ Local Development

### **For Documentation Editing:**

```bash
# Clone this repository
git clone https://github.com/edge-mining/docs.git
cd docs

# Edit Markdown files in docs/
# Test with VuePress (see below)
# Commit and push changes
```

### **For Preview with VuePress:**

```bash
# Navigate to the website repository
cd ../edgemining.energy

# Install dependencies
npm install

# Start development server
npm run docs:dev

# View at http://localhost:8080
```

## 📝 Documentation Guidelines

### **File Organization:**
- **`docs/intro.md`**: Project introduction and overview
- **`docs/about-us.md`**: Mission, values, and team information
- **`docs/product/`**: Product-specific documentation
- **`docs/modelling/`**: Architecture and technical documentation
- **`docs/contribution.md`**: How to contribute to the project
- **`docs/faq.md`**: Frequently asked questions

### **Markdown Standards:**
- Use relative links: `./about-us.md` instead of `/docs/about-us.html`
- Include proper frontmatter for VuePress
- Follow consistent formatting and structure
- Update table of contents when adding new pages

## 🔗 Important Links

- **Website Repository**: [edge-mining/edgemining.energy](https://github.com/edge-mining/edgemining.energy) (for developers)
- **Live Website**: [edgemining.energy](https://edgemining.energy)
- **Community**: [Discord](https://discord.com/invite/VQa9UY5SsS)

## ⚠️ Important Notes

- **Auto-sync**: Changes here are automatically synced to the website repository
- **No direct editing**: Don't edit the website repository directly for documentation changes
- **Immediate deployment**: Changes appear on the live site after sync
- **Editor-focused**: This repository is for content editors, not developers

## 🎯 Next Steps for Contributors

1. **Fork this repository** (if you haven't already)
2. **Make your changes** to the documentation
3. **Test locally** using the VuePress development server
4. **Create a Pull Request** to this repository
5. **Wait for review and merge**
6. **Changes will automatically appear** on the live site

---

**Note**: This repository is for documentation content only. The VuePress website and deployment infrastructure are in the [edge-mining/edgemining.energy](https://github.com/edge-mining/edgemining.energy) repository. 