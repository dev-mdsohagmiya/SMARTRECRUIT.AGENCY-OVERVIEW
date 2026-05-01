# SmartRecruit — Full Stack Admin Panel

A full-featured recruitment and HR management admin panel built with **React 18 + TypeScript + Redux Toolkit (RTK Query)** on the frontend and a **Next.js** server-action-based backend. Developed over **4 months** as a **Full Stack Developer**. Live at **https://smartrecruit.agency/**

---

## Summary

Built SmartRecruit — a production-grade recruitment and HR admin platform — in 4 months as a Full Stack Developer. Delivered a complete CMS-driven admin panel covering job posting, career job management, course/instructor management, application tracking, industry talent showcase, blog/review/success story management, media library, analytics dashboard with multiple chart types, and full page-builder for every public-facing page. Tech stack: React 18, TypeScript, Redux Toolkit (RTK Query), Ant Design, Tailwind CSS, Next.js (server actions), Formik, ApexCharts, jsPDF, XLSX — backend: Node.js, Express, MongoDB.

---

## Project Overview

| Item | Detail |
|---|---|
| **Live Website** | https://smartrecruit.agency/ |
| **Duration** | 4 months |
| **Role** | Full Stack Developer |
| **Frontend Stack** | React 18, TypeScript, Redux Toolkit (RTK Query), Ant Design, Tailwind CSS 4, React Router 7, Framer Motion, Next.js (server actions) |
| **Backend Stack** | Node.js, Express, MongoDB |
| **Forms** | Formik + Yup validation |
| **Rich Text** | TinyMCE, React Quill |
| **Charts** | ApexCharts, Recharts, CanvasJS |
| **Export** | jsPDF (PDF), XLSX (Excel) |
| **Other** | Redux Persist, Image Crop, React Toastify |

---

## Feature Breakdown

### 1. Authentication & Access Control

- **JWT-based login** — token stored in Redux (persisted via Redux Persist)
- **Bearer token** sent in every API request header automatically via RTK Query `prepareHeaders`
- **Client metadata** — IP address, user agent, browser URL, and timestamp sent as `X-Client-Details` header on every request for audit tracking
- **401 handling** — any unauthorized response triggers automatic logout and redirect to login
- **Role-based access** — routes protected by roles: `Super Admin`, `Admin`, `Editor`, `Publisher`
- **Password management** — change password from settings, forget password + reset password flow

---

### 2. Dashboard & Analytics

The landing page of the admin panel — gives a real-time snapshot of platform activity.

- **Stats cards** — total jobs, total applications, total courses, total enrollments
- **Charts (9 types)**:
  - Applications chart (bar/column)
  - Applications trend line
  - Hiring funnel chart
  - Interview success rate chart
  - Job applications analytics chart
  - Job categories distribution chart
  - Progress chart
  - Data distribution chart
  - Summary chart
- **Latest jobs** — quick view of recently posted jobs
- **Latest job applications** — recent applicant activity
- **Latest courses** — recently added courses

---

### 3. Jobs Management

Manage client-facing job postings displayed on the SmartRecruit website.

- **Create job** — title, description (rich text), category, location, salary, job type, deadline
- **Edit job** — full update of all fields
- **Delete job**
- **List all jobs** — paginated table with search and filter
- **Job Details modal** — preview job posting inline
- **Job Applications** — view all applications submitted for jobs:
  - Applicant name, email, resume/CV link
  - Application date
  - Application status tracking

---

### 4. Career Jobs Management

Separate section for internal career openings at SmartRecruit itself.

- **Create career job** — same fields as client jobs but for internal hiring
- **Edit / Delete career job**
- **List career jobs** — paginated and searchable
- **Career Job Applications** — track applicants for internal positions

---

### 5. Courses & Skill Training

Manage skill-development courses offered through the platform.

- **Create course** — title, slug, description (TinyMCE rich text), thumbnail, instructor, duration, fee, category
- **Edit course** — full update
- **Delete course**
- **List all courses** — paginated table
- **Course Details modal** — inline preview
- **Course Enrollments** — view all students enrolled in courses:
  - Student name, email, enrolled date, course name

---

### 6. Instructors Management

Manage the instructors who deliver courses.

- **Add instructor** — name, bio, photo, social links, specialization
- **Edit instructor**
- **Delete instructor**
- **List all instructors** — table view with photo and details

