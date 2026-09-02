# 🧭 QuestRoam — Gamified AI Travel Companion (MVP)

> **"Explore the World. Complete the Quest."**
> Turn every journey into an epic adventure with location-based quests, AI trip intelligence, historical AR clue hunting, and safety tools.

---

## 🌟 Overview & Hackathon Brief

**QuestRoam** is a gamified, AI-powered travel application designed for students, solo travelers, and culture enthusiasts. Instead of passive sightseeing, travelers unlock interactive heritage quests, solve location-based history challenges, scan for simulated AR artifacts, and earn XP and badges.

### 📍 Primary Demo Scenario
- **Destination:** Delhi, India
- **Hero Monument:** Red Fort (*Lal Qila*)
- **Featured Quest:** *Red Fort: Hidden History Quest* (3 Challenges)
- **Gamification Rewards:** +100 XP + "History Explorer" Badge unlock
- **Starting State:** Level 3 Explorer (650 XP) ➔ Completed State: Level 3 Explorer (750 XP)

---

## 🚀 Key Features

### 1. 🏆 Interactive Heritage Quests & Trivia
- Location-based historical challenges for monuments like **Red Fort**, **India Gate**, and **Qutub Minar**.
- Instant feedback with historical explanations and hints.
- Anti-duplicate XP protection (no duplicate rewards for previously completed quests).
- Confetti celebration and badge unlock notifications.

### 2. ⚡ Gamified Progression & Badges
- Persistent `localStorage` tracking for User Level, XP Progress, Completed Quests, and Unlocked Badges.
- Dynamic Level Progress bar calculating required XP for the next level tier.
- Achievement gallery featuring badges:
  - 🏰 *History Explorer* (Commissioned Mughal fort conquest)
  - 🍽️ *Food Hunter* (Chandni Chowk foodie)
  - 🧭 *City Explorer* (Delhi capital discoverer)
  - 🔮 *AR Heritage Sleuth* (Clue hunter)
  - 🛡️ *Safe Wanderer* (Safety Sentinel equipped)

### 3. 🤖 QuestRoam AI (Gemini 3.7 Flash + Offline Fallback)
- Server-side AI integration using Express proxy (`/api/ai/chat`, `/api/ai/place-info`, `/api/ai/recommendations`).
- Keeps API keys secure on the backend.
- High-resilience fallback system with intelligent keyword matching if `GEMINI_API_KEY` is not provided.
- Web Speech API text-to-speech audio reader.
- User preference personalization (History, Street Food, Adventure, Culture, Budget).

### 4. 🔮 Simulated AR Viewfinder Experience (`ARExperience.tsx`)
- Camera-style HUD viewfinder with reticles and holographic POI pins.
- "Scan Location" simulation uncovering Mughal inscriptions at Lahori Gate and Diwan-i-Khas.
- Awards **+50 Exploration XP** and unlocks the *AR Heritage Sleuth* badge.

### 5. 🗺️ Interactive OpenStreetMap & GPS Beacon
- Leaflet map centered on Delhi heritage sites.
- Category filters (Quests, UNESCO World Heritage, All Sights).
- Drawer sidebar with direct buttons to launch quests, AR, or detailed historical guides.

### 6. 🛡️ 24/7 Traveler SOS Sentinel
- Emergency one-tap simulated dials (112 National Helpline, 1091 Women Safety).
- Fake Incoming Call generator for solo travelers needing a polite excuse to leave awkward situations.
- Simulated Live GPS Coordinate broadcast (`28.6562° N, 77.2410° E`).

### 7. 🍽️ Local Eats & Hidden Gems
- Curated stops in Old Delhi (Karim's, Gali Paranthe Wali, Chandni Chowk, Dilli Haat, Khan Market).

### 8. 🌐 Multi-Language Support
- Switch between **English**, **हिन्दी (Hindi)**, **Español (Spanish)**, and **Français (French)**.

---

## 🛠️ Tech Stack

- **Frontend:** React 19, TypeScript, Tailwind CSS, Lucide Icons, Canvas Confetti, Leaflet.
- **Backend:** Node.js, Express, TSX, `@google/genai` TypeScript SDK.
- **State & Persistence:** React Context API + LocalStorage.
- **AI Model:** `gemini-2.5-flash` via server-side API proxy.

---

## 💻 Local Setup & Execution Instructions

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn

### 1. Install Dependencies
```bash
npm install
```

### 2. Environment Configuration (Optional)
QuestRoam operates out-of-the-box with an offline fallback. To enable live Gemini AI:
1. Create a `.env` file from `.env.example`:
```bash
cp .env.example .env
```
2. Add your Gemini API key:
```env
GEMINI_API_KEY="your_actual_gemini_api_key"
PORT=3000
```

### 3. Run Application
```bash
npm run dev
```
Open your browser at `http://localhost:3000` to start exploring!

---

## 🧪 Testing the Complete Hackathon Flow

1. **Launch App:** Visit `http://localhost:3000`. Verify starting stats: Level 3, 650 XP.
2. **Start Quest:** Click **"Continue Quest"** on the hero banner (or navigate to *Quests* -> *Red Fort: Hidden History Quest*).
3. **Solve Challenges:**
   - Q1: *Which Mughal emperor commissioned the Red Fort?* ➔ Select **Shah Jahan**.
   - Q2: *Where is the Red Fort located?* ➔ Select **Delhi**.
   - Q3: *The Red Fort is mainly associated with which empire?* ➔ Select **Mughal Empire**.
4. **Claim Rewards:** See confetti explosion! You receive **+100 XP** (total becomes **750 XP**) and the **History Explorer Badge**.
5. **Simulate AR:** Click **"Simulate AR"** -> **"Scan Location"** to discover the secret Lahori Gate inscription and earn **+50 Exploration XP**.
6. **Ask AI Guide:** Go to **AI Guide** tab and ask *"What should I eat near Red Fort?"* or click suggestion chips.
7. **Verify Profile:** Open **Profile** tab to inspect unlocked badges, level progress, and test the **"Reset Demo State"** button.
