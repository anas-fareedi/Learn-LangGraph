# AI Research Assistant with Multi-Agent System

A powerful research assistant built with LangGraph and AI agents that can search websites, extract relevant content, and save results in PDF and JSON formats.

## Installation

1. Install required packages:
```bash
pip install -r requirements.txt
```

2. Create a `.env` file in the project root with your API key:
```
GEMINI_API_KEY=your_api_key_here
```

## Usage

### Option 1: Interactive Notebook

Open `expirement/main.ipynb` and run the cells to use the research assistant interactively.

## Requirements

- Python 3.8+
- Google Gemini API key
- Internet connection for web scraping

# 🚀 Quick Start Guide - AI Research Assistant

## Step 1: Install Dependencies

Open your terminal and navigate to the project directory, then run:

```bash
pip install -r requirements.txt
```

This will install all necessary packages:
- langchain & langgraph (AI agent framework)
- google-genai (Google Gemini LLM)
- python-dotenv (environment variables)

## Step 2: Set Up API Key

1. Get a Google Gemini API key from: https://makersuite.google.com/app/apikey

2. Copy the `.env.example` file to `.env`:
   ```bash
   cp .env.example .env
   ```

3. Edit `.env` and add your API key:
   ```
   GEMINI_API_KEY=your_actual_api_key_here
   ```


# History
research("What caused the fall of the Roman Empire?")

## Need Help?

Check the main README.md for more detailed documentation and architecture information.

Happy researching! 🔬📚


# APP - Modular Research Assistant

This folder contains the modular implementation of the AI Research Assistant with proper separation of concerns.
## 🚀 Usage

### Run the test suite
```bash
cd APP
python test_app.py
```

### Run example queries
```bash
cd APP
python example_usage.py
```

### Run main application
```bash
cd APP
python main.py
```

### Custom websites
```python
result = research(
    query="Your question",
    websites=[
        "https://en.wikipedia.org",
        "https://www.nature.com"
    ]
)
```

## 📦 Dependencies

All dependencies are in the main `requirements.txt`:
- langchain & langgraph
- langchain_google_genai
- beautifulsoup4
- requests
- fpdf
- python-dotenv

## 🔐 Environment Variables

Create a `.env` file in the project root:
```
GEMINI_API_KEY=your_api_key_here
```
