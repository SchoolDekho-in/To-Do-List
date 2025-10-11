# Project Requirements: SchoolDekho.in

## 1. 🚀 Project Overview

**SchoolDekho.in** is a comprehensive educational platform designed to connect parents and students with schools, colleges, and financial aid opportunities. The platform will feature a powerful search engine, comparison tools, scholarship/loan applications, and an AI-powered chatbot to provide a seamless user experience. The frontend will be built with **Next.js** for optimal performance and SEO, styled efficiently with **Tailwind CSS**.

---

## 2. 💻 Tech Stack 

### Core Technologies:

-   **Base Framework:** **Next.js** (Frontend) + **Node.js/Express.js** (Backend)
-   **Frontend :** **Next.js** (v14+)
    -   **Styling:** **Tailwind CSS**
    -   **Animations:** Framer Motion
    -   **State Management:** React Context API, Zustand, or Redux Toolkit (if global state is complex)
    -   **Data Fetching:** React Query (TanStack Query) or SWR
    -   **UI Components:** Headless UI (for unstyled, accessible components) or custom components built with Tailwind.
-   **Backend:** **Node.js** with **Express.js**
    -   **Authentication:** JWT (JSON Web Tokens)
-   **Database:** **Supabase** (utilizing its managed **PostgreSQL** database)
    -   **GIS Functionality:** PostGIS extension for efficient location-based queries.
-   **AI & NLP Engine:** **OpenAI API (GPT-4)** for the chatbot's reasoning and response generation.
    -   **Chatbot Framework:** Custom implementation using Node.js backend.
-   **Cloud & Media:**
    -   **Image/Video Storage:** **Cloudinary API** for hosting all school-related media.
    -   **Deployment (Next.js):** Vercel (recommended for Next.js)
    -   **Deployment (Backend):** AWS EC2 / Heroku / DigitalOcean
-   **Testing:**
    -   **Unit/Integration:** Jest, React Testing Library
    -   **End-to-End:** Cypress

---

## 3. 📄 Page & Application Structure

### Common Pages:
-   **Login/Signup Page:** With options to register/login as a 'User' or 'School Admin'.

### User Flow:
-   **Homepage:** Hero section with a prominent search bar, featured schools, testimonials, and clear calls-to-action.
-   **School Search & Listing Page:** Displays search results with advanced filters.
-   **School Comparison Page:** Side-by-side comparison of up to 3-4 selected schools based on key metrics.
-   **Fundraising Page:** Browse active fundraising campaigns or start a new one.
-   **Scholarships Page:** List of available scholarships with filter options.
-   **Loans Application Page:** A step-by-step form to apply for educational loans.
-   **User Dashboard:** A personalized space showing:
    -   Status of submitted applications (loans, scholarships).
    -   Saved schools list.
    -   Donations made.
    -   Profile settings.
-   **AI Chatbot:** Accessible globally via a floating action button.

### School Admin Portal Flow (Angular Frontend):
-   **School Registration/Onboarding Page:** A multi-step form for schools to register. Gathers basic info and requires document uploads for verification by the Super Admin.
-   **School Admin Dashboard:** Central hub displaying key metrics:
    -   Profile completion status/score.
    -   Profile views and engagement statistics.
    -   Number of new inquiries received.
    -   Recent parent reviews.
-   **Profile Management Section:** A comprehensive interface for admins to build and update their school's public profile, including:
    -   **Basic Information:** School name, address, contact details, board affiliation.
    -   **Academics:** Curriculum details, subjects offered, grade levels.
    -   **Infrastructure & Facilities:** Upload photos and descriptions of the campus, labs, library, sports facilities, etc.
    -   **Admissions:** Detailed admission process, key dates, and a dynamic fee structure table.
    -   **Gallery Management:** A dedicated section to upload and manage high-resolution photos and videos.
    -   **News & Events:** A publisher to post announcements and school events.
-   **Inquiry Management:** A built-in messaging system to view and respond to inquiries from parents and students.

### Super Admin Portal Flow:
-   **Super Admin Dashboard:** Overview of platform health, key statistics, and pending actions.
    -   Total registered users, active schools, pending school verifications.
    -   Recent financial activities (donations, loan disbursements).
-   **School Verification & Management:**
    -   List of all registered schools, with status (Pending, Approved, Rejected, Blocked).
    -   Detailed view for each school: review submitted registration documents, approve/reject registration.
    -   Ability to edit any school's public profile.
    -   Ability to suspend or delete school accounts.
-   **User Management:**
    -   List of all parent/student users.
    -   Ability to view user profiles, manage account status (block/unblock), and reset passwords.
-   **Content Moderation:**
    -   Review user-submitted reviews and ratings for schools.
    -   Moderate any objectionable content (e.g., news/events posted by schools).
-   **Financial Oversight:**
    -   Manage loan and scholarship programs: add new schemes, set eligibility criteria.
    -   Approve or reject loan applications (after initial automated checks).
    -   Track all donations and financial transactions.
-   **Platform Settings:** Manage global settings, API keys, notification templates.
-   **Analytics & Reporting:** Generate custom reports on platform usage, school performance, user engagement, etc.

---

## 4. 🎨 Design System (Tailwind CSS Integration)

### 01 TYPOGRAPHY SYSTEM
-   **Font Family:** 'Inter' or 'Poppins' (sans-serif) - *Configured in `tailwind.config.js`*
-   **Font Sizes (px):**
    -   `text-xs` (10px) / `text-sm` (12px) / `text-base` (14px) / `text-lg` (16px) / `text-xl` (18px) / `text-2xl` (20px) / `text-3xl` (24px) / `text-4xl` (30px) / `text-5xl` (36px) / `text-6xl` (44px) / `text-7xl` (52px) / `text-8xl` (62px) / `text-9xl` (74px) - *Custom font sizes may be extended in `tailwind.config.js` for larger values.*
