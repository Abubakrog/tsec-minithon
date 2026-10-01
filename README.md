# 🛡️ DigitalShield — Digital Footprint & Privacy Risk Auditor

> **“See your digital exposure. Fix what matters.”**  
> *A modern cybersecurity SaaS application that audits credential clustering, maps cascade risk relationships, and prioritized remediations for everyday users.*

---

## 🚀 Hackathon Quickstart (30 Seconds)

### Prerequisites
- Node.js (v18+)
- MongoDB (Optional — built with automatic in-memory fallback store so the demo works out-of-the-box!)

### Install & Run
```bash
# 1. Install all dependencies (root, backend, frontend)
npm run install-all

# 2. Run both Backend & Frontend concurrently with one command
npm run dev
```

- **Frontend Client**: `http://localhost:5173` (or `http://localhost:5174`)
- **Backend API**: `http://localhost:5001`
- **Health Check & DB Mode**: `http://localhost:5001/api/health`

---

## 🌟 Key Product Features

### 1. Dashboard (`/dashboard`)
- **Real-Time Privacy Risk Score**: 72/100 ("Needs Attention") rendered via an animated circular SVG gauge.
- **Exposure Stats**: 18 monitored accounts, 4 high-risk accounts, 27 connected services, 6 accounts missing 2FA.
- **Risk Vector Breakdown**: Critical Risks (2), High Risks (4), Reused Password Groups (3), Missing 2FA (6).
- **Top Vulnerable Accounts**: Gmail (Critical), Instagram (High), Dropbox (High), Spotify (Medium) with itemized risk factor badges.
- **Recommended Next Steps**: High-leverage fixes with point reduction estimates and 1-click remediation.

### 2. My Digital Footprint (`/footprint`)
- Complete inventory of monitored accounts across 8 categories: *Email, Social, Finance, Shopping, Productivity, Cloud Storage, Entertainment, Developer*.
- Search bar & filters for Risk Level, 2FA status, and service categories.
- Dual layout switch: Polished SaaS Data Table and Card Grid view.
- **Credential Privacy Safeguard**: Real passwords are never stored or displayed. Shared credentials only display abstract groups: `Password Group A — shared by 4 accounts`.

### 3. Account Detail & Audit (`/account/:id`)
- Itemized risk factor bars: Known Breach (+30), Password Reused (+20), Missing 2FA (+20), Excessive Permissions (+15), Recovery Dependency (+10), Network Exposure (up to +25).
- **Single Point of Failure Warning**: Alerts when an identity anchor can reset 7+ other accounts.
- Granular device permission toggles (Location, Contacts, Camera, Microphone, Photos).

### 4. Interactive Risk Graph — *Core Hackathon Feature* (`/risk-graph`)
- Built with **React Flow**: interactive zooming, panning, dragging, minimap, and auto-fit.
- Custom dark-theme cybersecurity nodes color-coded by threat level:
  - 🔴 **Critical (80–100)**: Glowing red border & pulsing halo
  - 🟠 **High (60–79)**: Orange alert outline
  - 🟡 **Medium (30–59)**: Yellow badge
  - 🟢 **Low (0–29)**: Green secured node
- Edge relationship types with visual badges:
  - `Recovery` (Password reset pathway)
  - `SSO` (OAuth Single Sign-On link)
  - `Shared Password` (Clustered credential reuse)
  - `Permission` (Cross-app authorization)
  - `Recovery Phone` (Shared SMS recovery mobile)
- Interactive slide-over audit drawer with cascade explanation, dependent services list, and quick fix modal.

### 5. Fix Checklist & Action Plan (`/fixes`)
- Prioritized remediation cards (#1 Enable 2FA on Google, #2 Change reused password, #3 Revoke Instagram location, etc.).
- Educational modal with step-by-step instructions.
- **Interactive Remediation**: Clicking "Mark as Fixed" dynamically reduces the overall risk score, drops account risk, updates the network graph, and triggers celebratory confetti feedback!

### 6. Simulated Breach Monitoring (`/breaches`)
- Realistic breach intelligence feed labeled with `[SIMULATED DEMO ALERT]` badges.
- Shows cascade impact: services compromised via credential stuffing from shared password groups.
- Actions to change password, audit connections, and mark alerts as reviewed.

### 7. Privacy Telemetry Dashboard (`/privacy`)
- Deep telemetry on data sharing: Location (8 apps), Contacts (5 apps), Camera (6 apps), Mic (3 apps), Photos (7 apps).
- Interactive **Recharts** visualizations:
  - Donut Chart: Risk Level Distribution
  - Bar Chart: Sensitive Device Permission Counts
  - Area Chart: Score Improvement Trajectory
- Before vs. After comparison card: Initial (84) → Active (72) → Potential (48).

### 8. Add Service Modal
- Modal with prominent warning: *"Never enter your actual password. DigitalShield only records whether passwords are reused."*
- Instantly recalculates network exposure scores upon addition.

---

## 🧠 Explainable Risk Scoring Engine

```
Base Risk = 0
+ 30 pts: Known data breach
+ 20 pts: Reused password group
+ 20 pts: 2FA disabled
+ 15 pts: Excessive permissions (3+ device privileges)
+ 10 pts: High recovery dependency (serves as reset anchor)
+ 10 pts: Inactive / dormant account (12+ months)
+ min(dependentAccounts * 5, 25): Network exposure score

Total Account Score = min(totalRisk, 100)
Tiers: 0-29 Low (Green) | 30-59 Medium (Yellow) | 60-79 High (Orange) | 80-100 Critical (Red)
```

---

## 🛠️ Tech Stack

- **Frontend**: React 18, Vite, Tailwind CSS, Lucide React, Recharts, React Flow (`@xyflow/react`), Canvas Confetti
- **Backend**: Node.js, Express, Mongoose, CORS, Dotenv
- **Database**: MongoDB (with automatic in-memory fallback store)
- **Architecture**: RESTful JSON APIs, component-driven UI

---

## ⏱️ 3-Minute Hackathon Demo Script for Judges

1. **Dashboard (0:00 - 0:45)**:
   - Introduce DigitalShield: *"Most people assume their risk is isolated to individual accounts, but hidden dependencies link them together."*
   - Point out the 72/100 risk score and the 4 critical stats.
2. **Risk Graph (0:45 - 1:45)**:
   - Navigate to `/risk-graph`.
   - Click on **Google** node. Show the Single Point of Failure callout: *"Google can reset 7 other accounts! An attacker compromising Google cascades to Dropbox, Instagram, Canva, and Spotify."*
   - Drag nodes, zoom in/out, and toggle the relationship filter to *Recovery* and *Shared Password*.
3. **Fix Checklist (1:45 - 2:30)**:
   - Navigate to `/fixes`.
   - Click "Fix" on **#1 Enable 2FA on Google (-18 pts)**.
   - Click **Mark as Fixed**: watch the confetti fire, the score drop from 72 to 54, and Google's risk level change.
4. **Footprint & Privacy Telemetry (2:30 - 3:00)**:
   - Show `/footprint` with password clustering safeguards (never showing real passwords).
   - Show `/privacy` with the Recharts distributions and the "Load Demo Data" button to reset.

---

## 🔒 Security & Privacy Notice
*This is an MVP prototype built strictly for college hackathon demonstration. It does not solicit, capture, or store real passwords, financial credentials, or live user identities.*
