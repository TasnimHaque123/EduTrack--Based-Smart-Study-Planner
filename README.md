# EduTrack - Web Based Smart Study Planner

[![Next.js](https://img.shields.io/badge/Next.js-14+-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.0+-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)](https://supabase.com/)
[![Vercel](https://img.shields.io/badge/Vercel-Deployed-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://edu-track-wine.vercel.app)

> A centralized, role-based Academic & Learning Management System designed to streamline university administrative, teaching, and learning workflows.

---

## 📌 Overview

**EduTrack** (Web Based Smart Study Planner) addresses academic operational fragmentation by unifying course management, automated quiz assessments, attendance tracking, assignment workflows, and user management under a single platform. Built on modern JavaScript technologies, it provides role-specific dashboards with strict server-side authorization.

🔗 **Live Application:** [edu-track-wine.vercel.app](https://edu-track-wine.vercel.app)

---

## ✨ Key Features

### 🔐 Authentication & Access Control (RBAC)
* **5 Distinct User Roles:** Student, Teacher, Administrator, Dean, and Chairman.
* **Role Guards:** Route protection via middleware and server actions with PostgreSQL Row-Level Security (RLS).

### 📚 Course & Enrollment Management
* **Course Offerings:** Dynamic mapping of courses, teachers, academic terms, and semesters.
* **Scoped Dashboards:** Students view only enrolled offerings; teachers view only assigned courses.

### 📝 Automated Quiz Engine
* **Teacher Management:** Passcode protection, custom durations, start/end time windows, and JSON-based question structures.
* **Secure Student Attempt Flow:** Real-time answer auto-saving with ownership validation.
* **Server-Side Grading:** Automatic score evaluation without leaking correct answers to the frontend.

### 📅 Attendance & Content Distribution
* **Session Tracking:** Teachers log attendance per session; students track attendance metrics.
* **Syllabus & Material Access:** Direct access to course materials for enrolled students with syllabus coverage tracking.

### 👤 User Administration
* Searchable and filterable user management directory for admins.
* Controlled profile editing (names, phone numbers, avatars, department selection via UI dropdowns) while securing core identity data.

---

## 🛠️ Tech Stack

| Layer | Technology |
| :--- | :--- |
| **Framework** | Next.js (App Router, Server Actions) |
| **Frontend** | React, Tailwind CSS, Lucide React |
| **Backend & Auth** | Supabase (JWT, Row-Level Security) |
| **Database** | PostgreSQL |
| **Deployment** | Vercel (Frontend/Actions) & Supabase Cloud (Data Layer) |

---
## 🚀 Getting Started

### Prerequisites
* Node.js (v18.x or higher)
* npm or yarn
* A Supabase project instance

### Local Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/edutrack.git](https://github.com/your-username/edutrack.git)
   cd edutrack

---
### Install dependencies:

npm install

### Configure Environment Variables:

#### Create a .env.local file in the root directory:


NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key


### Run the development server:

npm run dev

Open http://localhost:3000 in your browser.

---
## 👥 Contributors

* [Tasnim Haque Ankhi](https://github.com/TasnimHaque123) 
* [Md. Mehedi Hasan Rifat](https://github.com/your-username) 
* [Ahad Hosen Akash](https://github.com/AHAAkash) 
* [Samir Baishnab](https://github.com/your-username) 

---

## 📁 Project Structure

EduTrack follows a **Vertical Slice Architecture**, isolating domain features into self-contained modules:

```text
src/
├── app/                  # Next.js App Router (Role-based route groups)
│   ├── (auth)/           # Sign-in & Sign-up routes
│   ├── admin/            # Admin dashboard & management
│   ├── teacher/          # Teacher course & quiz controls
│   ├── student/          # Student portal & quiz attempt views
│   ├── dean/             # Dean oversight dashboard shell
│   └── chairman/         # Chairman oversight dashboard shell
├── components/           # Reusable UI components
├── features/             # Vertical slice domain modules (actions, services, schemas)
│   ├── auth/
│   ├── course/
│   ├── student-quiz/
│   ├── teacher-quiz/
│   └── attendance/
└── lib/                  # Supabase clients & utility helpers
