# Online Store — Angular E-Commerce SPA

A multi-component e-commerce single-page application built with Angular 19, demonstrating component architecture, reactive state with RxJS, route-level access control, and REST API consumption. Built as a portfolio project to practice frontend engineering with modern Angular.

> **Note:** This is a learning project, not a production system. It uses [FakeStoreAPI](https://fakestoreapi.com/) as a backend and stores user sessions in localStorage.

---

## 🚀 Live Demo

**Site:** https://archil-simonishvili-ecommerce-proje.vercel.app

**Test login (FakeStoreAPI demo user):**

```
Username: johnd
Password: m38rmF$
```

You can browse, view product details, and filter by category without logging in. Login is required only to access the cart.

---

## 🛠️ Tech Stack

- **Angular 19** with standalone components (the new application builder)
- **TypeScript 5.6**
- **RxJS 7.8** — Observables, BehaviorSubject, operator pipelines
- **Angular Forms** (Template-driven)
- **Angular Router** with route parameters and CanActivate guards
- **Bootstrap 5.3** — responsive layout, utility classes
- **Swiper 11** — home-page hero slider
- **FakeStoreAPI** — public REST API for products and users

---

## 🔑 Key Features

- **12 standalone components** — home, shop, product list, product detail, category, cart, login, register, contact, plus reusable nav and footer.
- **Three injectable services**, cleanly separated by responsibility:
  - `ProductsService` — product fetching, top-rated derivation via RxJS `map`
  - `CartService` — local cart state management
  - `AuthService` — login, logout, currentUser as a `BehaviorSubject` for reactive subscribers, persisted via localStorage
- **Route-level access control** — `AuthGuard` implementing `CanActivate` restricts the `/cart` route to authenticated users with redirect-to-login behavior.
- **Route parameters** — `product/:id` and `category/:category` for dynamic routing with reactive parameter handling.
- **RxJS pipelines** — client-side derivations (top-rated products, category filtering) using `map` and other operators on API observables.
- **Responsive design** — Bootstrap 5 grid + utility classes, mobile-friendly nav and product layouts.

---

## 🏗️ Project Structure

```
src/app/
├── home/                Landing page with hero slider and top-sellers
├── shop/                Full product catalog
├── product-detail/      Single product view with /product/:id
├── product-category/    Category-filtered product list with /category/:category
├── cart/                Authenticated cart view (protected by AuthGuard)
├── login/               Login form
├── register/            (currently stub — see Future Work)
├── contact-us/          Contact form
├── nav/                 Reusable top navigation
├── footer/              Reusable site footer
├── slider/              Swiper-based home page slider
├── top-sellers/         Top-rated products section
│
├── services/
│   ├── products.service.ts
│   ├── cart.service.ts
│   └── auth.service.ts
│
├── guards/
│   └── auth.guard.ts    CanActivate guard for protected routes
│
├── models/              Type definitions for products, users, etc.
├── app.routes.ts        Application route configuration
└── app.component.ts     Root component
```

---

## 💻 Running Locally

### Prerequisites

- Node.js 18+ and npm
- Angular CLI 19 (`npm install -g @angular/cli`)

### Setup

1. Clone the repo:

   ```bash
   git clone https://github.com/Achi-Simonishvili/Archil-Simonishvili_Ecommerce-Project.git
   cd Archil-Simonishvili_Ecommerce-Project
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Run the dev server:

   ```bash
   ng serve
   ```

4. Open `http://localhost:4200` in your browser. The app will reload on file changes.

### Build for production

```bash
ng build
```

Output is written to `dist/my-project/browser/` (Angular's new application builder).

---

## 🌐 Deployment

Currently deployed to **Vercel** with a `vercel.json` providing SPA fallback for client-side routing. To deploy your own copy:

1. Fork the repo
2. Sign in to Vercel with GitHub
3. Import the repo, set **Output Directory** to `dist/my-project/browser`
4. Deploy

The included `vercel.json` rewrites all routes to `index.html` so refreshing on `/shop` or `/product/5` works correctly.

---

## 🚧 Future Work

Honest list of things this project doesn't do yet, kept here as a roadmap rather than hidden:

- **Functional registration** — `RegisterComponent` is a stub. Login currently validates against FakeStoreAPI's pre-existing demo users only.
- **Cart persistence** — cart state is in-memory; refreshing the page loses it.
- **Real backend** — switch from FakeStoreAPI to a real API (the [HMS REST API](https://github.com/Achi-Simonishvili/FinalProjects-2---HMS) project shows my backend approach in .NET).
- **Form validation** — checkout form needs more robust validation feedback.
- **Unit tests** — Karma scaffolding is in place but no tests written yet.

---

## 📄 License

This is a portfolio / learning project. Feel free to read the code, but it's not intended for production use.

---

## 👤 Author

**Archil Simonishvili**
[GitHub](https://github.com/Achi-Simonishvili) · [LinkedIn](https://linkedin.com/in/archil-simonishvili-47340017b)
