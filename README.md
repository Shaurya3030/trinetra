# tri.नेत्र

### AI · GIS · Blockchain — Land Intelligence Platform

*See the Land. Know the Truth.*

Built at **Code Apex — Hack the Upside Down 2025** by **Team BugSlayers**

---

## What is tri.नेत्र?

**tri.नेत्र (Trinetra)** means *The Third Eye* in Sanskrit — a symbol of intelligence, vision, and the power to see hidden truths.

We built an AI-powered platform that **detects land disputes before they reach the courtroom** — using satellite imagery, GIS mapping, and blockchain.

> India's government portals show land records. **Trinetra tells you what those records mean.**

---

## The Problem We're Solving

| | | | |
|---|---|---|---|
| **67M** | **66%** | **20+ Yrs** | **₹2L Cr** |
| pending land dispute cases | of civil cases are land-related | avg time to resolve one dispute | locked in disputed land |

Existing systems like Bhulekh only **store** land records. No system today **analyzes** them. No early warning. No risk detection. By the time someone finds out there is a problem — they have lost money or landed in court.

---

## Our Solution

```
USER searches a Survey Number
        ↓
SYSTEM fetches land records + court data + satellite data
        ↓
AI ENGINE generates Land Risk Score  ──→  0 to 100%
        ↓
GIS MODULE maps boundaries  ──→  detects overlaps
        ↓
BLOCKCHAIN verifies ownership  ──→  tamper-proof cert
        ↓
DASHBOARD shows result + sends ALERT if high risk
```

### Real Output Example

```json
{
  "survey_no": "112",
  "village": "Pune Rural",
  "risk_score": 82,
  "risk_level": "HIGH",
  "reasons": [
    "Ownership changed 5 times in 3 years",
    "Boundary overlap with Survey No. 113 detected",
    "Civil court case registered in 2021",
    "Multiple heirs claiming inheritance"
  ],
  "fraud_flag": true,
  "blockchain_verified": true
}
```

---

## Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                     FRONTEND LAYER                           │
│            React.js  ·  Leaflet Maps  ·  Tailwind            │
└─────────────────────────┬────────────────────────────────────┘
                          │
┌─────────────────────────▼────────────────────────────────────┐
│                     BACKEND LAYER                            │
│              Node.js  ·  FastAPI  ·  PostgreSQL              │
└──────────┬──────────────┬────────────────┬───────────────────┘
           │              │                │
    ┌──────▼──────┐ ┌─────▼──────┐ ┌──────▼───────┐
    │  AI ENGINE  │ │    GIS     │ │  BLOCKCHAIN  │
    │ TensorFlow  │ │  Mapbox    │ │  Ethereum    │
    │   OpenCV    │ │  Leaflet   │ │  Solidity    │
    │ Scikit-learn│ │  PostGIS   │ │    IPFS      │
    └──────┬──────┘ └─────┬──────┘ └──────┬───────┘
           └──────────────┼────────────────┘
                          │
