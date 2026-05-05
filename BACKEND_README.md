# ⚙️ GradLeap Backend — Django REST API

This is the hardened, service-oriented backend for the GradLeap LMS. It manages complex business logic including multi-step payments, course delivery, and AI interactions through a decoupled architecture.

## 🚀 Architectural Features
- **Service Layer Pattern:** Business logic is isolated in dedicated services (e.g., `PaymentService`, `EnrollmentService`) to ensure DRY and maintainable code.
- **Unified Security:** Standardized permission classes and rate-limiters across all API endpoints.
- **Data Resilience:** Atomic transaction management for critical flows (Checkout, Enrollment) to prevent data corruption.
- **Performance Optimized:** Rigorous N+1 query reduction and database indexing for high-scale traffic.
- **Advanced Tracking:** Server-side event tracking via **Meta Conversions API (CAPI)**.
- **Task Management:** Django Q2 for asynchronous processing (emails, reports, data sync).

## 📂 App Breakdown
- `accounts`: Identity management, OTP-based MFA, and student profiles.
- `courses`: Learning content, unified serializers, and enrollment tracking.
- `books`: Physical and digital bookstore logic.
- `orders`: Hardened checkout flow via `PaymentService` (SSLCommerz/Paystation).
- `support`: Helpdesk and student-instructor ticketing.
- `admin_api`: Optimized dashboard data points for internal management.
- `blog_app`: SEO-optimized content delivery.

## 🛠️ Setup Instructions

1. **Environment Configuration:**
   Create a `.env` file based on `.env.example`. Ensure `REDIS_URL` is set for background tasks.
   
2. **Installation:**
   ```bash
   python -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

3. **Database & Migrations:**
   ```bash
   python manage.py migrate
   python manage.py createsuperuser
   ```

4. **Run Server:**
   ```bash
   python manage.py runserver
   ```

## 📖 Backend Patterns
- **Serializers:** Use unified serializers for consistent data manifestation.
- **Permissions:** Apply standard classes (e.g., `IsStudent`, `HasPurchasedCourse`).
- **Errors:** Standardized error response format across the entire API.

---

## 💎 Business Value of the Backend Hardening

We've moved beyond a basic API to a **Production-Grade Infrastructure**. Here’s what that means for the business:

- **100% Reliable Payments:** By using a `PaymentService`, we’ve isolated the most critical part of the app. If the cart has an issue, the checkout logic remains safe and untouched.
- **Accurate Marketing Data:** With **Meta CAPI**, we send sales data directly from our server to Meta. This bypasses ad-blockers and ensures your marketing campaigns have the most accurate data possible.
- **Zero Data Corruption:** Our **Atomic Transactions** ensure that when a student pays, their enrollment happens *instantly or not at all*. No more cases where a student pays but doesn't get access to the course.
- **Scalability:** The system is now optimized for thousands of simultaneous users without slowing down, thanks to N+1 query fixing and caching.

---
Built with Django 5.x | PostgreSQL Ready
