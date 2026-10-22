# LagaTour
### A Community-Driven Travel Planning & Social Discovery Platform for Bangladesh

---

**Course Title:** Software Engineering Laboratory  
**Department:** Computer Science and Engineering  
**University:** United International University

---

| **Team Member** | **Student ID** |
|---|---|
| Nur Tamim | — |

**Project Repository:** [github.com/NurTamim331/LagaTour](https://github.com/NurTamim331/LagaTour)

---

## Table of Contents

1. [Program Outcomes](#1-program-outcomes)
2. [Abstract](#2-abstract)
3. [Introduction](#3-introduction)
4. [Motivation](#4-motivation)
5. [Objectives of the System](#5-objectives-of-the-system)
6. [System Overview](#6-system-overview)
7. [Feature Description](#7-feature-description)
   - 7.1 [Social Travel Feed](#71-social-travel-feed)
   - 7.2 [Tour Plans & Itinerary Builder](#72-tour-plans--itinerary-builder)
   - 7.3 [AI Tour Builder](#73-ai-tour-builder)
   - 7.4 [Map Explorer & Places Directory](#74-map-explorer--places-directory)
   - 7.5 [Group Expedition Planner](#75-group-expedition-planner)
   - 7.6 [Community Leaderboards & Rankings](#76-community-leaderboards--rankings)
   - 7.7 [Gamification & Traveler Score System](#77-gamification--traveler-score-system)
   - 7.8 [Public User Profiles](#78-public-user-profiles)
   - 7.9 [Messaging & Inbox](#79-messaging--inbox)
   - 7.10 [Admin Panel](#710-admin-panel)
   - 7.11 [Dynamic Theme System](#711-dynamic-theme-system)
8. [Technology Stack](#8-technology-stack)
   - 8.1 [Architecture Overview](#81-architecture-overview)
   - 8.2 [Frontend Technologies](#82-frontend-technologies)
   - 8.3 [Backend Technologies](#83-backend-technologies)
   - 8.4 [Database Architecture](#84-database-architecture)
   - 8.5 [AI Integration](#85-ai-integration)
   - 8.6 [Real-Time Communication](#86-real-time-communication)
   - 8.7 [Authentication & Security](#87-authentication--security)
   - 8.8 [Testing Infrastructure](#88-testing-infrastructure)
9. [System Testing and Validation](#9-system-testing-and-validation)
10. [Challenges](#10-challenges)
11. [Future Enhancements](#11-future-enhancements)
12. [Conclusion](#12-conclusion)
13. [References](#13-references)

---

## 1. Program Outcomes

| **Program Outcome (PO)** | **Project Alignment** |
|---|---|
| **PO2: Problem Analysis** | The project identifies key pain points in travel planning for Bangladeshi travelers, including fragmented itinerary tools, lack of community-verified destination safety information, and the absence of locally-grounded AI recommendations. A structured technical solution was derived from this analysis. |
| **PO3: Design and Development of Solutions** | LagaTour was designed with a modular full-stack architecture. Complex sub-systems including a dual-engine AI builder, a gamification engine, real-time WebSocket messaging, and a community safety reporting system were designed and implemented independently while remaining cohesively integrated. |
| **PO5: Modern Tool Usage** | Modern engineering tools and frameworks were used throughout development. The frontend was built with React 19 and Vite 8, the backend with Node.js and Express.js, and AI capabilities were delivered via the Google Gemini API. Firebase was used for image hosting, and Leaflet.js for interactive maps. Selenium and pytest were used for automated UI testing. |
| **PO8: Ethics** | User safety and data integrity were core design priorities. Image uploads are subject to AI-based content moderation before publication. Safety reporting mechanisms allow community members to flag dangerous destinations. Administrative controls ensure content accountability. |
| **PO9: Individual and Teamwork** | The project was developed with clearly separated concerns across the frontend, backend, database, AI layer, and testing suite, demonstrating both individual ownership of modules and unified integration. |
| **PO10: Communication** | The platform itself facilitates communication between travelers through direct messaging and group chat. Technically, the system architecture is documented comprehensively and RESTful API contracts are maintained throughout the codebase. |
| **PO12: Lifelong Learning** | The development process required independent research into retrieval-augmented generation (RAG) patterns, real-time WebSocket architecture, client-side image compression, and gamification design — technologies beyond the standard coursework. |

---

## 2. Abstract

Tourism in Bangladesh remains underserved by modern digital tooling. Most travelers rely on fragmented social media posts, outdated blogs, or word-of-mouth for trip planning, with no unified platform that combines community knowledge, safety data, and intelligent itinerary generation. This report presents **LagaTour**, a full-stack web-based travel planning and social discovery platform designed specifically for Bangladesh's traveler community.

LagaTour provides a comprehensive suite of features including a community social travel feed, multi-leg itinerary builder, an AI-powered dual-engine tour package generator (Google Gemini API), an interactive map explorer with community-reported safety alerts, group expedition planning tools, gamified rankings, real-time direct messaging, and a moderated admin panel. Built on React 19, Node.js, Express.js, MySQL, and Socket.io, the platform delivers a responsive, scalable, and secure experience.

The project demonstrates the practical application of modern software engineering principles — including modular architecture design, RESTful API development, real-time communication, automated UI testing with Selenium, and AI-assisted feature development — applied to a genuine and locally meaningful problem domain.

---

## 3. Introduction

Bangladesh possesses a wealth of natural and cultural tourist destinations — from the world's largest mangrove forest at the Sundarbans to the hill-station valleys of Bandarban and the scenic tea gardens of Sreemangal. Despite this richness, there is no dedicated digital platform that serves the Bangladeshi traveler community with curated, community-driven, and intelligently generated travel plans.

Existing general-purpose travel platforms such as TripAdvisor or Google Travel are not tailored to Bangladesh's specific geography, transportation infrastructure, local pricing, or community culture. Meanwhile, domestic alternatives such as GoZayaan and ShareTrip focus primarily on booking and ticketing rather than community-driven discovery and planning.

**LagaTour** was developed to fill this gap. It is a community-first travel platform where travelers can discover destinations, share stories, plan multi-leg trips, collaborate in groups, and receive AI-generated itineraries grounded in locally verified data — all within a single, cohesive web application.

The project follows core software engineering principles of modularity, separation of concerns, scalability, and security, making it suitable for real-world deployment.

---

## 4. Motivation

The primary motivation for LagaTour emerged from direct observation of how travel communities in Bangladesh operate. Information is fragmented across Facebook groups, YouTube videos, and personal blogs, with no reliable, searchable, community-verified record of travel plans, costs, or destination safety.

Several specific gaps motivated this project:

- **Fragmented Information:** No single platform aggregates community-verified itineraries, cost breakdowns, and safety ratings for Bangladeshi destinations.
- **Absence of Local AI Tools:** AI-powered travel planners that exist globally are not trained on or grounded in Bangladesh-specific destination data, transport options (bus, launch, train, jeep), or local pricing in BDT.
- **Lack of Gamified Engagement:** There is no platform that rewards travelers for contributing knowledge — sharing plans, rating places, or flagging unsafe destinations.
- **No Collaborative Planning Tools:** Travelers planning group trips lack a unified workspace for shared task management, expense splitting, and group communication.

LagaTour directly addresses each of these gaps through its ten core feature modules.

---

## 5. Objectives of the System

The primary objective of LagaTour is to design and develop a community-driven travel planning platform that empowers Bangladeshi travelers with intelligent tools, verified destination data, and collaborative features. The specific objectives are:

- To provide a social feed where travelers can share geotagged travel stories and media with AI content moderation.
- To enable the creation, sharing, and discovery of detailed multi-leg travel itineraries with itemized cost breakdowns.
- To offer an AI-powered dual-engine itinerary generator grounded in locally registered tourist destination data.
- To maintain an interactive map explorer with community-reported safety alerts and place ratings.
- To support collaborative group expedition planning with shared task management and expense splitting.
- To implement a gamification system that rewards community contribution through league tiers and traveler score points.
- To provide real-time private messaging between community members via WebSockets.
- To enforce role-based access control for regular users and administrators, with content moderation capabilities.

---

## 6. System Overview

LagaTour is a role-based web application supporting two primary user classes:

- **Traveler (User):** Community members who discover destinations, share travel content, plan itineraries, and engage with the platform's social and gamification features.
- **Administrator:** Privileged system managers responsible for content moderation, user management, and platform oversight.

The system follows a client-server architecture where a React-based Single Page Application (SPA) communicates with a Node.js/Express.js REST API backend over HTTP. Real-time features such as messaging are handled via Socket.io WebSocket connections on the same server. Persistent data — including users, posts, places, tour plans, groups, chats, and rankings — is stored in a relational MySQL database (`lagatour_db`). The Google Gemini API provides AI-driven itinerary generation, while Firebase is used for user authentication support and media hosting.

### System Architecture Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                     Client (Browser)                        │
│          React 19 + Vite + TailwindCSS + DaisyUI            │
│                                                             │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐   │
│  │ Social   │  │ AI       │  │ Map /    │  │ Group    │   │
│  │ Feed     │  │ Builder  │  │ Places   │  │ Planner  │   │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘   │
│       │             │             │              │          │
│       └─────────────┴──────┬──────┴──────────────┘          │
│                            │  REST API + WebSocket           │
└────────────────────────────┼────────────────────────────────┘
                             │
          ┌──────────────────▼──────────────────┐
          │         Node.js + Express.js         │
          │         Backend API Server           │
          │                                      │
          │  ┌──────────┐  ┌──────────────────┐  │
          │  │ REST API │  │ Socket.io Server  │  │
          │  │ Routes   │  │ (Real-Time)       │  │
          │  └─────┬────┘  └────────┬──────────┘  │
          │        │                │              │
          │  ┌─────▼────────────────▼──────────┐  │
          │  │       Service Layer              │  │
          │  │ aiService / socketService /      │  │
          │  │ imageVerificationService /       │  │
          │  │ emailService / leagueHelper      │  │
          │  └─────┬────────────────────────────┘  │
          └────────┼──────────────────────────────-┘
                   │
     ┌─────────────┼──────────────────┐
     │             │                  │
┌────▼────┐  ┌─────▼─────┐  ┌────────▼──────┐
│  MySQL  │  │  Google   │  │   Firebase    │
│ lagatour│  │ Gemini API│  │  (Auth + CDN) │
│   _db   │  │ (AI Gen.) │  │               │
└─────────┘  └───────────┘  └───────────────┘
```

---

## 7. Feature Description

This section describes the core functional modules of the LagaTour platform.

### 7.1 Social Travel Feed

The Social Travel Feed (`/`) is the primary discovery surface of the platform, analogous to a travel-focused social media newsfeed.

**Core Capabilities:**
- Travelers can publish travel stories with captions, geotagged locations, and media (photos/videos).
- All uploaded media is subject to AI-based geometry and geotag verification before publication to maintain authenticity.
- Published posts support community engagement through upvotes, downvotes, saves, and inline comments.
- A global notification banner system surfaces administrative alerts to all users.

**AI Media Verification Flow:**
```
Upload Media → AI Geometry Check → Geotag Validation → Approved / Flagged → Admin Review (if flagged) → Publish
```

---

### 7.2 Tour Plans & Itinerary Builder

The Tour Plans module (`/plans`) allows travelers to create, share, and browse detailed multi-leg travel itineraries.

**Core Capabilities:**
- **Multi-Leg Circuit Routes:** Each plan consists of an ordered list of stops specifying origin and destination, transport mode (Bus, Aeroplane, Train, Jeep, Launch), transport cost in BDT, hotel/accommodation name and cost, and per-stop miscellaneous expenses.
- **Auto-Budget Calculation:** Total trip budget is automatically summed across all legs and expense categories.
- **Route Flow Visualization:** Plan cards render visual step-by-step route timelines with transport badges and place costs.
- **Community Ratings:** Plans can be rated (1–5 stars) and liked by community members, feeding the Rankings module.

**Database Tables:** `tour_plans`, `tour_plan_places_modified`, `tour_plan_likes`

---

### 7.3 AI Tour Builder

The AI Tour Builder (`/ai-builder`) is the most technically sophisticated feature of the platform. It generates complete, multi-day travel packages using the Google Gemini API.

**Core Capabilities:**
- **Dual-Engine Suggestion Architecture:** For every generation request, the system simultaneously produces two independent travel packages:
  - **LagaTour DB-Grounded Package:** Itinerary grounded in MySQL-registered tourist spots, community safety scores, and GPS coordinates, using retrieval-augmented generation (RAG).
  - **Web Explorer & Culinary Trail Package:** Sourced from web travel blogs and culinary recommendations for a broader, internet-aware perspective.
- **Granular Time Slots:** Each day is broken into Morning (08:00 AM – 12:00 PM), Afternoon (01:00 PM – 05:00 PM), and Evening/Night (05:30 PM – 09:30 PM) slots with specific activities, spots, and local dining tips.
- **Direct Database Persistence:** A single-click "Create Tour Package" action saves the generated plan directly into the MySQL database (`tour_plans` and `tour_plan_places_modified` tables), making it immediately available on the Plans page.
- **Intelligent Fallback Engine:** If the primary Gemini API encounters a rate limit or failure, the system cascades through Gemini 3.5, Gemini 3.8, and finally a deterministic rule-based knowledge engine — ensuring zero generation failures.

**Input Parameters:** Starting city, destination, trip duration (days), total budget (BDT), travel style, preferred transportation mode.

**Popular Destinations Supported:** Cox's Bazar, Sajek Valley, Sreemangal, Saint Martin's Island, Bandarban, Sundarbans, Tanguar Haor, Kuakata, Sylhet, Rangamati.

---

### 7.4 Map Explorer & Places Directory

The Map Explorer (`/map`) and Places Directory (`/places`) provide spatial and categorical interfaces for destination discovery.

**Core Capabilities:**
- **Interactive Leaflet Map:** Renders tourist spots as markers on an interactive map with popups showing place name, safety rating, and safety report count.
- **Safety Alert Markers:** Locations with community-flagged safety concerns display prominent `⚠️ UNSAFE (X Reports)` warning banners on their map popups and in sidebar listings.
- **Place Directory Filters:** Destinations can be filtered by category (Beach, Hills, Nature, Island, Forest, Historic), by search query, and by safety status (Safe / Unsafe).
- **Community Contributions:** Users can add new tourist destinations through a modal form, contributing name, description, category, image, GPS coordinates, and curated exploration captions.
- **Rate & Review Modal:** A structured modal allows users to submit 1–5 star ratings, leave review comments, and toggle a "Mark as Unsafe" safety flag.

**Database Tables:** `places`, `place_images`, `place_ratings`, `myplaces`

---

### 7.5 Group Expedition Planner

The Group Expedition Planner (`/groups`) provides a collaborative workspace for travelers planning trips together.

**Core Capabilities:**
- **Interactive Task Checklist:** Group members can create, assign, and mark tasks as complete, enabling structured pre-trip preparation coordination.
- **Split-Expense Logger:** Shared group expenses are logged and automatically distributed per head, showing individual balances.
- **Group Chat Room:** Integrated real-time messaging for group members via Socket.io WebSockets.
- **Group Itinerary Timeline:** A shared, sequential activity timeline for the planned expedition.
- **Live Expedition Tracker:** Real-time status and progress tracking for active expeditions.

**Database Tables:** `group_expeditions`, `expedition_members`, `expedition_tasks`, `expedition_expenses`, `group_chats`

---

### 7.6 Community Leaderboards & Rankings

The Rankings page (`/rankings`) showcases the most active travelers and highest-rated tour plans across the platform.

**Core Capabilities:**
- **Top Travelers Leaderboard:**
  - Podium Showcase: The top three travelers are highlighted on Gold 🥇, Silver 🥈, and Bronze 🥉 podium cards with animated badges and profile links.
  - Full leaderboard table ranked by traveler score points, displaying league tier, trips shared, and cities visited. Includes name search and league category filters.
- **Top Tour Plans Leaderboard:**
  - Ranks community-submitted itineraries by highest community rating, most likes, or best budget value.
  - Displays multi-leg route previews, total budget, author profile, and quick-view links.

---

### 7.7 Gamification & Traveler Score System

LagaTour incorporates a gamification layer to encourage community participation and knowledge contribution.

**League Tier Progression:**

```
Explorer → Traveler → Adventurer → Expert → Legend
```

**Score Point Events:**

| Action | Points Awarded |
|---|---|
| Publish a Tour Plan | +15 pts |
| Rate & Review a Place | +5 pts |
| Share a Travel Story (Post) | +10 pts |
| Log Group Expenses | +3 pts |
| Follow a Traveler | +2 pts |
| Receive a Follow | +2 pts |

**Visual Rewards:** Milestone achievements trigger confetti animations (via `canvas-confetti`) and in-app level-up modal alerts.

---

### 7.8 Public User Profiles

Every traveler has a dedicated public profile page (`/profile/:userId`) accessible from any point in the platform.

**Core Capabilities:**
- **Profile Header:** Displays cover image, avatar, full name, username handle, current league tier badge, traveler score, bio, follower/following counts, and travel statistics.
- **Interactive Follow/Unfollow:** Real-time follower count updates with point rewards on follow actions.
- **Direct Messaging Shortcut:** One-click navigation to the private chat inbox with that traveler.
- **Authored Content Tabs:** Tabbed display of all Tour Plans and Travel Stories authored by the profile owner.
- **Global User Linking:** Clicking any user avatar or `@username` across the Social Feed, Tour Plans, Group Planner, Messaging, or Places pages routes to their profile.

---

### 7.9 Messaging & Inbox

The Messaging module (`/chats`) provides private, real-time communication between community members.

**Core Capabilities:**
- **Direct Chat Rooms:** Travelers can search the community and initiate private message conversations.
- **Real-Time Delivery:** Messages are delivered instantly via Socket.io WebSocket connections without page refresh.
- **Group Chat Support:** Group-specific chat rooms are created automatically when a Group Expedition is formed. Group chats can also be created independently (`/chats/create-group`).
- **Profile Integration:** User avatars and display names in chat headers link directly to public profiles.

---

### 7.10 Admin Panel

The Admin Panel (`/admin`) provides privileged system management tools accessible only to verified administrator accounts.

**Modules:**
- **Dashboard (`/admin`):** Overview statistics and platform health metrics.
- **User Management (`/admin/users`):** View, search, suspend, or delete user accounts. Review reported accounts.
- **Content Moderation (`/admin/posts`):** Review AI-flagged media, approve or reject posts, and manage report actions.
- **Admin Chat Portal (`/admin/chats`):** Monitor platform communication channels.

**Access Control:** Administrator status is determined by a compound check on `user_id`, account role field, email prefix, or username — with the root admin account seeded directly in the database schema.

---

### 7.11 Dynamic Theme System

LagaTour supports a dynamic Light and Dark (Sunset) theme system.

- **Light Mode:** High-contrast color palette with strong legibility across buttons, badges, cards, and navigation.
- **Dark (Sunset) Mode:** A warm, sunset-toned dark palette optimized for extended use and low-light environments.
- Theme state is persisted in local storage and applied globally through DaisyUI's theming system.

---

## 8. Technology Stack

### 8.1 Architecture Overview

LagaTour follows a decoupled, full-stack client-server architecture:

- **Frontend:** React 19 Single Page Application (SPA) served by Vite 8.
- **Backend:** Node.js + Express.js REST API with Socket.io for real-time WebSocket support.
- **Database:** MySQL (`lagatour_db`) accessed via a custom `db.js` query abstraction layer.
- **AI Layer:** Google Gemini API with server-side RAG integration using registered place data.
- **Auth:** Firebase Authentication (Google OAuth) and custom JWT-based credential authentication.
- **Testing:** Selenium WebDriver (Python) with pytest for automated UI test coverage.

---

### 8.2 Frontend Technologies

| Technology | Version | Purpose |
|---|---|---|
| React | 19.2.8 | Component-based UI framework |
| React Router DOM | 7.18.2 | Client-side SPA routing |
| Vite | 8.2.0 | Frontend build tool and dev server |
| TailwindCSS | 3.4.19 | Utility-first CSS framework |
| DaisyUI | 4.12.24 | Tailwind component library and theming |
| Leaflet.js | 1.9.4 | Interactive map rendering |
| Socket.io Client | 4.8.3 | Real-time WebSocket client |
| Firebase SDK | 12.17.1 | Authentication and media hosting |
| Lucide React | 1.29.0 | Icon library |
| Canvas Confetti | 1.9.4 | Gamification visual effects |
| @xenova/transformers | 2.17.2 | Client-side AI model inference (moderation) |

**Frontend File Structure:**

```
src/
├── pages/          # Full-page route components (15 pages)
├── components/     # Reusable UI components
│   ├── expedition/ # Expedition-specific components
│   └── modals/     # Modal dialog components (12 modals)
├── context/        # React Context providers
│   ├── AuthContext.jsx
│   ├── PostContext.jsx
│   └── ExpeditionContext.jsx
├── services/       # API and socket client services
├── data/           # Static mock/seed data
├── firebase/       # Firebase configuration
└── utils/          # Utility helpers (image compression, moderation, league)
```

---

### 8.3 Backend Technologies

| Technology | Version | Purpose |
|---|---|---|
| Node.js | LTS | Server runtime |
| Express.js | Latest | REST API framework |
| Socket.io | 4.x | WebSocket server for real-time messaging |
| MySQL2 | Latest | MySQL database driver |
| JSON Web Tokens (JWT) | Latest | Stateless authentication |
| bcrypt | Latest | Password hashing |
| Nodemailer | Latest | Email verification service |
| dotenv | Latest | Environment variable management |
| cors | Latest | Cross-Origin Resource Sharing |
| multer | Latest | File/image upload handling |

**Backend File Structure:**

```
server/src/
├── config/
│   └── db.js               # MySQL connection pool and query abstraction
├── controllers/            # Request handler logic (10 controllers)
│   ├── authController.js
│   ├── aiController.js
│   ├── postController.js
│   ├── placeController.js
│   ├── tourPlanController.js
│   ├── userController.js
│   ├── chatController.js
│   ├── groupController.js
│   ├── rankingController.js
│   └── adminController.js
├── routes/                 # Express route definitions (10 route files)
├── services/               # Business logic layer
│   ├── aiService.js        # Gemini API integration + RAG + fallback engine
│   ├── socketService.js    # Socket.io event handlers
│   ├── imageVerificationService.js
│   └── emailService.js
├── utils/
│   └── leagueHelper.js     # Gamification point calculation logic
└── index.js                # Server entry point
```

**API Route Summary:**

| Route Prefix | Controller | Responsibility |
|---|---|---|
| `/api/auth` | authController | Registration, login, JWT issuance, OTP verification |
| `/api/users` | userController | Profile management, follow/unfollow |
| `/api/posts` | postController | Social feed CRUD, likes, comments |
| `/api/places` | placeController | Places directory, ratings, safety flags |
| `/api/tour-plans` | tourPlanController | Itinerary CRUD |
| `/api/groups` | groupController | Expedition management, tasks, expenses |
| `/api/chats` | chatController | Direct messaging |
| `/api/rankings` | rankingController | Leaderboard queries |
| `/api/ai` | aiController | Gemini AI generation endpoint |
| `/api/admin` | adminController | Administrative management |

---

### 8.4 Database Architecture

LagaTour uses **MySQL 8.0** (`lagatour_db`) as its primary relational database with `utf8mb4` character encoding for full Unicode and emoji support.

**Key Tables:**

| Table | Description |
|---|---|
| `users` | Core user accounts with league points, follower counts, and travel stats |
| `divisions` / `districts` | All 8 divisions and 64 districts of Bangladesh |
| `places` | Tourist destinations with GPS coordinates, safety ratings, and report counts |
| `place_images` | Images associated with places |
| `place_ratings` | Community star ratings and reviews per user per place |
| `posts` | Social feed posts with engagement counts |
| `post_media` | Media attachments with AI verification status |
| `post_comments` | Threaded comments on posts and places |
| `tour_plans` | Multi-leg travel itineraries |
| `tour_plan_places_modified` | Sequenced stops for each tour plan |
| `group_expeditions` | Group trip workspaces |
| `expedition_members` | Group membership records |
| `chats` / `messages` | Direct messaging records |
| `email_verifications` | OTP codes for signup and password recovery |

**Referential Integrity:** All foreign key relationships are enforced at the database level with `ON DELETE CASCADE` and `ON UPDATE CASCADE` constraints to maintain data consistency.

**Entity-Relationship Overview:**

```
users ──< posts ──< post_media
      ──< places ──< place_ratings
      ──< tour_plans ──< tour_plan_places_modified
      ──< group_expeditions ──< expedition_members
      ──< chats ──< messages
```

---

### 8.5 AI Integration

The AI Tour Builder leverages the **Google Gemini API** through a multi-layered service architecture implemented in `server/src/services/aiService.js`.

**RAG Pipeline (LagaTour DB-Grounded):**

```
User Input → Query MySQL for Destination's Registered Places
           → Inject Places (names, coordinates, safety ratings) into Gemini Prompt
           → Generate Day-by-Day Itinerary Grounded in Local Data
           → Return Structured JSON Response
```

**Fallback Cascade:**

```
Gemini 3.5 Pro → (on failure) → Gemini 3.8 → (on failure) → Rule-Based Heuristic Engine
```

The deterministic fallback engine splits the user's budget realistically across transportation (28%), accommodation (38%), food (22%), and activities (12%), generating a structurally valid itinerary based on Bangladesh travel heuristics — ensuring users always receive a useful result.

---

### 8.6 Real-Time Communication

Real-time features are powered by **Socket.io** on the server side and the **Socket.io Client** on the frontend, both operating over the same HTTP server instance used by Express.

- Direct messages are delivered to recipients instantly via named socket rooms per conversation.
- Group expedition chat events (join, message, leave) are managed in group-specific socket rooms.
- Online presence and typing indicators are planned for future enhancement.

---

### 8.7 Authentication & Security

Security is enforced at multiple layers:

- **JWT-Based Authentication:** Stateless token-based authentication for all protected API endpoints.
- **bcrypt Password Hashing:** User passwords are hashed using bcrypt before storage; plaintext passwords are never persisted.
- **Email OTP Verification:** Account registration requires OTP verification via email (`emailService.js`).
- **Role-Based Access Control:** Admin routes are protected server-side; admin UI is gated client-side by compound role checks.
- **AI Content Moderation:** Post media passes through `imageVerificationService.js` before publication.
- **HTTPS Enforcement:** Recommended for production deployment; environment variables are managed via `.env` files with `.env.example` for safe onboarding.

---

### 8.8 Testing Infrastructure

Automated UI testing is implemented using **Selenium WebDriver** with **Python pytest**, providing end-to-end browser-level test coverage.

**Test Suite:**

| Test File | Coverage Area |
|---|---|
| `test_auth_and_navigation.py` | Login, registration, route protection |
| `test_social_feed_ui.py` | Feed rendering, post creation flow |
| `test_tour_plans_ui.py` | Plan creation, display, and routing |
| `test_ai_builder_ui.py` | AI Builder form submission and result rendering |
| `test_map_explorer_ui.py` | Map rendering and place marker interaction |
| `test_places_ui.py` | Places directory, rating modal, safety flags |
| `test_user_profile_ui.py` | Profile display and follow interaction |
| `test_rankings_ui.py` | Leaderboard tabs and podium rendering |
| `test_messaging_ui.py` | Chat inbox and message composition |
| `test_group_planner_ui.py` | Group creation, task, and expense flows |
| `test_admin_panel_ui.py` | Admin dashboard access and management |
| `test_deep_auth_workflow.py` | Deep authentication edge cases |
| `test_deep_ai_builder_submit.py` | Full AI generation submission and persistence |
| `test_deep_expedition_form_submit.py` | Complete expedition creation workflow |
| `test_ai_package_generation_and_expedition_sync.py` | AI-to-expedition synchronization |
| `test_create_post_page_ui.py` | Post creation page UI and form behavior |

Test configuration is defined in `pytest.ini` with shared browser setup in `tests/conftest.py`.

---

## 9. System Testing and Validation

System testing was conducted across all major functional modules using both manual exploratory testing and automated Selenium-based UI tests. The following categories of testing were performed:

- **Authentication Testing:** User registration with OTP email verification, login with JWT issuance, role-based routing, and session persistence were validated.
- **Feature Integration Testing:** Each feature module was tested end-to-end — from UI form submission through API call to database persistence and UI state update.
- **AI Generation Testing:** The AI Tour Builder was tested across multiple destinations, budget ranges, and duration inputs. Fallback engine behavior was verified by simulating API failures.
- **Real-Time Communication Testing:** WebSocket connections for direct messaging and group chat were validated for message delivery, ordering, and room isolation.
- **Safety Reporting Testing:** Place safety flagging, unsafe marker rendering on the map, and admin reporting actions were tested through the complete workflow.
- **Gamification Testing:** Score point awards, league tier progression, confetti triggers, and leaderboard position updates were verified across the relevant user actions.
- **Admin Panel Testing:** Role access enforcement, user suspension, content moderation approval/rejection, and admin-only route protection were validated.

These activities ensured consistent, reliable behavior across all system components and user roles.

---

## 10. Challenges

The development of LagaTour presented several technical and practical challenges:

- **AI Grounding Accuracy:** Constructing prompts that reliably produce well-structured, RAG-grounded itineraries — while staying within Gemini API token limits and maintaining output format consistency — required significant prompt engineering iteration.
- **Gemini API Rate Limits:** The free-tier Gemini API rate limits occasionally interrupted AI generation during development. Building the multi-level fallback cascade (Section 8.5) was essential to ensuring a reliable user experience.
- **Real-Time WebSocket Integration:** Managing Socket.io rooms for both direct and group chats, handling disconnections gracefully, and ensuring message ordering under concurrent connections required careful architectural decisions.
- **Image Handling at Scale:** Storing and serving large image files (profile pictures, post media, place images) as base64 encoded strings in a MySQL `LONGTEXT` column introduced performance considerations. A migration to object storage is planned.
- **Frontend State Synchronization:** Coordinating shared state across the three React Contexts (`AuthContext`, `PostContext`, `ExpeditionContext`) and ensuring UI consistency after API mutations required careful context design.
- **Selenium Test Flakiness:** Dynamic React component rendering introduced timing challenges for Selenium tests. Explicit wait strategies and robust selector targeting were employed to improve test stability.

---

## 11. Future Enhancements

LagaTour's modular architecture provides a strong foundation for continued development. Planned future enhancements include:

- **Mobile Application:** Development of a React Native companion application to extend accessibility to mobile users.
- **Object Storage Migration:** Migration of image assets from MySQL `LONGTEXT` storage to a dedicated object storage solution (AWS S3 or Firebase Storage) for improved performance and scalability.
- **Advanced AI Features:** Integration of live travel blog scraping and real-time web search grounding into the AI Builder's Web Explorer package, providing up-to-date recommendations.
- **Collaborative Trip Planning:** A shared, multi-user itinerary editing workspace similar to a collaborative document, allowing group members to co-build a tour plan in real time.
- **Real-Time Presence & Typing Indicators:** Enhancement of the messaging system with online presence indicators and typing status.
- **Push Notifications:** Browser-based push notifications for new messages, follower events, and plan ratings.
- **Verified Traveler Badges:** A verification system recognizing highly active and trusted community contributors.
- **Multi-Language Support:** Bangla language interface for wider accessibility across the traveler community.
- **Partner Integrations:** API integrations with domestic booking services (GoZayaan, ShareTrip) for in-platform ticket and accommodation booking.

---

## 12. Conclusion

LagaTour successfully demonstrates the practical application of modern full-stack software engineering principles to a genuine and locally meaningful problem: the fragmentation of travel planning resources for Bangladeshi travelers.

The platform integrates a rich feature set — community social feed with AI content moderation, multi-leg itinerary builder, dual-engine AI tour package generator with database-grounded RAG, interactive safety-aware map explorer, gamified community rankings, real-time messaging, group expedition planning, and a comprehensive admin panel — into a cohesive, responsive, and maintainable web application.

Built on React 19, Node.js, Express.js, MySQL, and the Google Gemini API, and validated through a suite of sixteen Selenium-based automated UI tests, LagaTour demonstrates the ability to design, build, test, and document a production-quality software system.

The project's modular architecture ensures that the planned enhancements — mobile application, object storage, real-time collaboration, and partner booking integrations — can be progressively adopted without requiring architectural restructuring. LagaTour is positioned to become a foundational platform for the Bangladeshi travel community.

---

## 13. References

1. Sommerville, Ian. (2016). *Software Engineering, 10th Edition*. Pearson Education.
2. Pressman, Roger S. & Maxim, Bruce R. (2020). *System Analysis and Design: A Practitioner's Approach, 9th Edition*. McGraw-Hill Education.
3. Node.js Documentation. Available at: https://nodejs.org/en/docs/ [Accessed: October 2026]
4. React.js Official Documentation. Available at: https://react.dev/ [Accessed: October 2026]
5. MySQL Reference Manual. Available at: https://dev.mysql.com/doc/ [Accessed: October 2026]
6. Express.js Official Documentation. Available at: https://expressjs.com/ [Accessed: October 2026]
7. TailwindCSS Documentation. Available at: https://tailwindcss.com/docs [Accessed: October 2026]
8. DaisyUI Documentation. Available at: https://daisyui.com/ [Accessed: October 2026]
9. Leaflet.js Documentation. Available at: https://leafletjs.com/ [Accessed: October 2026]
10. Socket.io Documentation. Available at: https://socket.io/docs/ [Accessed: October 2026]
11. Google Gemini API Documentation. Available at: https://ai.google.dev/docs [Accessed: October 2026]
12. Firebase Documentation. Available at: https://firebase.google.com/docs [Accessed: October 2026]
13. Vite Official Documentation. Available at: https://vitejs.dev/ [Accessed: October 2026]
14. Selenium with Python Documentation. Available at: https://selenium-python.readthedocs.io/ [Accessed: October 2026]
15. pytest Documentation. Available at: https://docs.pytest.org/ [Accessed: October 2026]
16. GoZayaan Official Website. Available at: https://www.gozayaan.com/ [Accessed: October 2026]
17. ShareTrip Official Website. Available at: https://www.sharetrip.net/ [Accessed: October 2026]
18. Agile Alliance. (2021). *Agile Software Development: Principles and Practices*. Available at: https://www.agilealliance.org/
19. LagaTour Feature Documentation. `features.txt`. [Internal Project Documentation, September 2026]
20. LagaTour Database Schema. `lagatour_db.sql`. [Internal Project Documentation, September 2026]
