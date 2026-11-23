# CubeVI

CubeVI is an interactive 3D visualizer and AI-powered solver for the 2×2×2 Pocket Cube. It pairs an optimal solver backend (IDA\* search accelerated by Pattern Databases) with an interactive Three.js / React 3D cube interface.

---

## Features

- **Interactive 3D Simulation**: Real-time 3D cube rendering powered by Three.js and React Three Fiber with orbit controls and smooth turn animations.
- **Color Palette & Sticker Painting**: Paint custom cube configurations directly onto the 3D cube with validation to ensure valid color counts.
- **Fast Optimal Solver**: Backend uses **IDA\* (Iterative Deepening A\*)** with precomputed **Pattern Databases (PDB)** to deliver optimal shortest-path solutions.
- **Step-by-Step Playback**: Step through, pause, or animate solutions at variable speeds (0.5× to 2×).
- **Random Scrambler**: One-click generation of valid random scrambles preventing redundant or canceling moves.

### 1. Backend Setup

```bash
cd backend

# Create and activate virtual environment (optional but recommended)
python -m venv venv
# Windows:
venv\Scripts\activate
# Linux/macOS:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run the FastAPI server (starts at http://localhost:8000)
uvicorn app.main:app --reload
```

---

### 2. Frontend Setup

In a separate terminal:

```bash
cd frontend

# Install dependencies
npm install

# Start Vite development server
npm run dev
```

Open your browser at the local URL shown by Vite (typically `http://localhost:5173`).

---

## 🧪 Running Tests

Run the backend test suite:

```bash
cd backend
python -m pytest
```

---

## 📁 Project Structure

```text
CubeVI/
├── backend/
│   ├── app/
│   │   ├── api/          # FastAPI routes & endpoints
│   │   ├── cube/         # Cube state representation, moves, scrambler, validator
│   │   └── solver/       # IDA* search algorithms & Pattern Database heuristics
│   ├── tests/            # Test suite for cube logic, solver, and API
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── components/   # UI components (Color palette, solution bar, controls)
│   │   ├── cube/         # Three.js 3D scene, cube geometry & face mappings
│   │   ├── api.js        # Backend communication layer
│   │   └── App.jsx       # Main application layout & state
│   ├── package.json
│   └── vite.config.js
└── README.md
```