---

### 7. Industries Section

Showcase talent categories and industry expertise on the public site.

- **Industry Banner** — update the hero banner for the Industries page
- **Industry Categories** — CRUD for talent categories (e.g., Finance, Tech, Healthcare)
- **Industry Labels** — CRUD for job industry labels/tags used in listings
- **Our Industry Talents** — CRUD for featured talent profiles per industry:
  - Name, photo, role, category, description

---

### 8. Blog Management

Full blog/article publishing system for the SmartRecruit website.

- **Create blog** — title, slug, content (TinyMCE rich text), thumbnail, tags, author, publish date
- **Edit blog** — update any field
- **Delete blog**
- **List all blogs** — paginated with slug-based routing
- **Blog modal** — preview blog content inline

---

### 9. Reviews Management

Two separate review streams — student reviews and client reviews.

#### Student Reviews
- Create, edit, delete student reviews
- Fields: student name, photo, course, rating, review text

#### Client Reviews
- Create, edit, delete client reviews
- Fields: client name, company, photo, rating, testimonial text

---

### 10. Success Stories

Showcase placement and career success stories on the public website.

- **Create success story** — title, description, photo, person name, role, company
- **Edit / Delete success story**
- **List all stories** — table view with preview

---

### 11. Team Management

Manage the SmartRecruit team displayed on the public About/Team page.

- **Add team member** — name, designation, photo, social links, category
- **Edit team member**
- **Delete team member** (with confirm modal)
- **List by category** — filter team by department/category

---

### 12. Media Library

Centralized image/file management used across all CMS modules.

- **Upload image** — single file upload with image crop tool
- **List all media** — grid view with search
- **Rename media**
- **Delete media**
- **Set media modal** — pick from existing library when editing any page/content
- **Image crop modal** — crop/resize before saving

---

### 13. Page Builder (CMS)

Every public-facing page of the SmartRecruit website is fully editable from the admin panel. Each page has section-specific forms.

#### Home Page (9 sections)
- Hero banner (headline, subtext, CTA buttons, background)
- About section
- Services section
- Stats section (numbers/counters)
- Brands/partners logos
- How to work section
- Why Choose Us section
- FAQ section
- Feature banner

#### About Page (5 sections)
- Hero banner
- Our Story section
- Opportunity section
- Vision section
- Why Choose Us section

#### Employer Page (4 sections)
- Hero banner
- How We Help section
- How We Work section
- CTA section

#### Partner Page (4 sections)
- Hero banner
- Why Choose Us section
- Step-by-step process section
- CTA section

#### Visa & Relocation Page (2 sections)
- Hero banner
- Guidelines/content section

#### Skill Training Page (4 sections)
- Hero banner
- Benefits section
- Tips section
- Why Choose Us section

#### Terms & Privacy Page (2 sections)
- Hero banner
- Full legal content (rich text)

---

### 14. User Management

Manage admin panel users and access.

- **Create user** — name, email, role
- **List all users** — paginated
- **Update user role** — assign `Super Admin`, `Admin`, `Editor`, `Publisher`
- **Suspend / Activate user** — toggle account status
- **Update profile** — name, photo, bio

---

### 15. Action Logs (Audit Trail)

- View system-wide action logs — who did what and when
- Helps with accountability and debugging

---

### 16. Settings

- **Change password** — from the profile settings menu
- **Profile updates** — update personal details and photo

---

## Architecture Highlights

- **RTK Query** — all API calls use RTK Query with cache tag invalidation; editing a resource auto-refreshes all related lists
- **Redux Persist** — auth token survives page refresh without re-login
- **Role-based route protection** — `ProtectedRoute` wrapper checks user role before rendering any page
- **Form stack** — Formik + Yup for all create/edit forms; consistent validation UX
- **Rich text** — TinyMCE and React Quill used across blog, courses, and page-builder forms
- **Export** — jsPDF for PDF reports, XLSX for Excel exports of application data
- **Image crop** — built-in crop/resize step before any image upload
- **Reusable component library** — shared `FormInput`, `FormSelect`, `FormDatePicker`, `FormRichTextEditor`, `AntTable`, `PageHeader` used consistently across all 25+ pages
- **9 chart types** — ApexCharts, Recharts, and CanvasJS used for different visualization needs in the analytics dashboard
