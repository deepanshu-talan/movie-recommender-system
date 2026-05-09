# MovieRS — AI-Powered Movie Recommendation System

A full-stack movie recommendation web app built with **React**, **Flask**, and a **TF-IDF + Cosine Similarity** ML engine, powered by the **TMDB API**.

---

## Screenshots

### Homepage — Hero Section
![Homepage](docs/screenshots/homepage.png)

### Trending Movies
![Trending](docs/screenshots/trending.png)

### High Rated Cinema
![High Rated](docs/screenshots/high_rated.png)

### Search Results
![Search](docs/screenshots/search.png)

---

## Tech Stack

| Layer | Technology |
|-------|--------|
| **Frontend** | React 18, Tailwind CSS, React Router, Axios |
| **Backend** | Python, Flask, Gunicorn |
| **ML Engine** | Scikit-learn (TF-IDF + Cosine Similarity) |
| **Database** | SQLite with FTS5 full-text search |
| **Cache** | Redis |
| **Containerization** | Docker, Docker Compose |
| **Data Source** | TMDB API v3 |

---

## Getting Started

### Prerequisites

- Python 3.11+
- Node.js 18+
- A free [TMDB API key](https://www.themoviedb.org/settings/api)

### 1. Clone and configure

```bash
git clone https://github.com/deepanshu-talan/movie-recommender-system.git
cd movie-recommender-system
cp .env.example .env
# Add your TMDB_API_KEY to .env
```

### 2. Backend

```bash
python -m venv venv
source venv/bin/activate        # Windows: .\venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Build the ML model

```bash
python scripts/fetch_tmdb_data.py --count 500
python scripts/train_model.py
```

### 4. Run backend

```bash
python -m app.main
# API runs at http://localhost:5000
```

### 5. Run frontend

```bash
cd frontend
npm install
npm run dev
# App runs at http://localhost:5173
```

### Docker (optional)

```bash
cd docker
docker-compose up --build -d
# App runs at http://localhost
```

---

## Project Structure

```
├── app/                  # Flask backend
│   ├── api/routes/       # API endpoints
│   ├── db/               # SQLite + Redis layers
│   ├── ml/               # TF-IDF pipeline
│   └── services/         # Business logic
├── frontend/             # React (Vite) app
│   └── src/
│       ├── components/
│       ├── pages/
│       └── hooks/
├── scripts/              # Data fetching + model training
└── docs/screenshots/     # App screenshots
```

---

## What's Next

- **Collaborative filtering** — user-based recommendations alongside content-based
- **User accounts** — watchlist, ratings, and personalised history
- **Fuzzy search** — better typo tolerance and semantic search
- **Trailer integration** — embedded video playback on the detail page
- **Mobile-first redesign** — dedicated responsive layouts for smaller screens
