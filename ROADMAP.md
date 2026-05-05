# 🎓 GradLeap — The Ultimate Learning & Career Ecosystem

<div align="center">
  
  <p align="center">
    <strong>A high-performance, resilient Learning Management System (LMS) and e-commerce platform built for the next generation of learners.</strong>
  </p>

  <p align="center">
    <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
    <img src="https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django" />
    <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
    <img src="https://img.shields.io/badge/TanStack_Query-FF4154?style=for-the-badge&logo=react-query&logoColor=white" alt="TanStack Query" />
    <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind" />
    <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite" />
  </p>
</div>

---

## 🌟 Overview

GradLeap is a full-stack Learning Management System (LMS) and e-commerce platform designed to bridge the gap between learning and career success. It leverages a modern, decoupled architecture to provide high-fidelity user experiences and a hardened, service-oriented backend.

### 🚀 Key Features

- **📚 Unified Marketplace:** Integrated e-commerce for digital courses, live batches, and physical books.
- **🖥️ Premium Dashboard:** A high-motion "My Learning" hub with intelligent progress tracking and active nav indicators.
- **⚡ Performance-First UI:** Zero Cumulative Layout Shift (CLS) using advanced skeleton loaders and optimized caching.
- **🛡️ Hardened Security:** Unified permission classes, atomic transaction management, and service-layer isolation.
- **🎫 Resilience System:** Global error boundaries and fail-safe initialization to prevent application crashes.
- **🎫 Advanced Tracking:** Meta Conversions API (CAPI) and Pixel integration for high-accuracy attribution.

---

## 🛠️ Tech Stack

### Frontend
- **Framework:** React 19 + Vite
- **Data Management:** **TanStack Query (React Query)** — Optimized server-state caching.
- **Animations:** **Framer Motion** — Premium motion-first UX and micro-interactions.
- **Resilience:** Global ErrorBoundary & Skeleton Loaders.
- **State Management:** Zustand
- **Language:** TypeScript

### Backend
- **Framework:** Django 5.x + Django REST Framework (DRF)
- **Architecture:** **Service-Oriented Design** (Decoupled business logic in `services.py`).
- **Database:** SQLite (Dev) / PostgreSQL (Production)
- **Background Tasks:** Django Q2 + Redis
- **Security:** Unified permissions, rate-limiting, and atomic transactions.
- **Admin UI:** Django Jazzmin.

---

## 📁 Project Structure

```bash
.
├── backend/            # Service-oriented Django API
│   ├── accounts/       # Authentication & Profiles
│   ├── courses/        # Learning content & Serializers
│   ├── books/          # Digital & Physical bookstore
│   ├── orders/         # PaymentService & Checkout logic
│   ├── support/        # Helpdesk & Tickets
│   └── core/           # Main settings & URL routing
├── frontend/           # Motion-first React application
│   ├── src/
│   │   ├── components/ # Atomic UI & Skeletons
│   │   ├── hooks/      # Custom TanStack Query hooks
│   │   ├── pages/      # Dynamic views
│   │   └── utils/      # Meta Pixel & Utility helpers
│   └── public/         # Static assets
└── README.md
```

---

## 💡 Why these upgrades matter? (User-Friendly Guide)

If you're not a developer, here is a quick breakdown of how our latest technical upgrades improve the user experience:

- **🚀 Faster Loading (TanStack Query):** Instead of reloading the entire page every time, the app now "remembers" data you've already seen. It feels snappy and instant.
- **✨ No More Jitter (Skeleton Loaders):** You know when a page "jumps" while loading an image? We've fixed that. Beautiful gray placeholders hold the spot so the layout stays perfectly still.
- **💎 Premium Feel (Framer Motion):** Smooth transitions and subtle animations make the site feel like a high-end mobile app rather than a basic website.
- **🛡️ Bulletproof Reliability (ErrorBoundary):** If a single button or section has a bug, the entire app won't crash. You'll see a friendly "Try Again" message instead of a white screen.
- **🔐 Secure Payments (Service-Layer):** Our payment logic is now isolated and hardened, making it extremely secure and reducing the chance of failed orders.

---

## ⚙️ Getting Started

### 1. Prerequisites
- **Node.js** (v18+)
- **Python** (v3.10+)
- **Redis** (Required for background tasks and caching)

### 2. Backend Setup
```bash
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

### 3. Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

---

## 📖 Documentation

- [🔌 **Full API Endpoints List** (Commercial Reference)](API_ENDPOINTS.md)
- [GradLeap API Integration Guide](FRONTEND_README.md)
- [Backend In-Depth Guide](BACKEND_README.md)

---

<div align="center">
  <p>Built with ❤️ by the GradLeap Team</p>
</div>
