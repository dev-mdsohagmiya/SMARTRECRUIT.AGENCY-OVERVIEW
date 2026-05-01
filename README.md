# SmartRecruit — Full Stack Recruitment & HR Platform

A production-grade B2B2C recruitment and skill development platform built end-to-end as a **Full Stack Developer** over **4 months**. The platform connects job seekers with European employment opportunities, helps employers hire skilled workers, offers skill and language training courses, and provides visa/relocation guidance — all managed through a fully CMS-driven admin panel. Live at **https://smartrecruit.agency/**

---

## Summary

Built SmartRecruit from the ground up in 4 months as a Full Stack Developer — covering the public-facing website, admin panel, and backend API. The platform serves job seekers, employers, training providers, and recruitment partners across Europe. Delivered a Next.js public website with dynamic job board, course enrollment, worker request forms, partner onboarding, and full CMS-controlled content; a React-based admin panel with analytics dashboard, full CRUD for all content, user management, media library, and page builder for every public page; and a Node.js + Express + MongoDB REST API powering both. Tech stack: Next.js (App Router, server actions), React 18, TypeScript, Redux Toolkit (RTK Query), Ant Design, Tailwind CSS, Framer Motion, React Hook Form, Zod, Formik, ApexCharts, jsPDF, XLSX, Node.js, Express, MongoDB.

---

## Project Overview

| Item | Detail |
|---|---|
| **Live Website** | https://smartrecruit.agency/ |
| **Duration** | 4 months |
| **Role** | Full Stack Developer |
| **Public Frontend** | Next.js 13 (App Router, server actions), TypeScript, Redux Toolkit (RTK Query), Tailwind CSS, Radix UI, Framer Motion, React Hook Form + Zod |
| **Admin Panel** | React 18, TypeScript, Redux Toolkit (RTK Query), Ant Design, Tailwind CSS 4, React Router 7, Formik + Yup, ApexCharts, Recharts |
| **Backend** | Node.js, Express, MongoDB |
| **Other** | TinyMCE, jsPDF, XLSX, Redux Persist, reCAPTCHA, Image Crop |

---

## Feature Breakdown

### 1. Authentication & Access Control

- **JWT-based login** — token stored in Redux (persisted via Redux Persist across sessions)
- **Bearer token** sent automatically in every API request header via RTK Query `prepareHeaders`
- **Client metadata** — IP address, user agent, browser URL, and timestamp sent as `X-Client-Details` header on every request for audit tracking
- **401 handling** — any unauthorized response triggers automatic logout and redirect to login
- **Role-based access** — admin routes protected by roles: `Super Admin`, `Admin`, `Editor`, `Publisher`
- **Password management** — change password from settings, forget password + reset password via email flow

---

### 2. Public Website (Next.js Frontend)

The public-facing marketing and service platform at https://smartrecruit.agency/ — fully CMS-driven from the admin panel.

#### Home Page
- Hero section, stats counters, services overview
- How We Work section, Why Choose SmartRecruit section
- Brands/partners logos, testimonials/reviews
- Job Fair & Seminar section, FAQ section
- All content dynamically loaded from backend CMS

#### Job Board (`/jobs`)
- Search jobs by keyword
- Filter by industry, country, employment type, experience level, education level
- Sort options, pagination
- Mobile-friendly drawer-based filters
- Individual job detail pages (`/jobs/[id]`)
- **Job application** — apply directly from the platform

#### Career Opportunities (`/career`)
- Internal job openings at SmartRecruit
- Individual career job detail pages (`/career/[id]`)
- Application flow for internal positions

#### Skill & Language Training (`/skill-and-training`)
- Browse courses split by category: skill-based and language-based
- Individual course detail pages (`/skill-and-training/[slug]`)
- **Course enrollment** form
- Why Choose Our Training section, Benefits, Tips for Success, Real Stories

#### Employer Services (`/employer`)
- How SmartRecruit helps companies hire skilled workers across Europe
- **Worker Request Form** — employers submit hiring needs by industry and worker count
- Process walkthrough, benefits showcase

#### Talent Hub (`/talent-hub`)
- Browse available talent profiles organized by industry
- CTA to submit a worker request

#### Partner Page (`/partner`)
- Recruitment agency partnership opportunities
- **Partner application form** with industry selection
- Step-by-step partnership process, Why Choose section

#### Visa & Relocation Guide (`/visa-and-relocation`)
- Step-by-step guide for workers relocating to Europe
- Visa process breakdown, relocation tips

#### Blog & News
- `/blog` — blog landing with featured articles
- `/news` — paginated news listing with category filters
- `/news/[slug]` — individual article pages with rich text content, share buttons

#### Hall of Fame (`/hall-of-fame`)
- Success stories of placed workers and satisfied employers
- Filterable by category

#### About Us (`/about`)
- Company mission, vision, our story
- Team member profiles

#### Contact (`/contact`)
- Contact form with **reCAPTCHA v2** protection
- Multiple office locations displayed
- Message sent directly to backend

#### Technical Features (Frontend)
- **IP-based geolocation** — detects user country via IPInfo API, stored in cookie
- **Dynamic image optimization** — all images served from CDN (`/uploads`)
- **Loading skeletons** — smooth UX during API data fetching
- **Responsive design** — mobile, tablet, desktop breakpoints throughout
- **DOMPurify** — sanitizes rich text content before rendering
- **next-themes** — light/dark theme support

