# 🎨 GradLeap Frontend

The motion-first React application for the GradLeap ecosystem. Built for extreme performance, premium aesthetics, and rock-solid resilience.

## ⚡ Performance & Resilience
- **TanStack Query (React Query):** Enterprise-grade server-state management with intelligent caching and background synchronization.
- **Cinematic Skeleton System:** Zero-layout-shift loading experience with high-fidelity skeletons for Dashboard, Shop, and Course Details.
- **Global Error Boundary:** Application-wide crash protection with a dedicated recovery UI.
- **Motion-First UX:** Complex staggered animations and tactile interactions powered by Framer Motion.

## 🛠️ Technology Stack
- **Framework:** [React 19](https://react.dev/) + [Vite](https://vitejs.dev/)
- **Data Management:** **TanStack Query v5**
- **Animations:** **Framer Motion** (Spring-based physics)
- **Styling:** **Tailwind CSS 3** (Custom design system)
- **State:** **Zustand** (Local store & persistence)
- **Tracking:** Meta Pixel & Conversions API (CAPI) Integration

## 🚀 Quick Start

1. **Install Dependencies:**
   ```bash
   npm install
   ```

2. **Environment Configuration:**
   Create a `.env.local` file:
   ```env
   VITE_API_URL=http://localhost:8000/api/v1
   VITE_SERVICES_API_URL=http://localhost:8000
   ```

3. **Development Mode:**
   ```bash
   npm run dev
   ```

## 📦 Scripts
- `npm run dev` - Start development server.
- `npm run build` - Build for production.
- `npm run preview` - Preview the production build locally.

---

## 🎨 UX Impact: The "Premium" Experience

We've invested heavily in frontend engineering to make GradLeap feel like a world-class platform. Here is the impact:

- **The "Instant" App Feel:** Because we use **TanStack Query**, data is cached locally. Navigating between the Shop and Dashboard feels almost instantaneous because the app doesn't have to wait for the server every single time.
- **Visual Stability:** Our **Skeleton System** ensures that the page structure is visible *before* the content arrives. This prevents annoying "layout shifts" where buttons move as images load.
- **High-Fidelity Animations:** We use spring-based physics in **Framer Motion**. This means buttons react to your touch naturally, and pages slide into view with a sense of weight and quality.
- **Fail-Safe Usage:** If a single part of the UI fails to render, our **ErrorBoundary** catches it gracefully, allowing the rest of the app to function and providing the user with a simple "Reload" button.

---
Part of the [GradLeap Project](../README.md)
