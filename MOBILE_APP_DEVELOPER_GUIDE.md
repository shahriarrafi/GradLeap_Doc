# 📱 GradLeap Mobile App — Developer Onboarding Guide

Welcome to the GradLeap LMS Mobile Development Team! This document provides all the technical context, API specifications, and integration requirements you need to build the cross-platform Flutter application.

---

## 🏗️ 1. Technical Context

- **Backend:** Django 5.x + Django REST Framework (DRF)
- **Database:** PostgreSQL (Production) / SQLite (Dev)
- **Primary API:** RESTful JSON API
- **Auth System:** Custom OTP-based registration + Token Authentication (DRF Standard). 
  - *Note: While the PRD mentions Firebase, we recommend using the custom REST API for Auth to ensure a unified user database with the web version.*

---

## 🔌 2. API Integration Reference

All mobile app features are powered by our backend API.

### **Base URLs**
- **Development:** `http://your-local-ip:8000/api/v1/`
- **Production:** `https://api.gradleap.org/api/v1/`

### **Full Endpoint List**
Refer to the [🔌 API_ENDPOINTS.md](API_ENDPOINTS.md) for a comprehensive list of all endpoints, methods, and auth requirements.

---

## 🔐 3. Authentication Flow (High Priority)

The mobile app should follow this flow for a seamless experience:

1. **Registration:**
   - Call `POST customer/register/` with `email`, `password`, `phone`, etc.
   - User receives an OTP via email.
2. **OTP Verification:**
   - Call `POST otp/verify/` with `email` and `otp_code`.
3. **Login:**
   - Call `POST login/` with `email` and `password`.
   - **Response:** You will receive a `token`. 
4. **Header Setup:**
   - Every subsequent request must include the header: `Authorization: Token <your_token_here>`

---

## 🛠️ 4. Feature-to-API Mapping (MVP Scope)

Based on your PRD, here is the direct mapping to our API:

| PRD Section | Feature | API Endpoint |
|-------------|---------|--------------|
| **4.2** | Home Dashboard (Featured) | `blogs/featured/`, `bundles/`, `resources/` |
| **4.3** | Course Listing | `courses/` |
| **4.3** | Course Details | `courses/{slug}/` |
| **4.4** | Library (Books) | `books/` |
| **4.4** | Book Reading | `my-books/{id}/read/` |
| **4.7** | My Learning / Enrolled | `my-courses/`, `my-batches/` |
| **4.7** | Profile Update | `profile-update/` |

---

## 📦 5. Key Data Objects

When building your Flutter models, pay attention to these core structures:

### **Course Object**
```json
{
  "id": 1,
  "title": "Mastering Flutter",
  "slug": "mastering-flutter",
  "thumbnail": "https://...",
  "price": 5000,
  "discounted_price": 4500,
  "is_live": false
}
```

### **Enrollment Object**
```json
{
  "id": 12,
  "course": { ... },
  "progress_percentage": 45,
  "last_accessed": "2024-05-05T..."
}
```

---

## 🚀 6. Phase-wise Implementation Guide

### **Phase 1: Project Setup (Days 1-5)**
- Initialize Flutter project with **Riverpod** or **Provider**.
- Create a `Dio` or `http` client wrapper that automatically attaches the `Authorization: Token` header if available.

### **Phase 2: Core UI (Days 6-20)**
- Build screens using our [Design Style Guide](README.md#design-aesthetics) (Dark Modern UI, Card-based).
- Use `CachedNetworkImage` for course thumbnails to ensure high performance.

### **Phase 3: Integration (Days 21-29)**
- Connect the Auth flow first.
- Map the Home Dashboard using parallel API calls (e.g., `Future.wait`) for Courses, Bundles, and Resources.

---

## ⚠️ 7. Critical Considerations for Mobile
- **N+1 Performance:** The API is optimized, but avoid calling detailed info inside a list. Use the list endpoint first.
- **Video Playback:** Lesson videos are served via URL. Use `video_player` or `chewie` in Flutter.
- **PDF Viewing:** Use `flutter_pdfview` for resources and digital books.

---

**Documentation Status:** 🟢 Verified & Ready for Handoff
**Support:** For API issues or schema changes, contact the Backend Lead.
