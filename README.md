## Introduction
The purpose of this project is to develop a content-based and matrix factorization music recommendation
system by leveraging song metadata and simulated user data. This system aims to identify and recommend
songs that share similar characteristics, enhancing the user’s experience through personalized suggestions.

## Methods/Results

#### Web-Scraper
Using Python, the audio_features.csv file from Kaggle was read in, the primary key being the ISRC codes.
The Selenium library was used to automate web browser interactions and for each ISRC code, a URL was
constructed to search for the rest of the song information on soundexchange.com. Once the page loaded,
the algorithm located the table elements containing the search results.

#### Content-Based Recommender
The content-based recommender leverages six audio features – danceability, energy, valence, tempo, acousticness, and liveness – to identify and recommend songs that share similar characteristics with a given input
song. Using the sigmoid kernel, a nonlinear similarity measure, the system calculates pairwise similarity
scores between the feature vectors of the input track and all other tracks in the merged dataset. The process
begins by standardizing the audio features using StandardScaler to ensure that all features contribute equally
to the similarity calculation.

#### Matrix Factorization Recommender
To improve our content based recommender system we opted to also include matrix factorization. The
matrix factorization recommender uses implicit feedback, primarily user play counts for these results, to
generate personalized song recommendations. Utilized an Alternating Least Squares model that decomposes
the user-item interaction matrix into latent factors. These factors represent the user preferences and the song
characteristics. The recommender can then identify user behavior patterns and predict songs based on their
listening history.
