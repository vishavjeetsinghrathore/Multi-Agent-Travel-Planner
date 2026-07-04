# ✈️ TripMate AI — A Multi-Agent Travel Planner with LangGraph

An open-source AI travel planner that turns a natural-language trip request into a practical travel plan with flight suggestions, hotel ideas, and a day-by-day itinerary. The project uses a multi-agent workflow built with LangGraph, LangChain, FastAPI, and Google Gemini.

## Why this project?

Planning a trip usually means jumping between multiple websites, tools, and spreadsheets. This project brings that flow into one experience by combining:

- a flight-search agent,
- a hotel-research agent,
- an itinerary-planning agent, and
- a final response agent,

all coordinated through a LangGraph workflow.

## Features

- ✈️ Flight research using AviationStack API
- 🏨 Hotel suggestions using Tavily Search API
- 🧠 Multi-agent orchestration with LangGraph
- 📝 AI-generated travel itinerary using Google Gemini
- 🌐 FastAPI backend with a simple web interface
- 💾 Conversation state persistence using PostgreSQL
- ⚡ Fast and efficient responses powered by Google Gemini 2.5 Flash Lite

## Tech Stack

- Python 3.10+
- FastAPI
- Jinja2 + HTML/CSS/JavaScript
- LangGraph
- LangChain
- Google Gemini 2.5 Flash Lite
- PostgreSQL
- Tavily API
- AviationStack API

## Project Structure

```text
.
├── app.py                # FastAPI app entry point
├── backend.py            # LangGraph travel workflow
├── requirements.txt      # Python dependencies
├── static/               # Static frontend assets
├── templates/            # HTML templates
└── tools/                # Flight and web search integrations
```

## Prerequisites

Before running the project locally, make sure you have:

- Python 3.10 or newer installed
- PostgreSQL running and accessible
- API keys for:
  - Google Gemini
  - Tavily
  - AviationStack

## Environment Variables

Create a `.env` file in the project root with the following variables:

```env
DATABASE_URL=postgresql://user:password@localhost:5432/travel_db
GOOGLE_API_KEY=your_google_api_key
AVIATIONSTACK_API_KEY=your_aviationstack_api_key
TAVILY_API_KEY=your_tavily_api_key
DEFAULT_ORIGIN_IATA=DAC
```

## Installation

```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS/Linux
source .venv/bin/activate

pip install -r requirements.txt
```

## Running the App

Start the FastAPI server:

```bash
python app.py
```

Then open your browser at:

```text
http://127.0.0.1:8000/
```

## API Endpoints

### Health Check

```http
GET /health
```

### Plan a Trip

```http
POST /api/travel
```

Example request:

```bash
curl -X POST http://127.0.0.1:8000/api/travel \
  -H "Content-Type: application/json" \
  -d '{"message":"Plan a 3-day trip to Tokyo with a budget of $1200"}'
```

## How the Workflow Works

1. The user submits a travel request.
2. The Flight Agent gathers flight information using AviationStack.
3. The Hotel Agent searches for accommodation suggestions using Tavily.
4. The Itinerary Agent generates a detailed travel plan using Google Gemini.
5. The Final Response Agent combines all results into a structured travel guide.

## Contributing

Contributions are welcome! If you'd like to improve the project:

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Open a Pull Request.

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