# FreightOS — Dispatch Intelligence Platform

A full-stack freight dispatch management platform inspired by Optimal Dynamics.
Features driver assignment & matching, load management, route optimization, and analytics.

## 🚀 Quick Start

### 1. Backend (Python Flask)

```bash
cd backend
pip install -r requirements.txt
python app.py
```

The API runs at **http://localhost:5000**

### 2. Frontend

Open `frontend/landing.html` in your browser for the landing page.
Open `frontend/app.html` for the full dispatch dashboard.

> The dashboard works standalone with mock data even without the backend running.
> Connect the backend to enable full CRUD operations.

---

## 📁 Project Structure

```
freight-platform/
├── backend/
│   ├── app.py              # Flask REST API + SQLite
│   └── requirements.txt
└── frontend/
    ├── landing.html         # Marketing landing page
    └── app.html             # Full dispatch dashboard (React)
```

---

## 🔌 API Endpoints

### Drivers
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/drivers` | List all drivers |
| GET | `/api/drivers?status=available` | Filter by status |
| GET | `/api/drivers/:id` | Get single driver |
| POST | `/api/drivers` | Create driver |
| PUT | `/api/drivers/:id` | Update driver |

### Loads
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/loads` | List all loads |
| GET | `/api/loads?status=available` | Filter by status |
| POST | `/api/loads` | Create load |
| PUT | `/api/loads/:id` | Update load |

### Dispatch & Matching
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/assignments` | List all assignments |
| POST | `/api/assignments` | Assign driver to load |
| POST | `/api/match` | Get optimal driver matches for a load |

### Routes
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/routes` | List all routes |
| POST | `/api/routes/optimize` | Re-optimize a route |

### Analytics
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/analytics` | Full analytics summary + trends |

---

## 🎛️ Dashboard Features

### 📊 Analytics
- Live KPI cards: utilization, active loads, on-time rate, miles
- 14-day revenue trend chart
- Driver utilization breakdown by type (OTR / Regional / Solo)

### 🚛 Dispatch
- Browse available loads on the left
- Click a load → AI-powered driver matching scores appear on the right
- Select one or more drivers → click "Assign to Driver"
- Match types: SOURCE LOAD, 4 LOAD TOUR, 1HR TO SOURCE, SOURCE TOUR

### 📦 Loads
- Full load table with filtering by status
- Search by load number, origin, or destination
- Add new loads with the form

### 👤 Drivers
- Card grid view of all drivers
- Color-coded status (available / on load / off duty)
- Add new drivers with the form

### 🗺️ Routes
- View active routes with miles, hours, fuel & toll estimates
- Click "Optimize Route" to run route optimization
- Visual route bar with waypoints

---

## 🏗️ Next Steps (Production Roadmap)

- [ ] Add JWT authentication
- [ ] Integrate real TMS (McLeod, TMW, Aljex)
- [ ] Connect Google Maps API for real routing
- [ ] Add real-time WebSocket updates
- [ ] Build mobile driver app
- [ ] Add ML-based match scoring model
- [ ] Deploy to AWS/GCP with Docker

---

## 🛠️ Tech Stack

| Layer | Tech |
|-------|------|
| Backend | Python · Flask · SQLite |
| Frontend | React 18 · Recharts |
| Styling | Pure CSS custom properties |
| Fonts | Syne · JetBrains Mono · DM Sans |
