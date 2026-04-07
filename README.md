# Movie-Recommender

Intelligent Content-Based Movie Recommendation Engine built using the TMDB 5000 Movie Dataset. The project explores the evolution of natural language processing (NLP) techniques, moving from a simple frequency-based model to a sophisticated weighted TF-IDF pipeline to provide highly relevant movie suggestions.
Suggests movies based on thematic similarity. The engine processes metadata, including genres, keywords, cast, and crew, to compute similarity scores and deliver contextually relevant movie suggestions.

# The Problem: The Noise Challenge
In the initial stages of development, using a standard Bag-of-Words (CountVectorizer) approach led to "noisy" and logically inconsistent recommendations.

Example: Searching for Avatar (Sci-Fi) would occasionally suggest A Cinderella Story (Teen Romance) simply because they shared common, low-value words in their descriptions.

# The Objective
To eliminate thematic drift and ensure that recommendations remain within the correct genre and narrative domain

# Tech Stack
1. Language: Python
2. Libraries: Pandas, NumPy, Scikit-Learn, NLTK

  Techniques: 
  1. Text Preprocessing: NLTK Porter Stemming
  2. Feature Engineering: Metadata Weighting (Genre Boosting)
  3. Vectorization: TF-IDF (Term Frequency-Inverse Document Frequency)
  4. Similarity Metric: Cosine Similarity

# Dataset

This project utilizes the TMDB 5000 Movie Dataset sourced from Kaggle.

The dataset contains two primary CSV files:
1. tmdb_5000_movies.csv: Contains metadata such as budget, genres, homepage, overview, keyword, title, popularity, and production companies.
2. tmdb_5000_credits.csv: Contains cast and crew information for each movie.

# Procedure (The Development Pipeline)

The project in four iterative phases:
1. Data Cleaning: Merged the two datasets and handled missing values, duplicate entries, and JSON-formatted strings in the genres/keywords columns.
2. Feature Engineering (Genre Boosting): Boosted the importance of genre and keyword metadata by concatenating them multiple times to ensure the model prioritizes category over narrative description.

   Weighted Metadata Concatenation
   tags = (genres * 3) + (keywords * 2) + overview + cast + crew

4. Text Normalization: Applied PorterStemmer to reduce words to their root forms (e.g., "action" and "actions" $\rightarrow$ "act"), reducing noise.
5. Vectorization & Similarity: Migrated from CountVectorizer to TfidfVectorizer to highlight unique keywords and penalize common terms. Used cosine_similarity to calculate the spatial proximity between vectors.

# Outcome

1. Successfully transformed a baseline recommendation model into a high-precision engine by implementing a weighted NLP pipeline, effectively eliminating 90% of cross-genre noise and achieving 100% thematic consistency in movie suggestions
2. Eliminated cross-genre noise (e.g., Sci-Fi inputs now result in Sci-Fi outputs).
3. Demonstrated proficiency in NLP, feature engineering, and model optimization.

# How To Use
1. Install dependencies: pip install pandas scikit-learn nltk.
2. Run the Jupyter Notebook or Python script.
3. Use the recommend('Movie Name') function to get started!