-   **Font Weights:** `font-normal` (400), `font-medium` (500), `font-semibold` (600), `font-bold` (700)
-   **Line Heights:** `leading-tight` (1.05), `leading-normal` (1.2), `leading-relaxed` (1.6) - *Default line height for text is often `leading-none` (1) or `leading-tight` in Tailwind.*
-   **Letter Spacing:** `tracking-tighter` (-0.5px), `tracking-wide` (0.75px) - *Custom values can be added to `tailwind.config.js`.*

### 02 COLORS
-   **Primary:** `school-blue` (`#0057FF`)
-   **Tints:** `school-blue-100` (`#E6F0FF`), `school-blue-300` (`#B3D1FF`)
-   **Shades:** `school-blue-700` (`#0043CC`), `school-blue-900` (`#002A80`)
-   **Accents:** `school-yellow` (`#FFC700`), `school-green` (`#28A745`)
-   **Greys:**
    -   `gray-50` (`#F8F9FA`)
    -   `gray-200` (`#E9ECEF`)
    -   `gray-600` (`#6C757D`)
    -   `gray-900` (`#212529`)
-   *These custom colors will be defined in `tailwind.config.js`.*

### 03 SHADOWS
-   **Card Shadow:** `shadow-md` (Tailwind default or custom `shadow-school-card`)
-   **Hover Shadow:** `shadow-lg` (Tailwind default or custom `shadow-school-hover`)
-   *Custom shadows can be extended in `tailwind.config.js`.*

### 04 BORDER-RADIUS
-   **Default:** `rounded-lg` (8px-12px range, can be customized)
-   **Medium:** `rounded-xl` (12px-16px range, can be customized)
-   *Custom `borderRadius` values can be added to `tailwind.config.js`.*

### 05 WHITESPACE
-   **Spacing System (px):** `space-x/y-0.5` (2px) / `space-x/y-1` (4px) / `space-x/y-2` (8px) ... up to `space-x/y-32` (128px) - *Tailwind's default spacing scale covers most of these, custom values can be added.*

---

## 5. 🌐 Social Media Strategy

-   **Platforms:** Facebook, Instagram, LinkedIn.
-   **Goals:** Build brand awareness, drive website traffic, and engage with the parent/student community.
-   **Content Pillars:**
    1.  **Informative Tips:** Posts on "How to choose a school," "Understanding different curricula," etc.
    2.  **School Spotlights:** Feature partner schools and their unique offerings.
    3.  **Community Engagement:** Run polls, Q&As, and share user-generated content.
    4.  **Platform Updates:** Announce new features, scholarships, or loan partners.

---

## 6. 🔍 Core Features

-   **AI Chatbot:**
    -   **Purpose:** Assist users with school searches, loan guidance, scholarship info, and application status.
    -   **Technology:** Integrated via a custom NLP backend using the **OpenAI API**.
    -   **Features:** Real-time analytics on user queries to improve responses.
-   **Advanced Search & Filters:**
    -   **Filters:** Location, Board (CBSE, ICSE), Type (Day School, Boarding), Fee Range, Ratings.
    -   **Search Bar:** Instant, real-time search with fuzzy matching and autocomplete.
-   **Geolocation:**
    -   **Auto-Detection:** Uses browser geolocation to suggest nearby schools.
    -   **Manual Search:** Allows users to search by city or pin on a map.
-   **Finance & Aid:**
    -   **Payments:** Secure **UPI integration** for donations and application fees.
    -   **AI Recommendations:** AI-based system to recommend suitable scholarships and loans based on user profiles.
-   **Notifications:**
    -   **Push Notifications:** For application status updates and important reminders.
    -   **Email/SMS Notifications:** For account verification and critical alerts.

---

## 7. 👥 User Roles & Access

### 1. Parent/Student User
-   **Access:** Search/compare schools, apply for loans/scholarships, join fundraisers, interact with the AI chatbot.
-   **Goal:** To find the perfect educational institution and financial support.

### 2. School Admin
-   **Access:** Manage their school's profile (academics, infrastructure, events), handle inquiries, and manage the alumni network.
-   **Goal:** To showcase their institution and attract prospective students.

### 3. Super Admin (SchoolDekho Team)
-   **Access:** Full control over the platform. Manage school listings, verify new accounts, oversee user roles, and generate platform-wide analytics.
-   **Goal:** To ensure data integrity, platform growth, and smooth operation.

---

## 8. 🔌 Required APIs

### Internal APIs (Built by our Backend Team)
-   `/api/auth/`: User/Admin registration, login, and password management.
-   `/api/schools/`: CRUD operations for school listings, search, and filtering.
-   `/api/users/`: Manage user profiles and dashboards.
-   `/api/applications/`: Handle loan and scholarship application submissions.
-   `/api/payments/`: Process donations and fees.
-   `/api/chatbot/`: Handle communication between the frontend and the AI engine.

### External (Third-Party) APIs
-   **Google Maps Platform:**
    -   **Geolocation API:** To determine a user's current location.
    -   **Places API:** For school address autocomplete and details.
    -   **Maps JavaScript API:** To display interactive maps.
-   **OpenAI API:** To power the NLP and conversational abilities of the chatbot.
-   **Cloudinary API:** For uploading, storing, and delivering all images and video assets.
-   **Payment Gateway API (e.g., Razorpay, Stripe):** To handle all UPI and card transactions securely.
-   **Email/SMS Gateway API (e.g., SendGrid, Twilio):** To send transactional emails (verification, notifications) and SMS alerts.

