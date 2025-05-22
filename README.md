# AI-Powered News Aggregator with Insight Generation

## How to Use

### Step 1: Clone the Repository
Download the `.ipynb` files:
- `model1.ipynb`
- `model2.ipynb`

### Step 2: Install Dependencies
In the terminal type:
pip install -r requirements.txt

## Step 3: Set Up API Keys

### Google News API:
1. Create an API key from [newsapi.org](https://newsapi.org)
2. Paste your key in the script where `google_news_api` is defined

### Google Generative AI (PaLM 2 / Gemini 1.5 Flash):
1. Set up API access from [Google AI Studio](https://ai.google.dev/)
2. Insert your API key in the `google_genai_api` variable

## Step 4: Run the Notebook
Execute the notebooks using Jupyter Notebook in VS Code or any compatible environment.

---

# System Architecture & Design (Model 2)

## 1. Data Source – Google News API
- Fetches real-time news data across various topics
- Extracts news metadata including:
  - Titles
  - URLs
  - Publication dates

## 2. URL Extraction & DataFrame Creation
- Collects article URLs from API data
- Stores metadata in a structured Pandas DataFrame

## 3. Article Extraction
- Downloads and parses content for each URL

## 4. Handling Website Variability
**Challenge:** Diverse website structures and protections hinder consistent scraping  
**Solution:** Implemented `newspaper3k` library with:
- Robust article extraction
- Fallback mechanisms for errors (e.g., 403 Forbidden)

## 5. Insight & Summary Generation
- Uses Hugging Face's `t5-small` model to generate:
  - Key takeaways
  - Concise summaries
- Optimized for real-time performance

## 6. Category Classification
- Zero-shot classification using Hugging Face models
- Predefined categories:
  ```python
  ['World', 'Politics', 'Business', 'Finance', 'Technology',
   'Science', 'Health', 'Sports', 'Entertainment', 'Crime', ...]