---

### 3. Admin Panel (React Frontend)

A fully role-protected internal panel for SmartRecruit staff to manage all platform content and operations.

#### Dashboard & Analytics
- Stats cards — total jobs, total applications, total courses, total enrollments
- **9 chart types**: Applications chart, Trend line, Hiring Funnel, Interview Success Rate, Job Applications Analytics, Job Categories distribution, Progress chart, Data Distribution, Summary chart
- Latest jobs, latest job applications, latest courses — real-time activity view

#### Jobs Management
- Create, edit, delete client-facing job postings
- Fields: title, description (rich text), category, location, salary, job type, deadline
- Inline Job Details modal
- **Job Applications** — view all applicants: name, email, resume link, date, status

#### Career Jobs Management
- Separate CRUD for internal SmartRecruit job openings
- **Career Job Applications** — track applicants for internal positions

#### Courses & Enrollments
- Create, edit, delete courses with slug-based routing
- Fields: title, slug, rich text description, thumbnail, instructor, duration, fee, category
- **Course Enrollments** — view all enrolled students with details

#### Instructors Management
- Add, edit, delete instructors
- Fields: name, bio, photo, social links, specialization

#### Industries Section
- **Industry Banner** — update the Industries page hero from admin
- **Industry Categories** — CRUD (e.g., Finance, Tech, Healthcare, Construction)
- **Industry Labels** — CRUD for job industry tags used in listings
- **Our Industry Talents** — CRUD for featured talent profiles per industry

#### Blog Management
- Create, edit, delete blog posts with TinyMCE rich text editor
- Slug-based routing, thumbnail, tags, author, publish date
- Inline blog preview modal

#### Reviews Management
- **Student Reviews** — create, edit, delete course/training reviews
- **Client Reviews** — create, edit, delete employer testimonials

#### Success Stories
- Create, edit, delete placement success stories
- Fields: title, description, photo, person name, role, company

#### Team Management
- Add, edit, delete team members shown on the public About page
- Filter by category/department
- Confirm modal before deletion

#### Media Library
- Upload images with built-in **image crop/resize** before saving
- Grid view with search, rename, delete
- **Set Media modal** — pick from existing library when editing any content

#### Page Builder (CMS)
Every public page section is editable from admin:

| Page | Sections |
|---|---|
| **Home** | Hero, About, Services, Stats, Brands, How to Work, Why Choose Us, FAQ, Feature Banner |
| **About** | Hero, Our Story, Opportunity, Vision, Why Choose Us |
| **Employer** | Hero, How We Help, How We Work, CTA |
| **Partner** | Hero, Why Choose Us, Step Process, CTA |
| **Visa & Relocation** | Hero, Guidelines Content |
| **Skill Training** | Hero, Benefits, Tips, Why Choose Us |
| **Terms & Privacy** | Hero, Full Legal Content |

#### User Management
- Create users, assign roles (`Super Admin`, `Admin`, `Editor`, `Publisher`)
- Suspend / activate accounts
- Update profile (name, photo, bio)

#### Action Logs (Audit Trail)
- View system-wide logs of all admin actions — who did what and when

#### Settings
- Change password, update personal profile

---

### 4. Backend API (Node.js + Express + MongoDB)

RESTful API powering both the public website and the admin panel.

- **Authentication** — JWT issue and verification, refresh token, forget/reset password via email
- **Jobs & Career Jobs** — full CRUD with filtering, search, pagination
- **Job Applications & Career Applications** — receive and store applicant submissions
- **Courses & Enrollments** — course CRUD, enrollment registration
- **Instructors** — instructor management endpoints
- **Blogs** — slug-based blog CRUD
- **Success Stories** — story CRUD with category filters
- **Student & Client Reviews** — review CRUD
- **Industries, Categories, Labels, Talents** — full industry section management
- **Team Members** — team CRUD with category support
- **Media** — file upload, rename, delete (served from `/uploads`)
- **Page Content** — Home, About, Employer, Partner, Visa, Skill Training, Terms & Privacy — GET + PATCH per page
- **Users** — user CRUD, role update, status toggle
- **Action Logs** — server-side logging of all admin mutations
- **Dashboard Stats** — aggregated statistics endpoint
- **Contact / Worker Request / Partner Form** — form submission handling with reCAPTCHA verification

---

## Architecture Highlights

- **Monorepo structure** — public website (`frontend.smartrecruit`) and admin panel (`admin.smartrecruit`) as separate apps sharing one backend
- **RTK Query** — all API calls in both apps use RTK Query with cache tag invalidation; mutations auto-refresh related lists
- **Redux Persist** — auth token survives page refresh in both apps without re-login
- **Role-based route protection** — `ProtectedRoute` in admin; public site has no login requirement
- **Server actions** — Next.js server actions used for select data-fetching operations alongside RTK Query
- **Form stacks** — React Hook Form + Zod (public site), Formik + Yup (admin panel)
- **Rich text** — TinyMCE (admin) and React Quill (public) for content editing
- **Export** — jsPDF for PDF reports, XLSX for Excel exports of application data
- **Image crop** — built-in crop/resize step before any image upload in admin
- **reCAPTCHA v2** — protects contact and application forms on the public site
- **IP geolocation** — detects user country on page load via IPInfo API for localized UX
