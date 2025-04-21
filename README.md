# 🎬 Movie Recommendation System
A content-based movie recommendation system that suggests similar movies based on metadata such as genre, cast, director, overview, and keywords. Built using Python, Pandas, Scikit-learn, and Natural Language Processing (NLP) techniques.

# Features
    
    1. Combines metadata from movies.csv and credits.csv to enrich movie details.
    
    2. Handles data preprocessing: missing values, duplicates, and nested JSON fields.
    
    3. Creates a consolidated tags field using important features (overview, genres, cast, director, keywords).
    
    4. Applies NLP techniques (stemming, lowercasing, stopword removal) for text normalization.
    
    5. Implements Bag of Words (BoW) using CountVectorizer with a feature limit of 5000.
    
    6. Calculates cosine similarity between movie vectors to find and rank similar movies.

# How It Works
    1. Data Preprocessing
        -Merge movies.csv and credits.csv using the movie ID.
        -Extract relevant fields using custom functions (ast.literal_eval for JSON-like strings).
        -Drop unnecessary or null data and clean the datasets.

    2. Feature Engineering
        -Combine features such as genres, cast, director, keywords, and -overview into a single tags column.
        -Normalize text (lowercasing, stemming) using PorterStemmer.

    3. Vectorization & Similarity
        -Use CountVectorizer to convert text into vectors (max_features=5000, stop_words='english').
        -Calculate pairwise cosine similarity between all movie vectors.

    4. Recommendation Function
        -Input a movie title and get the top 5 similar movies based on content similarity.

# Technologies Used
    1. Python
    2. Pandas & NumPy
    3. Scikit-learn
    4. NLP (nltk, PorterStemmer)
    5. CountVectorizer (BoW Model)
    6. Cosine Similarity

# Example
    recommend("The Dark Knight")

    Output:
    1. Batman Begins  
    2. The Dark Knight Rises  
    3. Batman v Superman: Dawn of Justice  
    4. Man of Steel  
    5. Justice League

# Dataset
    1. movies.csv: Contains basic movie information (id, title, genres, overview, etc.)

    2. credits.csv: Includes cast and crew details for each movie.
    Datasets sourced from The Movie Database (TMDB).

# Future Improvements
    
    1. Replace CountVectorizer with TF-IDF for better feature weighting.
    
    2. Explore Word Embeddings (Word2Vec, BERT) for richer semantic similarity.
    
    3. Add user-based or collaborative filtering to enhance personalization.
    
    4. Build a web interface using Flask or Streamlit for real-time recommendations.
