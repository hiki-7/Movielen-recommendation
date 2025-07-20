# BERT-based Movie Recommendation System 

This project is a personalized movie recommender system built upon the [MovieLens 1M dataset](https://grouplens.org/datasets/movielens/1m/). It is inspired by and based on [YJiangcm's project](https://github.com/YJiangcm/Movielens1M-movie-recommendation-syste), with several modifications including the integration of movie **year** into the movie representation.

---

##  Data Description

The original dataset consists of:

- `ratings.dat`: user ratings of movies
- `movies.dat`: movie ID, title, and genres
- `users.dat`: demographic info of users

##  Modification

We extended the original preprocessing by:

Extracting movie release year from the title string

Incorporating the year as a new feature into the movie embedding

This addition provides temporal context, helping the model better understand user preferences across time periods.

##  Netural Network

We implemented a deep learning model that learns joint embeddings for users and movies.

Input:

User features: ID, gender, age, occupation

Movie features: ID, genres, title, release year

Embedding Layers: Each categorical feature is embedded into a fixed-size dense vector

Architecture: The embeddings are concatenated and passed through fully connected layers to predict the user’s rating

Loss Function: Mean Squared Error (MSE) is used to train the model

##  Recommend system

After training, we extract the learned user and movie embeddings to enable two types of recommendations:

Movie-to-Movie Recommendations
Compute cosine similarity between movie embeddings to find movies similar in genre, style, or content.

User-to-Movie Recommendations
Match each user’s embedding with all movie embeddings to suggest personalized movie recommendations.


