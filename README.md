# ✈️ TripMate AI — A Multi-Agent Travel Planner with LangGraph

An open-source AI travel planner that turns a natural-language trip request into a practical travel plan with flight suggestions, hotel ideas, and a day-by-day itinerary. The project uses a multi-agent workflow built with LangGraph, LangChain, FastAPI, and Google Gemini.

🚀 **Live Demo:** https://multi-agent-travel-planner-9c2t.onrender.com

---

## Why this project?

Planning a trip usually means jumping between multiple websites, tools, and spreadsheets. This project brings that flow into one experience by combining:

- Flight Search Agent
- Hotel Research Agent
- Itinerary Planning Agent
- Final Response Agent

All coordinated through a LangGraph workflow to generate a complete travel plan from a single user query.

---

## Features

- ✈️ Flight research using AviationStack API
- 🏨 Hotel suggestions using Tavily Search API
- 🧠 Multi-agent orchestration with LangGraph
- 📝 AI-generated travel itinerary using Google Gemini 2.5 Flash Lite
- 🌐 FastAPI backend with an interactive web interface
- 💾 Conversation state persistence using PostgreSQL
- ⚡ Fast and efficient responses powered by Google Gemini

---

## Live Demo

🌐 **Application:** https://multi-agent-travel-planner-9c2t.onrender.com

Health Check:

```text
https://multi-agent-travel-planner-9c2t.onrender.com/health
```

---

## Tech Stack

- Python 3.10+
- FastAPI
- Jinja2
- HTML
- CSS
- JavaScript
- LangGraph
- LangChain
- Google Gemini 2.5 Flash Lite
- PostgreSQL
- Tavily API
- AviationStack API

---

## Project Structure

```text
.
├── app.py                # FastAPI application
├── backend.py            # LangGraph workflow
├── requirements.txt
├── templates/
├── static/
└── tools/
```

---

## Prerequisites

Before running locally, ensure you have:

- Python 3.10+
- PostgreSQL
- Google Gemini API Key
- Tavily API Key
- AviationStack API Key

---

## Environment Variables

Create a `.env` file:

```env
DATABASE_URL=postgresql://user:password@localhost:5432/travel_db
GOOGLE_API_KEY=your_google_api_key
AVIATIONSTACK_API_KEY=your_aviationstack_api_key
TAVILY_API_KEY=your_tavily_api_key
DEFAULT_ORIGIN_IATA=DAC
```

---

## Installation

```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS/Linux
source .venv/bin/activate

pip install -r requirements.txt
```

---

## Running the Application

```bash
python app.py
```

Open your browser:

```text
http://127.0.0.1:8000/
```

---

## API Endpoints

### Health Check

```http
GET /health
```

### Travel Planner

```http
POST /api/travel
```

Example:

```bash
curl -X POST http://127.0.0.1:8000/api/travel \
-H "Content-Type: application/json" \
-d '{"message":"Plan a 3-day trip to Tokyo with a budget of $1200"}'
```

---

## How It Works

1. User submits a travel request.
2. Flight Agent retrieves flight information using AviationStack.
3. Hotel Agent finds accommodation suggestions using Tavily.
4. Itinerary Agent creates a detailed travel itinerary using Google Gemini.
5. Final Agent formats everything into a structured travel guide.

---

## Contributing

Contributions are welcome!

1. Fork the repository.
2. Create a new feature branch.
3. Commit your changes.
4. Push the branch.
5. Open a Pull Request.

---

## Acknowledgments

This project demonstrates how to build a production-ready AI application using:

- LangGraph
- LangChain
- Google Gemini
- FastAPI
- PostgreSQL
- Tavily Search API
- AviationStack API

It serves as a practical example of orchestrating multiple AI agents with external APIs to automate real-world travel planning.