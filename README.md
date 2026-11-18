# Planazo 🎈

[![Next.js 15](https://img.shields.io/badge/Next.js-15-black?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org/)
[![React 19](https://img.shields.io/badge/React-19-blue?style=for-the-badge&logo=react&logoColor=61DAFB)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Zustand](https://img.shields.io/badge/State-Zustand-orange?style=for-the-badge&logo=react&logoColor=white)](https://zustand-demo.pmnd.rs/)
[![Supabase](https://img.shields.io/badge/Supabase-Auth_%26_DB-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)](https://supabase.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

> **A real-time community & local event discovery platform.**  
> Connects people through shared interests, regional group chats, and community-created events ("planazos") using a high-performance **three-column layout** inspired by modern collaborative applications.

---

## 🧭 Live Demo

- **Production App**: [planazo.online](https://planazo.online)
- **Repository**: [github.com/rawcorn/planazo-app](https://github.com/rawcorn/planazo-app)

---

## 🌟 Key Architecture & Features

### 1. High-Performance Three-Column Layout (Discord / Telegram-inspired)
- **Left Column (Navigation & Channels)**: Instant switching between regional community rooms, direct 1-to-1 conversations, and user profile management.
- **Center Column (Live Chat Engine)**: Real-time message streaming, active participants, system announcements for newly published events, and direct messaging.
- **Right Column (Dynamic Context Inspector)**: Context-aware interactive panel that dynamically surfaces:
  - Regional Events Billboard (filterable by category, tags, and date).
  - Event Creation Form with custom image upload and date/time pickers.
  - Interactive Event Details & real-time attendee list.
  - Member Public Profile Viewer.

### 2. Events & "Planazos" Engine
- **Event Management**: Create community events with titles, descriptions, custom image assets (hosted on Supabase Storage), exact venue addresses, and participant caps.
- **Smart Filtering**: Multi-parameter search by geographical region, category interests, and attendee capacity restrictions.
- **Dynamic Attendance**: Real-time RSVP management allowing users to join or leave events with instant state synchronization.

### 3. Authentication & Profile Security
- **Passwordless & Password Auth**: Built on Supabase Auth with custom transactional email delivery and secure token-based password reset flows.
- **Detailed Profiles**: Avatars, age, gender, geographic region, social links (Instagram), and curated interest tags.
- **Row Level Security (RLS)**: Enforced directly on PostgreSQL tables to ensure private messages and user profile changes are strictly authorized at the database level.

---

## 📂 Project Structure

```bash
planazo-app/
├── public/                 # Static assets, branding, and PWA manifest
├── src/
│   ├── app/                # Next.js App Router
│   │   ├── actions/        # Server actions (auth, catalog, events, messages, storage)
│   │   ├── globals.css     # Global styles and responsive layout utilities
│   │   ├── layout.tsx      # Root layout, fonts, and meta tags
│   │   └── page.tsx        # Main application three-column viewport
│   ├── components/
│   │   ├── auth/           # Login, registration & password recovery views
│   │   ├── layout/         # LeftColumn, CenterColumn, and RightColumn architecture
│   │   └── ui/             # Reusable UI controls, custom DatePicker & TimePicker
│   ├── lib/
│   │   ├── supabase/       # Server and client Supabase SDK instances
│   │   └── validations.ts  # Zod validation schemas for forms and inputs
│   ├── store/
│   │   └── uiStore.ts      # Reactive Zustand store managing panels & selected channels
│   └── types/              # Full TypeScript models and database contracts
├── supabase/
│   └── schema.sql          # Production PostgreSQL database schema, tables & RLS
├── .env.example            # Environment variables template
├── package.json            # Project dependencies & build scripts
└── tsconfig.json           # TypeScript configuration
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Framework** | [Next.js 15](https://nextjs.org/) (App Router & Server Actions) |
| **Frontend UI** | [React 19](https://react.dev/) |
| **Language** | [TypeScript 5](https://www.typescriptlang.org/) |
| **Styling** | [Tailwind CSS 3.4](https://tailwindcss.com/) |
| **State Management** | [Zustand](https://zustand-demo.pmnd.rs/) |
| **Validation** | [Zod](https://zod.dev/) & React Hook Form |
| **Database & Auth** | [Supabase](https://supabase.com/) (PostgreSQL + RLS + Storage) |
| **Icons** | [Lucide React](https://lucide.dev/) |
| **Deployment** | [Vercel](https://vercel.com/) |

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/rawcorn/planazo-app.git
cd planazo-app
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Setup Environment Variables
Create a `.env.local` file with your Supabase credentials:
```env
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
SUPABASE_SERVICE_ROLE_KEY=your-service-role-key
```

### 4. Run Development Server
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser.

### 5. Production Build
```bash
npm run build
npm run start
```

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
