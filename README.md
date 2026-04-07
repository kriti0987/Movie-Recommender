# Movie-Recommender

An  Intelligent Content-Based Movie Recommendation Engine built using the TMDB 5000 Movie Dataset. The project explores the evolution of natural language processing (NLP) techniques, moving from a simple frequency-based model to a sophisticated weighted TF-IDF pipeline to provide highly relevant movie suggestions.

# The Problem: The Noise Challenge
In the initial stages of development, using a standard Bag-of-Words (CountVectorizer) approach led to "noisy" and logically inconsistent recommendations.

Example: Searching for Avatar (Sci-Fi) would occasionally suggest A Cinderella Story (Teen Romance) simply because they shared common, low-value words in their descriptions.

#The Goal: To engineer a system that prioritizes Genre and Thematic Consistency over random keyword overlap.

# Tech Stack
1. Language: Python
2. Libraries: Pandas, NumPy, Scikit-Learn, NLTK
3. Algorithm: Cosine Similarity

# Installation & Usage
1. Install dependencies: pip install pandas scikit-learn nltk.
2. Run the Jupyter Notebook or Python script.
3. Use the recommend('Movie Name') function to get started!
