# KNA — Khandakar Nakibul Akhter · Personal Marketing Website

> A fully custom, single-file personal website for **Khandakar Nakibul Akhter** — Meta Ads Strategist & Digital Marketing Expert based in Bangladesh.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Live Preview](#live-preview)
- [Features](#features)
- [Page Sections](#page-sections)
- [Tech Stack](#tech-stack)
- [File Structure](#file-structure)
- [How to Deploy](#how-to-deploy)
- [Customization Guide](#customization-guide)
- [Known Behaviors](#known-behaviors)
- [Contact](#contact)

---

## Overview

This is a **zero-dependency, single HTML file** personal portfolio and service website. No frameworks, no build tools, no backend — just drop the file on any static host and it works.

Built to convert visitors into clients through:
- Clear service offerings and transparent pricing
- Real case study results (BD Fishing Store — 1.72M BDT revenue)
- Direct WhatsApp booking integration
- Professional photo, logo, and signature branding

---

## Live Preview

Open `index.html` directly in any browser — no server required.

```bash
# Option 1: Just double-click index.html
# Option 2: Serve locally
npx serve .
# or
python3 -m http.server 8080
```

---

## Features

### ✅ Functionality
| Feature | Details |
|---|---|
| 📦 Expandable Package Details | Click "See Full Service Details" on any package to reveal the full breakdown |
| 📊 Case Study Modal | Click "View Case Study" on BD Fishing Store card to open a full metrics popup |
| 📬 Contact Form → WhatsApp | Form submission opens WhatsApp pre-filled with the client's message |
| 🍔 Mobile Hamburger Nav | Fully animated slide-in menu for screens under 768px |
| 🟢 WhatsApp Float Button | Sticky bottom-left button for instant chat on all pages |
| 🔦 Active Nav Highlight | Current section is highlighted in teal as you scroll |
| ✨ Scroll Reveal Animations | Cards and elements fade in as they enter the viewport |
| 🔔 Toast Notification | Confirmation message after form submission |
| ⌨️ Keyboard Accessible Modal | Press `Escape` or click outside to close the case study modal |

### 🎨 Design
- **Dark theme** with teal (`#00d4b8`) and purple (`#7c3aed`) accent gradient
- **Fonts:** Syne (headings) + DM Sans (body) via Google Fonts
- **Fully responsive** — tested at 375px, 768px, 1280px, 1440px
- All images (logos, photos, signature) embedded as **base64** — no broken image links ever

### 🔍 SEO
- Custom `<title>` with full keyword phrase
- `<meta name="description">` optimized for search
- Open Graph tags (`og:title`, `og:description`, `og:type`)
- Emoji favicon (📈)
- Semantic HTML sections with proper `id` anchors

---

## Page Sections

| # | Section | Nav Label | Anchor |
|---|---|---|---|
| 1 | Hero — Headline + CTA + Photo | *(top)* | `#home` |
| 2 | Services — 6 service cards | Services | `#services` |
| 3 | Packages — 3 pricing tiers | Packages | `#packages` |
| 4 | Case Study — BD Fishing Store | Results | `#results` |
| 5 | About Me — Bio + Photo + Signature | About | `#about` |
| 6 | Clients — 4 client logos | Clients | `#clients` |
| 7 | How It Works — 4-step process | Process | `#how` |
| 8 | Payment Options | Payment | `#payment` |
| 9 | Refund & Cancellation Policy | Refund Policy | `#refund` |
| 10 | Booking / Contact Form | Contact | `#booking` |
| 11 | Terms & Conditions | Terms | `#terms` |
| 12 | Footer | — | — |

---

## Tech Stack

```
HTML5          — Structure & content
CSS3           — All styling (variables, grid, flexbox, animations)
Vanilla JS     — All interactivity (no jQuery, no frameworks)
Google Fonts   — Syne + DM Sans (loaded via CDN)
Base64 Images  — All images embedded inline (no external image hosting needed)
```

**Zero npm. Zero build step. Zero dependencies.**

---

## File Structure

```
project/
│
└── index.html          ← The entire website (single file, ~2.2MB with embedded images)
└── README.md           ← This file
```

> **Why one file?** Portability. Share it as an email attachment, drop it on GitHub Pages, Netlify, or any cPanel file manager — it works everywhere without configuration.

---

## How to Deploy

### Option 1 — GitHub Pages (Free)
```bash
1. Create a new GitHub repository
2. Upload index.html to the root
3. Go to Settings → Pages → Source: main branch / root
4. Your site is live at: https://yourusername.github.io/repo-name
```

### Option 2 — Netlify (Free, Custom Domain Support)
```bash
1. Go to netlify.com → "Deploy manually"
2. Drag and drop the index.html file
3. Done — live in seconds with a .netlify.app URL
```

### Option 3 — Hostinger / cPanel
```bash
1. Log into your hosting control panel
2. Open File Manager → public_html
3. Upload index.html
4. Visit yourdomain.com
```

### Option 4 — Local (No Internet)
```bash
# Just open the file
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

> ⚠️ **Note:** Google Fonts require an internet connection. Offline, the page will fallback to system sans-serif fonts — layout remains intact.

---

## Customization Guide

All content is in a single HTML file. Use browser Find (`Ctrl+F` / `Cmd+F`) to locate and edit.

### Update Contact Info
| What | Search For | Replace With |
|---|---|---|
| WhatsApp number | `01912420201` | Your number |
| Email address | `nakibulo@gmail.com` | Your email |
| WA link | `wa.me/8801912420201` | `wa.me/88YOURNUMBER` |

### Update Pricing
| Package | Search For |
|---|---|
| Quick Fix | `4,000 BDT` |
| Growth | `12,000 BDT` |
| All-In | `20,000 BDT` |

### Update Bank Details
Search for `Midland Bank` to find the payment section.

### Replace Photos
All photos are base64-encoded `<img>` tags. To update:
```python
import base64

with open('your-photo.jpg', 'rb') as f:
    b64 = base64.b64encode(f.read()).decode()

# Then replace the base64 string inside src="data:image/jpeg;base64,..."
```

### Add/Remove a Client Card
Find `class="client-card"` in the Clients section. Copy one card block and modify the name, description, tags, and logo image.

### Change Theme Color
At the top of `<style>`, find:
```css
:root {
  --teal: #00d4b8;
  --purple: #7c3aed;
  --gold: #f59e0b;
}
```
Change `--teal` to any hex color to update the entire accent theme instantly.

---

## Known Behaviors

| Behavior | Explanation |
|---|---|
| Large file size (~2.2MB) | All images are embedded as base64. No external image requests = no broken images ever. Trade-off is file size. |
| Google Fonts may not load offline | Fonts load from `fonts.googleapis.com`. Offline fallback is system sans-serif. |
| Form doesn't send email | By design — form opens WhatsApp instead (more direct for a freelancer). To add email, integrate [Formspree](https://formspree.io) or [EmailJS](https://emailjs.com). |
| No analytics | Add Google Analytics or Plausible by inserting their script tag before `</body>`. |

---

## Clients Featured

| Client | Industry | Service |
|---|---|---|
| BD Fishing Store | E-Commerce | Meta Ads, Retargeting — **1.72M BDT revenue** on $1,000 budget |
| Royan Apparels | Garment Buying House (B2B) | Meta Ads, B2B Lead Generation |
| Four Seasons BD | *(Active)* | Full Funnel Campaign Management |
| BD Gadget Hub | Gadgets / E-Commerce | Meta Ads, Product Sales |

---

## Contact

**Khandakar Nakibul Akhter**
Digital Marketing Expert & Meta Ads Strategist

- 📧 Email: [nakibulo@gmail.com](mailto:nakibulo@gmail.com)
- 💬 WhatsApp: [+880 1912 420201](https://wa.me/8801912420201)
- 📍 Location: Bangladesh *(Remote-friendly)*

---

*Built with ❤️ — pure HTML, CSS & JavaScript. No frameworks harmed in the making of this website.*
