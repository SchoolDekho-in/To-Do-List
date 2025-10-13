# 📁 SchoolDekho.in - Project Folder Structure

## Root Directory
.
├── 📁 client/                      # Frontend (Next.js 14 + Tailwind CSS)
├── 📁 server/                      # Backend (Node.js + Express)
├── 📁 docs/                        # Documentation & Diagrams
├── 📁 scripts/                     # Deployment or automation scripts
├── .env                            # Environment variables (shared secrets)
├── package.json                    # Root dependencies (optional if monorepo)
├── README.md                       # Project overview
└── turbo.json / nx.json            # Monorepo workspace config (if using Turborepo/Nx)

---

## 🧩 CLIENT (Next.js Frontend)
📁 client/
├── 📁 public/                      # Static assets
│   ├── 📁 images/                  # Logos, icons, banners
│   ├── 📁 fonts/                   # Custom fonts (e.g., Poppins, Inter)
│   └── favicon.ico
│
├── 📁 src/
│   ├── 📁 app/                     # Next.js App Router (v14+)
│   │   ├── layout.tsx
│   │   ├── page.tsx               # Homepage
│   │   ├── 📁 (auth)/             # Group routes for auth
│   │   │   ├── login/page.tsx
│   │   │   ├── signup/page.tsx
│   │   │   └── reset-password/page.tsx
│   │   ├── 📁 user/
│   │   │   ├── dashboard/page.tsx
│   │   │   ├── profile/page.tsx
│   │   │   └── applications/page.tsx
│   │   ├── 📁 schools/
│   │   │   ├── page.tsx           # Search & listing page
│   │   │   ├── [id]/page.tsx      # Individual school details
│   │   │   └── compare/page.tsx
│   │   ├── 📁 scholarships/
│   │   │   └── page.tsx
│   │   ├── 📁 loans/
│   │   │   └── apply/page.tsx
│   │   ├── 📁 fundraising/
│   │   │   ├── page.tsx
│   │   │   └── create/page.tsx
│   │   ├── 📁 admin/
│   │   │   ├── dashboard/page.tsx
│   │   │   ├── manage-school/page.tsx
│   │   │   └── inquiries/page.tsx
│   │   ├── 📁 super-admin/
│   │   │   ├── dashboard/page.tsx
│   │   │   ├── schools/page.tsx
│   │   │   ├── users/page.tsx
│   │   │   ├── finance/page.tsx
│   │   │   ├── content/page.tsx
│   │   │   └── reports/page.tsx
│   │   └── 📁 api/                # Next.js API routes (if required)
│   │       └── chatbot/route.ts
│   │
│   ├── 📁 components/             # Reusable UI components
│   │   ├── 📁 ui/                 # Buttons, Modals, Dropdowns
│   │   ├── 📁 forms/              # Custom form components
│   │   ├── 📁 cards/              # School cards, Scholarship cards
│   │   ├── 📁 layout/             # Navbar, Footer, Sidebar
│   │   ├── 📁 chatbot/            # Chatbot widget
│   │   └── index.ts
│   │
│   ├── 📁 context/                # Context API for global state
│   │   ├── AuthContext.tsx
│   │   ├── ThemeContext.tsx
│   │   └── ChatContext.tsx
│   │
│   ├── 📁 store/                  # Zustand/Redux global store
│   │   ├── userStore.ts
│   │   ├── schoolStore.ts
│   │   └── uiStore.ts
│   │
│   ├── 📁 hooks/                  # Custom React hooks
│   │   ├── useAuth.ts
│   │   ├── useFetch.ts
│   │   ├── useChatbot.ts
│   │   └── useGeolocation.ts
│   │
│   ├── 📁 lib/                    # Utility functions & configurations
│   │   ├── api.ts                 # API wrappers for backend calls
│   │   ├── supabaseClient.ts
│   │   ├── cloudinary.ts
│   │   ├── openai.ts
│   │   └── maps.ts
│   │
│   ├── 📁 styles/                 # Global and Tailwind styles
│   │   ├── globals.css
│   │   ├── tailwind.css
│   │   └── animations.css
│   │
│   ├── 📁 utils/                  # Helper utilities
│   │   ├── constants.ts
│   │   ├── formatters.ts
│   │   ├── validations.ts
│   │   └── analytics.ts
│   │
│   ├── 📁 tests/                  # Jest + React Testing Library
│   │   ├── components/
│   │   ├── pages/
│   │   └── utils/
│   │
│   ├── tailwind.config.js
│   ├── postcss.config.js
│   └── next.config.js
│
└── package.json

---

## ⚙️ SERVER (Node.js + Express Backend)
📁 server/
├── 📁 src/
│   ├── index.js                   # Entry point (Express app setup)
│   ├── server.js                  # App bootstrap (connect DB, start server)
│   │
│   ├── 📁 config/                 # Environment & service configurations
│   │   ├── db.js                  # Supabase/PostgreSQL connection
│   │   ├── cloudinary.js
│   │   ├── openai.js
│   │   ├── maps.js
│   │   ├── jwt.js
│   │   └── payment.js             # Razorpay/Stripe setup
│   │
│   ├── 📁 routes/                 # Express routers
│   │   ├── authRoutes.js
│   │   ├── schoolRoutes.js
│   │   ├── userRoutes.js
│   │   ├── applicationRoutes.js
│   │   ├── paymentRoutes.js
│   │   └── chatbotRoutes.js
│   │
│   ├── 📁 controllers/            # Route logic handlers
│   │   ├── authController.js
│   │   ├── schoolController.js
│   │   ├── userController.js
│   │   ├── applicationController.js
│   │   ├── paymentController.js
│   │   └── chatbotController.js
│   │
│   ├── 📁 models/                 # Database schemas (if using Sequelize/Prisma)
│   │   ├── User.js
│   │   ├── School.js
│   │   ├── Application.js
│   │   ├── Fundraiser.js
│   │   └── Review.js
│   │
│   ├── 📁 middlewares/
│   │   ├── authMiddleware.js
│   │   ├── errorHandler.js
│   │   ├── uploadMiddleware.js
│   │   └── rateLimiter.js
│   │
│   ├── 📁 services/               # External integrations (AI, Cloud, Payments)
│   │   ├── openaiService.js
│   │   ├── cloudinaryService.js
│   │   ├── paymentService.js
│   │   ├── emailService.js
│   │   └── notificationService.js
│   │
│   ├── 📁 utils/
│   │   ├── validators.js
│   │   ├── helpers.js
│   │   ├── constants.js
│   │   └── logger.js
│   │
│   ├── 📁 tests/                  # Jest/Cypress backend tests
│   │   ├── routes/
│   │   ├── controllers/
│   │   └── utils/
│   │
│   └── 📁 logs/
│       └── server.log
│
├── package.json
└── README.md

---

## 📘 DOCS
📁 docs/
├── architecture-diagram.png
├── database-schema.sql
├── api-reference.md
├── feature-list.md
├── deployment-guide.md
└── ui-wireframes.pdf

---

## ⚡ SCRIPTS
📁 scripts/
├── deploy-client.sh
├── deploy-server.sh
├── backup-db.sh
└── seed-data.js

