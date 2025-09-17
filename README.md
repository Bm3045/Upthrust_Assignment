
# Upthrust_Assignment — Mini Workflow Automation with AI Agent

This project is a mini workflow automation app where users can enter a prompt, and the system generates a result by combining an AI response with data from a third-party API.

Supported actions:

🌦 Weather — via OpenWeatherMap API

💻 GitHub — fetch trending repositories

📰 News — via GNews API





## Tech Stack

**Backend:** Node.js, Express, Google Gemini API

**Frontend:** React (Vite), TailwindCSS

**APIs Used:**
  
Google Gemini (gemini-pro)

OpenWeatherMap (Weather data)

GitHub API (Trending repos)

GNews API (Top headlines)

## Setup Instructions

1. Clone the Repository 

```bash
git clone https://github.com/your-username/Upthrust_Assignment.git
cd Upthrust_Assignment

```

2. Backend Setup

```bash
cd backend
npm install
cp .env.example .env


```

Example .env

```bash
PORT=4000

# Gemini AI Studio
GEMINI_API_KEY=your_google_ai_studio_api_key

# Weather API (OpenWeatherMap)
OPENWEATHER_API_KEY=your_openweathermap_api_key

# GitHub Token (optional for higher rate limits)
GITHUB_TOKEN=your_github_pat

# GNews API
GNEWS_API_KEY=your_gnews_api_key

# Mock mode (use fake responses without real API calls)
MOCK=false



```

Run Backend

```bash
npm run start
# or (with auto-reload using nodemon)
npm run dev

```
Backend runs on:
👉 http://localhost:4000


3. Frontend Setup

```bash
cd frontend
npm install
cp .env.example .env

```

Example .env

```bash
VITE_BACKEND_URL=http://localhost:4000
```

Run Frontend

```bash
npm run dev
```

Frontend runs on:
👉 http://localhost:5173


## 🚀 Example Usage

Request (Weather)

```bash
POST /run-workflow
{
  "prompt": "Write a tweet about today’s weather in Mumbai",
  "action": "weather",
  "params": { "city": "Mumbai" }
}
```

Response

```bash
{
  "ai_response": "Rainy vibes, perfect for chai ☔",
  "api_response": "light rain in Mumbai, 27°C",
  "final_result": "Rainy vibes, perfect for chai ☔ light rain in Mumbai, 27°C #weather"
}

```
