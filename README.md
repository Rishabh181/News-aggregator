# News-aggregator
Problem Statement: 
AI-Powered News Aggregator with Insight Generation
How to Use
Step 1: Clone the Repository
Download the .ipynb files model1 and model2.
Step 2: Install Dependencies
pip install -r requirements.txt
Step 3: Set Up API Keys
•	Google News API:
Create a key from newsapi.org
Paste your key in the script where “google_news_api” is defined.
•	Google Generative AI (PaLM 2 / Gemini 1.5 Flash):
Set up API access from Google AI Studio
Insert your API key in the “google_genai_api” variable.
Step 4: Run the Notebook
•	Use Jupyter Notebook (in VS Code or any environment):

System Architecture & Design For Model 2
1. Data Source – Google News API
•	Used the Google News API to fetch real-time news data across topics.
•	Extracted news metadata such as titles, URLs, publication dates, etc.
2. URL Extraction & DataFrame Creation
•	Collected article URLs from the fetched API data.
•	Stored metadata and URLs in a structured Pandas DataFrame for further processing.
3. Article Extraction
•	For each URL, attempted to download and parse the article content.
4. Handling Website Variability
Problem: Different websites have varied structures and protection mechanisms that hinder uniform scraping.
Solution: Used the newspaper3k library for robust article extraction with fallback handling for failed downloads (e.g., 403 errors).
5. Insight & Summary Generation
•	Used the lightweight Hugging Face model t5-small to generate:
o	Key takeaways
o	Summaries
•	Optimized for real-time or near real-time response.
6. Category Classification
•	Applied zero-shot classification using Hugging Face models.
•	Predefined categories included:
['World', 'Politics', 'Business', 'Finance', 'Technology', 'Science', 'Health', 'Sports', 'Entertainment', 'Crime', ...]
7. Headline Generation
•	Utilized the model:
"JulesBelveze/t5-small-headline-generator"
to generate concise and compelling article headlines.
8. Final Output
•	Compiled all enriched data into a .csv file:
o	Original title
o	Cleaned article text
o	Extracted summary
o	Key insights
o	Category
o	AI-generated headline
o	Source URL
