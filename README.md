# Capstone-Project
Game Recommender 

The plan for this project was to create a function that recommends games based on user input and similarity; a model that returns recommended games. The dataset I have chosen to work with is The Games of All Time Dataset which is data scraped from the website Metacritic and made available on Kaggle.

I attempted this using a couple of models, promising modelling techniques such as Content-Based Recommendation using NLP: TF-IDF - Cosine Similarity Metric, and Feature-Selected Recommendation using NLP: CountVectorizer - Cosine Similarity. 

The Content-Based Recommender uses NLP to extract features from the game descriptions and computes word vectors using TF-IDF to compute the similarity between them. I applied some feature engineering and cleaning to prep the description data using an NLP_Prep_data function. In this function I have performed Tokenization, removed punctuation and stopwords, and applied stemming and lemmatization to the text; the output is a new column called clean_description. I then construct the Tf IDF matrix and compute the cosine similarity scores in which this data is plugged into the recommender function which delivers results based on the user input game.


To further refine my model, I attempted a feature selection model approach which rather than just using the game description as my feature, I use other features which might be important, such as the developer, the platform, the genre, the type and age rating to see how the quality of the results compare with the TF IDF content-based test results. I created a function the joins all the required (cleaned) feature columns by a space and creates a new feature that I feed into the model vectorizer. The cosine similarity is computed based on the count matrix and ran through the recommender fuction again. Results can then be compared with the Content_Based results.
