# 🛍️ ShopNova — E-Commerce Website

A fully functional Amazon-style e-commerce frontend built with pure HTML, CSS, and JavaScript.
No frameworks, no build tools — just open `index.html` in a browser.

---

## 📁 Project Structure

```
shopnova/
├── index.html              ← Main entry point (open this)
│
├── css/
│   ├── variables.css       ← CSS custom properties, reset, keyframes, utilities
│   ├── navbar.css          ← Navbar, search bar, suggestions, user dropdown, auth form
│   ├── layout.css          ← Hero, categories, product grid, deals banner, footer
│   └── components.css      ← Modal, cart panel, checkout, toasts, order success
│
├── js/
│   ├── app.js              ← Global state, theme toggle, page routing, toast, timer
│   ├── auth.js             ← Login / Signup form logic, validation, localStorage
│   ├── cart.js             ← Cart CRUD, totals, localStorage, slide-in panel
│   ├── products.js         ← Product cards, filtering, search, modal, wishlist, ratings
│   └── checkout.js         ← 3-step checkout: delivery → payment → review → success
│
└── data/
    └── products.js         ← Product catalogue (16 items across 7 categories)
```

---

## ✨ Features

| Feature | Details |
|---|---|
| **Dark / Light Mode** | Toggle persisted to `localStorage` |
| **Product Catalogue** | 16 products across Electronics, Fashion, Home, Sports, Beauty, Books, Toys |
| **Category Filtering** | Pill bar + sub-nav + footer links |
| **Live Search** | Suggestions dropdown + full-text search with skeleton loaders |
| **Quick View Modal** | Product details, quantity selector, add-to-cart, wishlist, star rating |
| **Shopping Cart** | Slide-in panel, quantity controls, remove, subtotal, savings |
| **Wishlist** | Add/remove with ♥ toggle, dedicated wishlist page |
| **Product Ratings** | Click stars in modal → persisted per product |
| **Authentication** | Sign In / Sign Up with validation, stored in `localStorage` |
| **3-Step Checkout** | Delivery address → Payment method → Review → Order success |
| **Toast Notifications** | Contextual success / warning / error messages |
| **Countdown Timer** | Flash sale live countdown |
| **Skeleton Loaders** | Shimmer placeholders before products render |
| **Responsive** | Mobile-first, works on all screen sizes |

---

## 🚀 Getting Started

1. **Download / unzip** the `shopnova` folder
2. Open `index.html` directly in any modern browser
3. No server, no npm install, no build step required

> **Tip:** For the best experience, use a local server (e.g. VS Code Live Server extension) to avoid any browser CORS restrictions on local file loading.

---

## 🎨 Design System

| Token | Value |
|---|---|
| Display font | Syne (Google Fonts) |
| Body font | DM Sans (Google Fonts) |
| Accent color | `#e8470a` (burnt orange) |
| Background | `#f5f3ee` (warm parchment) |
| Dark background | `#111008` |

All colours and spacing are defined as CSS custom properties in `css/variables.css` and automatically swap on dark mode.

---

## 📦 Data & Persistence

All state is held in `localStorage` under these keys:

| Key | Contents |
|---|---|
| `sn_cart` | Cart items `[{id, qty}]` |
| `sn_wishlist` | Wished product IDs `[1, 5, …]` |
| `sn_user` | Logged-in user `{name, email}` |
| `sn_ratings` | Per-product star ratings `{1: 4, 3: 5, …}` |
| `sn_theme` | `"light"` or `"dark"` |

---

## 🧩 Adding Products

Edit `data/products.js` and add an object to the `PRODUCTS` array:

```js
{
  id: 17,
  name: "My New Product",
  cat: "electronics",        // electronics | fashion | home | sports | beauty | books | toys
  emoji: "🖥️",
  price: 299.99,
  orig: 399.99,              // original price (optional, for discount badge)
  rating: 4.5,
  reviews: 1200,
  desc: "Short description here.",
  features: ["Feature 1", "Feature 2"],
  badge: "sale",             // null | "new" | "hot" | "sale"
  trending: false,           // shows in Trending section
}
```

---

*Built with ❤️ — pure HTML, CSS & JavaScript*
