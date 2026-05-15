# Driver-Pulse

# 🚗 Driver Pulse — Team ACE

> Real-time driver wellness & earnings intelligence platform for ride-hailing drivers.  
> Uses on-device sensor data (accelerometer, gyroscope, microphone) with ML models to detect stressful driving situations and forecast earnings velocity.

---

## 🎥 Demo Video
[Watch Demo](https://youtu.be/PL-XsfVfLA0?feature=shared)

## 🌐 Live Application
[Open Driver Pulse](https://driver-pulse-gamma.vercel.app/)

---

# 👨‍⚖️ Judge Login Credentials

```txt
Username: judge@uber.com
Password: hackathon2026
```

> ⚠️ Note for Judges:  
> The backend is hosted on Render and may take around **60 seconds** to wake up on the first request.

---

# ✨ Features

## 📊 Dashboard
- Daily trips overview
- Earnings tracking
- Driver stress score
- Real-time activity timeline

## 🛣️ Trip Detail
- Route playback with maps
- Sensor visualisation charts
- Event detection with explainability
- Confidence indicators

## 📈 Trends
- Weekly/monthly earnings analytics
- Stress trend visualisation
- Earnings velocity insights

## 🎯 Goals
- Set daily earning targets
- Track completion progress
- Performance monitoring

## 🤖 Predict (Judge Facing)
- Input sensor & earnings values
- Instant ML-powered prediction
- Real-time forecasting interface

## 📂 Batch Upload (Judge Facing)
- Upload CSV files
- Run inference on multiple trips
- Bulk stress & earnings analysis

## 🔍 Explainability
- Per-event feature contribution analysis
- Confidence badges
- Transparent ML insights

## 👍 Feedback System
- Thumbs up/down event feedback
- Improve detection quality

## 🔐 Authentication
- Login/Register support
- Demo accounts available

> 📌 To log multiple trips at once, go to the **Trips** tab and use **Import CSV**.

---

# 🏗️ Architecture

```bash
Driver-Pulse/
├── backend/                       # FastAPI REST API (25 endpoints)
│   ├── main.py                    # Routes, middleware, Pydantic models
│   ├── data/
│   │   ├── sample_data.py         # Synthetic trip/route/event generator
│   │   ├── batch_processor.py     # Loads ML models, runs batch inference
│   │   ├── trips_import.py        # CSV trip import parser
│   │   ├── users.py               # In-memory auth store
│   │   └── config.py              # Batch limits & constants
│   └── utils/
│       └── logging.py             # Structured logging
│
├── frontend/                      # React + Vite + Tailwind SPA
│   └── src/
│       ├── pages/                 # Main application pages
│       ├── components/            # Reusable UI components
│       ├── api/client.js          # Centralised API client
│       └── utils/sanityChecks.js  # Input validation helpers
│
├── drivepulse_stress_model/       # Stress Detection ML Pipeline
│   ├── run.py
│   ├── src/
│   │   ├── generate_data.py
│   │   ├── train.py
│   │   ├── inference.py
│   │   └── hal.py
│   ├── model/
│   └── calibration/
│
├── earnings/earnings/             # Earnings Forecasting ML Pipeline
│   ├── run.py
│   ├── src/
│   │   ├── build_dataset.py
│   │   ├── features.py
│   │   ├── augment.py
│   │   ├── train.py
│   │   └── inference.py
│   ├── model/
│   └── data/
│
├── streamlit_app.py               # Standalone Streamlit demo
├── tests/data/                    # Example CSVs
└── requirements.txt
```

---

# ⚙️ Setup & Installation

## 📋 Prerequisites

- Python 3.9+
- Node.js 18+
- Docker Desktop

---

# 🚀 Run Locally

## 1️⃣ Install Python Dependencies

```bash
pip install -r requirements.txt
```

## 2️⃣ Start Backend

```bash
cd backend
python main.py
```

Backend runs at:

```txt
http://localhost:8000
```

---

## 3️⃣ Start Frontend

```bash
cd frontend
npm install
npm run dev
```

Frontend runs at:

```txt
http://localhost:5173
```

---

# 🐳 Run with Docker

```bash
docker compose up --build
```

## Open Applications

| Service | URL |
|---|---|
| Frontend | http://localhost:5173 |
| Backend Health API | http://localhost:8000/api/health |

---

# 🔄 Data Flow

## 🚘 Trips & Goals
- Manual trip entry or CSV uploads
- `/api/trips`
- `/api/trips/import-csv`

These endpoints update:
- earnings
- hours
- forecasts
- dashboard metrics

---

## 🤖 Batch Stress & Earnings Prediction
CSV uploads are:
1. Processed by backend helpers
2. Features engineered
3. ML models invoked
4. Predictions returned as JSON

---

# 🧠 Machine Learning Pipelines

## 🚨 Stress Detection Model
- Random Forest Classifier
- Sensor-based event detection
- Rule-based fallback support
- Device calibration layer

### Inputs
- Accelerometer
- Gyroscope
- Microphone sensor features

### Outputs
- Stress events
- Confidence score
- Explainability insights

---

## 💰 Earnings Forecasting Model
- Random Forest Regressor
- 14 engineered features
- Rolling averages
- Rush-hour flags
- Earnings velocity prediction

---

# 🛠️ Tech Stack

| Layer | Technologies |
|---|---|
| Frontend | React 18, Vite, Tailwind CSS, Recharts, Leaflet |
| Backend | FastAPI, Uvicorn |
| ML | scikit-learn, NumPy, Pandas |
| Deployment | Vercel, Render, Docker |

---

# 📦 Scalability & Modularity

## Backend
- Modular FastAPI structure
- Easily replace in-memory storage
- Scalable ML service integration

## Frontend
- Centralized API layer
- Reusable components
- Feature-flag friendly architecture

## Batch Processing
- Stateless request handling
- Parallel backend scalability
- Load-balancer compatible

---

# 🧪 Testing & Validation

## Frontend Validation
- Money input validation
- Time range validation
- Goal target sanity checks

## Example Test Coverage
Located in:

```txt
frontend/src/__tests__/
```

Example tests:
- EarningsProgress.test.jsx
- TripsAddTrip.test.jsx

---

# 👥 Contributors

| Name | GitHub |
|---|---|
| Rishit Gupta | [@RishitGG](https://github.com/RishitGG) |
| Lavisha | [@lavishaa4](https://github.com/lavishaa4) |
| Merin Theres Jose | [@merintheres](https://github.com/merintheres) |
| Arjun Dubey | [@addev2906](https://github.com/addev2906) |

---

# 📊 GitHub Stats

- ⭐ Stars: 0
- 🍴 Forks: 1
- 🚀 Deployments: 58

---

# 🌟 Vision

Driver Pulse aims to improve:
- Driver wellness
- Driving safety
- Earnings optimisation
- Real-time operational intelligence

by combining:
- sensor analytics
- explainable AI
- forecasting systems
- scalable cloud infrastructure

---

# 📜 License

This project was built for a hackathon/demo purpose.

---

# ❤️ Team ACE

Building safer, smarter, and healthier driving experiences with AI.
