# 🌍 LagaTour - Social Media Tour Planner & Collaborative Travel Platform

[![Live Demo](https://img.shields.io/badge/Demo-Live%20Website-brightgreen?style=for-the-badge&logo=vercel)](https://laga-tour-flax.vercel.app/)
[![GitHub Repo](https://img.shields.io/badge/GitHub-NurTamim331%2FLagaTour-blue?style=for-the-badge&logo=github)](https://github.com/NurTamim331/LagaTour.git)
[![Backend Status](https://img.shields.io/badge/Backend-Render%20Live-46E3B7?style=for-the-badge&logo=render)](https://lagatour-api.onrender.com/api/health)
[![Database](https://img.shields.io/badge/Database-TiDB%20Cloud%20Serverless-F37021?style=for-the-badge&logo=mysql)](https://tidbcloud.com)

**LagaTour** is a modern full-stack travel community platform and social tour organizer designed to revolutionize tourism in Bangladesh. It allows travelers to design and generate AI-powered itineraries, record live GPS coordinates across all 64 districts, discover tourist spots, collaborate on group expeditions with expense splitters, rate community safety, and connect in real time.

---

## 🔗 Live Deployments

- 🌐 **Live Web Application**: [https://laga-tour-flax.vercel.app/](https://laga-tour-flax.vercel.app/)
- 📡 **Production API Server**: [https://lagatour-api.onrender.com/](https://lagatour-api.onrender.com/)
- 💚 **Backend Healthcheck**: [https://lagatour-api.onrender.com/api/health](https://lagatour-api.onrender.com/api/health)
- 🐙 **Source Code**: [https://github.com/NurTamim331/LagaTour.git](https://github.com/NurTamim331/LagaTour.git)

---

## 🏛️ System Architecture

```mermaid
flowchart TD
    User["🌍 Global Travelers"] -->|HTTPS / Browsing| Vercel["⚡ Vercel (React 19 + Vite SPA)"]
    Vercel -->|REST API Requests| Render["🚀 Render (Node.js + Express API)"]
    Vercel <-->|WebSockets (Live Chat)| Render
    Render -->|Encrypted TLS/SSL Pool| TiDB["🗄️ TiDB Cloud Serverless (MySQL)"]
    Render -->|AI Package Builder & Moderation| Gemini["🧠 Google Gemini 1.5 Flash API"]
    Render -->|OTP Email Verification| SMTP["📧 Gmail SMTP (Nodemailer)"]
    Vercel -->|Zero-Shot Vision Moderation| ONNX["🤖 Transformers.js (In-Browser WebAssembly)"]
```

---

## ✨ Key Features & Built Modules

### 1. 🧠 AI Tour Package Builder & Generator
- **Powered by Google Gemini 1.5 Flash**: Generates intelligent dual-package itineraries (Customized AI Budget vs. Database-Driven Heritage Plan).
- **Comprehensive Trip Parameters**: Input starting location, destination, duration (1–10 days), budget, transport type, and travel style.
- **Sequential Itineraries**: Daily morning, afternoon, and evening breakdowns with food suggestions and realistic local travel heuristics.
- **One-Click Sync**: Converts any generated AI tour package directly into a shareable public expedition plan.

### 2. 🗺️ Smart Interactive Map Explorer
- **OpenStreetMap & Leaflet Integration**: Custom GPS markers, cluster views, and division/district boundaries.
- **Interactive Discoveries**: Filter by safety rating (Safe, Moderate, Caution), division, or district across all 64 districts.
- **Live Coordinate Locking**: Pinpoint locations on the interactive map to preview coordinates before saving.

### 3. 📍 GPS Places & Community Safety Directory
- **1-Click Live Location Recording**: High-precision browser GPS capture with automatic discovery points (+25 pts).
- **Tourist Safety Ratings & Reviews**: Community ratings (1.0 to 5.0 stars) with moderated safety tips.
- **Photo Carousel**: Multi-image uploads with carousel navigation for every destination.

### 4. 👥 Collaborative Group Expeditions & Trip Planner
- **Multi-User Expedition Management**: Join requests, approval workflows, and organizer controls.
- **Joint Expense Tracker**: Real-time spending breakdowns, individual payer logs, and auto-calculated cost per traveler.
- **Shared Packing & Preparation Checklist**: Interactive task assignment and status tracking.
- **Dedicated Group Chat**: Instant messaging per expedition to coordinate logistics.

### 5. 💬 Real-Time Messaging & Direct Chat
- **Socket.IO WebSockets**: Instant message delivery with sub-second latency.
- **Presence & Room Management**: Online/offline indicators, typing notifications, and unread badges.
- **Direct & Group Chats**: Seamless navigation between 1-on-1 conversations and expedition channels.

### 6. 📸 Social Feed & Traveler Community
- **Visual Travel Stories**: Share travel photos, captions, tagged destinations, and duration tags.
- **Engagement Tools**: Instant likes, nested comment threads, bookmarks/saves, and social sharing.
- **Flag & Report System**: Community moderation with administrative review queues.

### 7. 🛡️ AI Content Moderation & Photographic Realism
- **Dual-Layer Protection**:
  1. *Client-side*: Zero-Shot semantic classification via HuggingFace Transformers.js (`Xenova/clip-vit-base-patch32`) in browser WebAssembly.
  2. *Server-side*: Google Gemini Vision AI inspection for image uploads.
- **Blocks**: Clip-art, 2D vector illustrations, memes, text circulars, documents, and NSFW content to ensure high-quality authentic travel photos.

### 8. 🏆 Traveler Leagues & Gamification
- **Point Accumulation System**: Points rewarded for writing stories (+15), recording places (+25), linking verified spots (+50), and leaving safety reviews (+10).
- **5 Progressive Tiers**:
  - 🥉 **Explorer** (0 - 299 pts)
  - 🥈 **Adventurer** (300 - 999 pts)
  - 🥇 **Traveler** (1,000 - 1,999 pts)
  - 💎 **Expert** (2,000 - 3,999 pts)
  - 👑 **Legend** (4,000+ pts)

### 9. 🔐 Authentication & Security
- **Email OTP Verification**: 6-digit verification codes sent via Gmail SMTP for sign-up and password reset.
- **Encrypted Password Security**: Password hashing with `bcryptjs`.
- **Administrative Portal**: Dedicated dashboard for user management, account suspension, reported post moderation, and platform statistics.

---

## 🛠️ Tech Stack

| Category | Technology | Usage |
| :--- | :--- | :--- |
| **Frontend Framework** | **React 19** (Vite 8) | Single Page Application (SPA) architecture |
| **Styling & UI** | **Tailwind CSS 3 + DaisyUI 4** | Responsive modern glassmorphic travel design |
| **Icons & Media** | **Lucide React + Canvas Confetti** | Crisp UI icons and interactive feedback |
| **Maps & Geospatial** | **Leaflet 1.9 + OpenStreetMap** | Interactive vector map and GPS pinpoints |
| **Client-Side AI** | **@xenova/transformers (ONNX)** | In-browser zero-shot image classification |
| **Backend API** | **Node.js (ESM) + Express 4** | Scalable REST API with centralized routing |
| **Real-time Engine** | **Socket.IO 4.8** | Persistent WebSockets for live chat |
| **Database** | **TiDB Cloud Serverless (MySQL)** | High-availability cloud relational database with SSL |
| **Database Driver** | **mysql2/promise** | Connection pool with automatic schema initialization |
| **AI Services** | **Google Gemini 1.5 Flash API** | AI Tour Itinerary Builder & Vision Moderation |
| **Email Services** | **Nodemailer + Gmail SMTP** | Transactional 6-digit OTP delivery |
| **Hosting Platforms** | **Vercel** (Frontend) + **Render** (Backend) | 100% Free continuous cloud hosting |

---

## 🚀 Local Development Setup

### 1. Prerequisites
- **Node.js**: v18.0.0 or higher
- **npm**: v9.0.0 or higher
- **Git**

### 2. Clone the Repository
```bash
git clone https://github.com/NurTamim331/LagaTour.git
cd LagaTour
```

### 3. Install Dependencies
```bash
# Install frontend dependencies
npm install

# Install backend dependencies
cd server
npm install
cd ..
```

### 4. Configure Environment Variables

#### Backend (`server/.env`):
Create `server/.env` with your database credentials (or copy from `server/.env.example`):
```env
PORT=5000

# TiDB Cloud (or local XAMPP MySQL)
DB_HOST=gateway01.ap-northeast-1.prod.aws.tidbcloud.com
DB_PORT=4000
DB_USER=your_tidb_user.root
DB_PASSWORD=your_tidb_password
DB_NAME=lagatour_db
DB_SSL=true

# Email Verification (Gmail SMTP)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=465
SMTP_SECURE=true
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_gmail_app_password
SMTP_FROM="Laga Tour Official <your_email@gmail.com>"

# Google Gemini AI
GEMINI_API_KEY=your_gemini_api_key
```

#### Frontend (`.env`):
Create `.env` in the root folder:
```env
VITE_API_URL=http://localhost:5000/api
VITE_SOCKET_URL=http://localhost:5000
```

### 5. Run the Application
Open two terminal windows:

**Terminal 1 (Backend Server):**
```bash
npm run server
```
*The server will connect to TiDB Cloud (or local MySQL), automatically create all missing tables, and seed initial demo data.*

**Terminal 2 (Frontend Client):**
```bash
npm run dev
```
Open **[http://localhost:5173](http://localhost:5173)** in your browser.

---

## 🧪 Running Automated Tests

LagaTour includes a suite of pytest integration tests:
```bash
# Run all tests
npm test

# Run AI package generator and expedition sync tests
npm run test:ai
```

---

## 📦 Production Deployment Summary

- **Frontend**: Hosted on [Vercel](https://vercel.com) using the `Vite` preset with client-side SPA routing (`vercel.json`).
- **Backend**: Hosted on [Render](https://render.com) as a continuous Node Web Service with persistent WebSocket support.
- **Database**: Cloud MySQL hosted on [TiDB Cloud](https://tidbcloud.com) with automated table migrations and SSL encryption.

---

## 👥 Authors & Contributors

- **MD Nur Uddin Tamim** ([@NurTamim331](https://github.com/NurTamim331))
- **LagaTour Engineering Team**

---

## 📄 License

This project is licensed under the **MIT License** - see the LICENSE file for details.