┌─────────────────────────▼────────────────────────────────────┐
│                      DATA LAYER                              │
│       Bhulekh APIs · Court Records · Satellite Imagery       │
└──────────────────────────────────────────────────────────────┘
```

---

## Tech Stack

| Layer | Technologies |
|---|---|
| **Frontend** | React.js, Next.js, Tailwind CSS, Leaflet.js, Mapbox GL |
| **Backend** | Node.js, Express, FastAPI (Python), REST APIs, Redis |
| **AI & ML** | Python 3.11, TensorFlow, PyTorch, OpenCV, Scikit-learn, NLP |
| **Database** | PostgreSQL, MongoDB, PostGIS, IPFS |
| **Blockchain** | Ethereum, Solidity, Hardhat, Web3.js |
| **GIS** | Mapbox GL, Leaflet.js, GeoJSON, Satellite Imagery APIs |
| **Security** | JWT, Role-based access, DigiLocker ready |

---

## Project Structure

```
trinetra/
├── frontend/                   # React + Next.js app
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   │   ├── index.jsx       # Search + home
│   │   │   ├── dashboard.jsx   # Govt dashboard
│   │   │   ├── land/[id].jsx   # Land risk report
│   │   │   └── citizen.jsx     # Citizen portal
│   │   └── utils/
│   └── package.json
│
├── backend/                    # Node.js REST API
│   ├── src/
│   │   ├── routes/
│   │   │   ├── land.js
│   │   │   ├── dispute.js
│   │   │   └── alerts.js
│   │   ├── models/
│   │   └── controllers/
│   └── package.json
│
├── ai-engine/                  # Python FastAPI service
│   ├── models/
│   │   ├── dispute_predictor.pkl
│   │   └── boundary_detector.h5
│   ├── routers/
│   │   ├── predict.py
│   │   ├── overlap.py
│   │   └── nlp.py
│   ├── data/
│   ├── notebooks/
│   └── requirements.txt
│
├── blockchain/                 # Hardhat + Solidity
│   ├── contracts/
│   │   └── LandRegistry.sol
│   ├── scripts/
│   │   └── deploy.js
│   ├── test/
│   └── hardhat.config.js
│
└── README.md
```

---

## Quick Start

### Prerequisites

```bash
node >= 18.0.0
python >= 3.11
postgresql >= 14
git
```

### 1. Clone

```bash
git clone https://github.com/team-bugslayers/trinetra.git
cd trinetra
```

### 2. Backend

```bash
cd backend
npm install
cp .env.example .env
npm run dev
# http://localhost:5000
```

### 3. AI Engine

```bash
cd ai-engine
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
# http://localhost:8000
```

### 4. Blockchain

```bash
cd blockchain
npm install
npx hardhat compile
npx hardhat node
npx hardhat run scripts/deploy.js --network localhost
```

### 5. Frontend

```bash
cd frontend
npm install
cp .env.example .env.local
npm run dev
# http://localhost:3000
```

---

## Environment Variables

**`backend/.env`**
```env
PORT=5000
DATABASE_URL=postgresql://user:password@localhost:5432/trinetra
MONGODB_URI=mongodb://localhost:27017/trinetra
JWT_SECRET=your_jwt_secret_here
AI_ENGINE_URL=http://localhost:8000
REDIS_URL=redis://localhost:6379
```

**`frontend/.env.local`**
```env
NEXT_PUBLIC_API_URL=http://localhost:5000
NEXT_PUBLIC_MAPBOX_TOKEN=your_mapbox_token_here
NEXT_PUBLIC_CONTRACT_ADDRESS=your_contract_address
```

**`ai-engine/.env`**
```env
MODEL_PATH=./models/dispute_predictor.pkl
DATABASE_URL=postgresql://user:password@localhost:5432/trinetra
```

---

## API Reference

### Land Records
```
GET    /api/land/:surveyNo           →  Land details + risk score
GET    /api/land/:surveyNo/history   →  Ownership history
POST   /api/land/register            →  Register new land
GET    /api/land/geojson             →  All parcels as GeoJSON
```

### AI Engine
```
POST   /predict                      →  Generate risk score
POST   /detect-overlap               →  Boundary conflict detection
POST   /nlp/analyze                  →  Court text extraction
```

### Blockchain
```
POST   /api/blockchain/register      →  Register on-chain
GET    /api/blockchain/:surveyNo     →  Get chain record
POST   /api/blockchain/transfer      →  Transfer ownership
GET    /api/blockchain/verify/:hash  →  Verify document
```

---

## Features

- Instant Land Search — any survey number
- AI Risk Score — 0 to 100% with detailed reasons
- GIS Boundary Map — satellite maps with conflict zones
- Blockchain Certificate — tamper-proof ownership proof
- Real-time Alerts — instant notification on suspicious activity
- Government Dashboard — district-wide dispute heatmap
- Citizen Portal — verify land before buying
- Mobile Responsive — works on all devices

---

## Team BugSlayers

| Name | Role |
|---|---|
| **[Member 1]** | · System Design |
| **[Member 2]** | AI & Computer Vision |
| **[Member 3]** | Backend & Database |
| **[Member 4]** | Blockchain & Security |

---

## Impact

| Metric | Number |
|---|---|
| Land parcels in India | 650 Million |
| Pending dispute cases | 67 Million |
| Potential savings | Rs 50,000 Crore over 5 years |
| GovTech market India 2027 | $4.2 Billion |

---

## Roadmap

- [x] AI dispute prediction model
- [x] GIS boundary conflict detection
- [x] Blockchain ownership registry
- [x] Government dashboard
- [x] Citizen portal
- [ ] State Bhulekh API integration
- [ ] Real-time satellite pipeline
- [ ] Mobile app — Android & iOS
- [ ] Aadhaar + DigiLocker integration
- [ ] Predictive AI — flag disputes 2 to 3 years early
- [ ] National land grid — all 650M parcels

---

## License

MIT License — see LICENSE for details.

---

**tri.नेत्र** — *See the Land. Know the Truth.*

Made with love by Team BugSlayers · Code Apex 2025
