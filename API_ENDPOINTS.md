# 🔌 GradLeap API Documentation — Comprehensive Endpoint List

This document provides a full list of API endpoints available in the GradLeap LMS. All endpoints (except public ones) require a valid **Authorization Token** in the header.

**Base URL:** `https://api.gradleap.org/api/v1/` (Production) | `http://localhost:8000/api/v1/` (Development)

---

## 🔐 1. Authentication & Account Management
| Endpoint | Method | Description | Auth Required |
|----------|--------|-------------|---------------|
| `customer/register/` | POST | Register a new student account. | No |
| `otp/verify/` | POST | Verify registration OTP. | No |
| `otp/resend/` | POST | Resend verification OTP. | No |
| `login/` | POST | Login and receive auth token. | No |
| `logout/` | POST | Invalidate current session. | Yes |
| `token-validator/` | GET | Check if current token is valid. | Yes |
| `profile-update/` | PATCH | Update student profile details. | Yes |
| `password-reset/` | POST | Request a password reset link. | No |
| `password-reset/confirm/` | POST | Set a new password with reset token. | No |
| `change-password/` | POST | Change password while logged in. | Yes |

---

## 📚 2. Course Catalog & Learning Hub
| Endpoint | Method | Description | Auth Required |
|----------|--------|-------------|---------------|
| `courses/` | GET | List all available courses. | No |
| `courses/{slug}/` | GET | Get detailed info for a specific course. | No |
| `course-categories/` | GET | List all course categories. | No |
| `my-courses/` | GET | List all courses purchased by the user. | Yes |
| `my-batches/` | GET | List live batches the user is enrolled in. | Yes |
| `lessons/{id}/` | GET | Get lesson content and video link. | Yes |
| `lessons/{id}/questions/` | GET | Get quiz questions for a lesson. | Yes |
| `lessons/{id}/submit_quiz/` | POST | Submit quiz answers for grading. | Yes |
| `live-sessions/{id}/` | GET | Get details for a live class session. | Yes |
| `progress/update/` | POST | Mark a lesson or session as completed. | Yes |
| `study-activity/` | GET | Get daily/weekly learning activity stats. | Yes |
| `courses/{id}/certificate/` | GET | Download course completion certificate. | Yes |

---

## 🛒 3. E-Commerce & Checkout Flow
| Endpoint | Method | Description | Auth Required |
|----------|--------|-------------|---------------|
| `cart/` | GET/POST | View or add items to the shopping cart. | Yes/No |
| `cart/{id}/` | DELETE | Remove an item from the cart. | Yes/No |
| `cart/clear/` | POST | Remove all items from the cart. | Yes/No |
| `promo/validate/` | POST | Validate a coupon/promo code. | Yes |
| `orders/checkout/` | POST | Initialize payment gateway redirect. | Yes |
| `orders/verify_payment/` | POST | Verify payment status after redirect. | Yes |
| `installments/my-plans/` | GET | List user's active installment plans. | Yes |
| `installments/{id}/pay/` | POST | Pay a specific installment. | Yes |
| `bundles/` | GET | List all available product bundles. | No |

---

## 📖 4. Digital Bookstore
| Endpoint | Method | Description | Auth Required |
|----------|--------|-------------|---------------|
| `books/` | GET | List all available books. | No |
| `books/{slug}/` | GET | Get detailed info for a specific book. | No |
| `book-categories/` | GET | List book categories. | No |
| `my-books/` | GET | List books purchased by the user. | Yes |
| `my-books/{id}/read/` | GET | Access the digital reader for a book. | Yes |
| `my-books/{id}/download/` | GET | Download PDF (if permitted). | Yes |

---

## 🎫 5. Support & Resources
| Endpoint | Method | Description | Auth Required |
|----------|--------|-------------|---------------|
| `support/ticket-categories/` | GET | List helpdesk ticket categories. | Yes |
| `support/my-tickets/` | GET/POST | List user tickets or create a new one. | Yes |
| `support/my-tickets/{id}/` | GET | View a ticket and its replies. | Yes |
| `support/my-tickets/{id}/reply/` | POST | Post a reply to a ticket. | Yes |
| `consultation-request/` | POST | Request a 1-on-1 consultation. | No |
| `resources/` | GET | Access free guides and PDF resources. | No |

---

## 📰 6. Blog & Content
| Endpoint | Method | Description | Auth Required |
|----------|--------|-------------|---------------|
| `blogs/` | GET | List all blog posts. | No |
| `blogs/featured/` | GET | List only featured blog posts. | No |
| `blogs/{slug}/` | GET | Read a specific blog post. | No |
| `blogs/{slug}/comments/` | POST | Post a comment on a blog. | Yes |

---

## 👑 7. Admin API (Management)
| Endpoint | Method | Description | Auth Required |
|----------|--------|-------------|---------------|
| `admin/dashboard/stats/` | GET | Overview of sales, students, and growth. | Admin |
| `admin/orders/` | GET | Manage all transactions. | Admin |
| `admin/students/` | GET/PUT | Manage student accounts and status. | Admin |
| `admin/courses/` | CRUD | Full management of course content. | Admin |
| `admin/tickets/` | GET/POST | Manage and reply to student tickets. | Admin |
| `admin/promo-codes/` | CRUD | Create and manage discount codes. | Admin |

---
**Note:** This documentation is optimized for integration testing and commercial presentation. For further details on request/response schemas, refer to the [Schema Guide](file:///Users/rafi/Documents/gradleap-lms%20copy/meta_api.md).
