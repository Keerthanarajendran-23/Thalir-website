# THALIR Health (தளிர்) 🌱
### AI-Powered Child Health Screening & Referral Companion

> **Tamil Name:** தளிர்  
> **Tagline:** *“Every little life deserves a healthy start.”*  
> **Tamil Tagline:** *“ஒவ்வொரு குழந்தைக்கும் ஆரோக்கியமான தொடக்கம்.”*  
> **Target Audience:** Frontline Community Health Workers (ASHAs, Anganwadi Workers, Village Health Nurses) & Rural Caregivers.

---

## 1. Overview & Brand Meaning

**“தளிர்” (Thalir)** in Tamil signifies a tender green shoot or sprout. It represents childhood, delicate growth, hope, and the vital community responsibility to nurture every newborn and young child.

In underserved and rural communities, children often face barriers to early health assessments due to remote geography, limited medical personnel, transportation challenges, and intermittent internet connectivity. **THALIR Health** addresses this by providing a lightweight, offline-first, multilingual clinical screening companion designed for low-resource environments.

> ⚠️ **Responsible AI Disclaimer:**  
> THALIR Health is an assistive screening support system based on verified WHO IMCI and Indian National Health protocols. It **does NOT** diagnose clinical diseases, prescribe pharmaceutical treatments, or replace qualified medical practitioners. In any acute emergency, the system instructs immediate transfer to the nearest Primary Health Centre (PHC) or Hospital.

---

## 2. Core Capabilities & Architectural Pillars

### 🌐 1. Multilingual Native (English + தமிழ்)
- Complete dual-language interface across all forms, guides, clinical decision rationale, and doctor referral sheets.
- High-contrast, field-ergonomic UI with clear typography (`Noto Sans Tamil` + `Inter`).

### ⚖️ 2. WHO Anthropometry & Growth Engine (0–60 Months)
- Instant calculation of **Weight-for-Age**, **Height-for-Age**, and **Weight-for-Height** Z-scores.
- Automatic classification of **Severe Acute Malnutrition (SAM)**, **Moderate Acute Malnutrition (MAM)**, Stunting, and Underweight.
- **MUAC (Mid-Upper Arm Circumference)** color-band indicator:
  - 🔴 **Red (< 11.5 cm):** Severe Acute Malnutrition (Immediate referral)
  - 🟡 **Yellow (11.5 – 12.5 cm):** Moderate Acute Malnutrition (Targeted supplementary feeding)
  - 🟢 **Green (> 12.5 cm):** Normal nutrition status
- Bilateral pedal pitting edema check (diagnostic sign of Kwashiorkor).

### ⏱️ 3. Interactive Respiratory Rate Tap-Timer (WHO IMCI)
- Built-in tap-to-count timer allowing frontline workers to tap the screen with each chest rise/fall.
- Automatic breaths-per-minute (BPM) calculation with age-specific tachypnea alerts:
  - Under 2 months: $\ge 60$ breaths/min
  - 2 to 11 months: $\ge 50$ breaths/min
  - 12 to 59 months: $\ge 40$ breaths/min

### 🧠 4. Explainable AI Clinical Decision Support (CDSS)
- Rule-based, transparent triage tiers:
  - **EMERGENCY (Red):** Critical danger signs (inability to feed, intractable vomiting, convulsions, lethargy, stridor, severe dehydration).
  - **CAUTION (Yellow):** Fast breathing without chest indrawing, persistent diarrhea, MAM, prolonged fever, or missed milestones.
  - **HEALTHY (Green):** Optimal growth velocity, age-appropriate developmental progression, and routine care reinforcement.
- Every assessment provides an explicit **chain of reasoning** citing official WHO IMCI, POSHAN Abhiyaan, and IAP guideline sources.

### 📄 5. Digital Referral Slip & High-Density Offline QR Code
- Generates a clinical referral slip formatted for Primary Health Centre Medical Officers.
- Encodes full clinical findings into an offline-scannable QR code that any smartphone or hospital EMR system can read without network access.
- Print-friendly layout (`window.print()`).

### 🥣 6. Culturally Rooted Local Nutrition Hub
- Tamil Nadu and South Asian localized recipes:
  - **Sathu Maavu Kanji** (Sprouted multi-grain nutrient porridge)
  - **Murungai Keerai Broth** (Moringa / Drumstick leaf iron-rich soup)
  - **Ragi Porridge** (High calcium finger millet)
  - **Boiled Egg Mash** & seasonal local fruit purees (Papaya / Guava)
  - Feeding directives during illness (ORS, tender coconut water, small frequent meals).

### 🔊 7. Voice Assistant for Rural Accessibility
- Integrated Web Speech API audio synthesis to read aloud danger signs, care plans, and recipes in Tamil (`ta-IN`) and English (`en-IN`) for low-literacy caregivers.

### 💾 8. Offline-First Resilience & Sync Hub
- Full local data persistence via `localStorage` / client registry.
- Simulation toggle to switch between **Online** and **Offline (Field)** modes.
- Export all screening records to standard **CSV** and **JSON** formats.

---

## 3. Demonstration Case Scenarios

THALIR Health includes three realistic clinical scenarios for instant evaluation:
1. **Priya (பிரியா) – 8 Months (Caution / Yellow Alert):**
   - Tachypneic respiratory rate (56 bpm > 50 bpm threshold), mild acute undernutrition (MUAC 12.0 cm).
2. **Kavin (கவின்) – 18 Months (Healthy / Green Routine):**
   - Optimal growth curves, active milestones, timely alert for 18-month DPT booster.
3. **Anitha (அனிதா) – 24 Months (Emergency / Red Alert):**
   - Acute diarrhea, sunken eyes, delayed skin turgor pinch, bilateral pedal edema, MUAC 11.2 cm.

---

## 4. Tech Stack

- **Framework:** React 18 with TypeScript
- **Bundler:** Vite 6
- **Styling:** Tailwind CSS with typography and print media queries
- **Icons:** Lucide React
- **QR Code Engine:** `qrcode` library
- **Voice Synthesis:** Web Speech API (`SpeechSynthesisUtterance`)
- **State & Storage:** React Context + LocalStorage Offline Persistence

---

## 5. Getting Started

### Prerequisites
- Node.js (v18 or higher)
- npm (v9 or higher)

### Installation
```bash
# Clone the repository
git clone https://github.com/your-username/thalir-health.git
cd thalir-health

# Install dependencies
npm install

# Start development server
npm run dev
```

### Production Build & Preview
```bash
# Build production bundle
npm run build

# Preview production build locally
npm run preview
```

The application will be served at `http://localhost:3000/`.

---

## 6. License
MIT License. Dedicated to the health, dignity, and flourishing of every child.
