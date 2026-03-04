# AI Research Assistant with Multi-Agent System

A powerful research assistant built with LangGraph and AI agents that can search websites, extract relevant content, and save results in PDF and JSON formats.

## Features

- **Multi-Agent Architecture**: Specialized agents for planning, searching, extraction, summarization, and saving
- **Flexible Web Scraping**: Search across multiple websites simultaneously
- **AI-Powered Content Extraction**: Uses LLMs to extract and summarize relevant information
- **Multiple Export Formats**: Save research results as JSON or PDF
- **Customizable**: Specify your own websites and search parameters

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

### Option 1: Python Script

Run the research assistant directly:

```python
from research_assistant import research

# Basic usage
result = research("What are the latest developments in quantum computing?")

# With custom websites
result = research(
    query="Impact of climate change on marine ecosystems",
    websites=[
        "https://www.nature.com",
        "https://www.sciencedirect.com",
        "https://oceanservice.noaa.gov"
    ]
)

print(f"Results saved to:")
print(f"JSON: {result['json_path']}")
print(f"PDF: {result['pdf_path']}")
```

### Option 2: Interactive Notebook

Open `expirement/main.ipynb` and run the cells to use the research assistant interactively.

## How It Works

The research assistant uses a multi-agent workflow:

1. **Planning Agent**: Analyzes your query and extracts key search terms
2. **Search Agent**: Searches specified websites for relevant content
3. **Extraction Agent**: Extracts text content from discovered URLs
4. **Summarization Agent**: Uses AI to summarize and synthesize findings
5. **Saving Agent**: Saves results to JSON and PDF files

## Output

All research outputs are saved in the `research_outputs/` directory:
- **JSON files**: Structured data with all extracted content, URLs, and metadata
- **PDF files**: Formatted research reports with summaries and source citations

## Customization

You can customize:
- **Websites to search**: Pass a list of URLs to the `websites` parameter
- **Number of results**: Modify `max_results` in the search functions
- **Content length**: Adjust the character limits in extraction functions
- **Output format**: Modify the PDF and JSON generation functions

## Architecture

```
User Query → Planning Agent → Search Agent → Extraction Agent → Summarization Agent → Saving Agent → Results (PDF + JSON)
```

## Requirements

- Python 3.8+
- Google Gemini API key
- Internet connection for web scraping

## Notes

- Be respectful of website terms of service and robots.txt
- Some websites may block automated requests
- The quality of results depends on the accessibility of the websites
- Consider using a dedicated web search API (like Tavily) for better results

## License
MIT License

# 🚀 Quick Start Guide - AI Research Assistant

## Step 1: Install Dependencies

Open your terminal and navigate to the project directory, then run:

```bash
pip install -r requirements.txt
```

This will install all necessary packages:
- langchain & langgraph (AI agent framework)
- google-genai (Google Gemini LLM)
- beautifulsoup4 & requests (web scraping)
- fpdf (PDF generation)
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

## Step 3: Run Your First Research

### Option A: Using the Example Script

Run the example usage script:

```bash
python example_usage.py
```

This will run several research examples and show you how the system works.

### Option B: Write Your Own Script

Create a new Python file:

```python
from research_assistant import research

# Run a research query
result = research("Your research question here")

# Access the results
print(f"JSON saved to: {result['json_path']}")
print(f"PDF saved to: {result['pdf_path']}")
print(f"Summary: {result['summary']}")
```

### Option C: Interactive Mode

Run Python interactively:

```python
python
>>> from research_assistant import research
>>> result = research("What is machine learning?")
```

## Step 4: Customize (Optional)

### Specify Custom Websites

```python
result = research(
    query="Your research question",
    websites=[
        "https://www.nature.com",
        "https://en.wikipedia.org",
        "https://www.sciencedirect.com"
    ]
)
```

### Modify Configuration

Edit `config.py` to change:
- LLM settings (model, temperature)
- Search parameters (max URLs, timeout)
- Default websites
- Output formats

## Step 5: View Results

All outputs are saved in the `research_outputs/` directory:

- **JSON files**: Contains all extracted data, URLs, and metadata
- **PDF files**: Formatted research report with summary and sources

## Common Research Topics

Try these example queries:

```python
# Technology
research("What are the latest developments in artificial intelligence?")

# Science
research("How does CRISPR gene editing work?")

# Health
research("What are the health benefits of intermittent fasting?")

# Environment
research("What is the impact of deforestation on climate change?")

# History
research("What caused the fall of the Roman Empire?")
```

## Troubleshooting

### Issue: "No module named 'langgraph'"
**Solution**: Run `pip install -r requirements.txt`

### Issue: "API key not found"
**Solution**: Make sure you created a `.env` file with your `GEMINI_API_KEY`

### Issue: "Connection timeout"
**Solution**: Some websites may block automated requests. Try different websites or increase timeout in `config.py`

### Issue: "No content extracted"
**Solution**: Some websites have complex structures. The system will skip problematic pages and continue with others.

## Tips for Best Results

1. **Be Specific**: More specific queries yield better results
   - ❌ "AI"
   - ✅ "How do transformer models work in natural language processing?"

2. **Choose Relevant Websites**: Select websites that are likely to have the information
   ```python
   # For medical research
   websites=["https://pubmed.ncbi.nlm.nih.gov", "https://www.mayoclinic.org"]
   
   # For technology news
   websites=["https://techcrunch.com", "https://arstechnica.com"]
   ```

3. **Review and Refine**: The AI summary may need human verification. Always review the sources.

4. **Respect Rate Limits**: Don't make too many requests in quick succession

## Next Steps

- Explore the full codebase in `research_assistant.py`
- Modify agent prompts to customize behavior
- Add new export formats (Word, HTML, etc.)
- Integrate with other tools (databases, email, etc.)
- Build a web interface using Streamlit or Gradio

## Need Help?

Check the main README.md for more detailed documentation and architecture information.

Happy researching! 🔬📚
