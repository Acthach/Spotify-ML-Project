

# Spotify Music Recommendation Model

## Overview

This project aims to build a personalized music recommendation system using data sourced from Spotify’s API. By examining track-level features, artist similarities, genre relationships, and user listening patterns, the system generates highly tailored recommendations that elevate the listener’s overall Spotify experience. Leveraging data mining and machine learning techniques, the project organizes music into meaningful structures, identifies influential artists and trends, and delivers precise song and artist recommendations aligned with individual tastes.

## Personal Goals & Key Questions

* **End-to-end model development:** From data collection and cleaning to feature engineering, modeling, evaluation, and generating a final curated playlist.
* **User segmentation:** How can user listening behavior be grouped into distinct segments to enable personalized marketing and engagement strategies?
* **Cross-genre connectivity:** Which artists or songs serve as bridges between genres, subcultures, or listening communities?
* **Content-based recommendations:** How can audio features, embeddings, and metadata improve the accuracy and diversity of recommendations?


## Table of Contents
1. Data
2. EDA
3. Model Creation
4. Conclusion
   


### Data Mining
To continuously gather fresh tracks for the recommendation model, I implemented a backoff-and-retry mechanism for scraping Spotify public playlists. This system automatically pauses, retries, and recovers from API rate limits, ensuring reliable extraction of track features such as popularity, danceability, acousticness, energy, instrumentalness, liveness, loudness, speechiness, tempo, and time signature. I intentionally chose this approach over using a Kaggle dataset because my previous projects had already demonstrated my ability to build models from clean, pre-curated data; this time, I wanted to engage directly with the raw, messy data returned by the API to gain deeper experience in handling real-world data workflows.

### Exploratory Data Analysis (EDA)
Dataset Summary:

Songs: 170,653

Artists: 28,680

Genres: 2,973

Key Findings:
A significant increase in song loudness over the years, correlating with higher energy levels in music.
Identification of distinct trends and patterns in music characteristics across different time periods and genres.

### Model Creation
1. Logistic Regression (Baseline Model)

I began with a Logistic Regression model to establish a baseline for comparison. After training on the feature set, I evaluated performance using predicted labels and a confusion matrix to understand the model’s strengths and weaknesses.
This baseline helped determine whether more complex models were necessary.

2. Decision Tree Classifier + GridSearchCV

To experiment with nonlinear modeling, I implemented a Decision Tree Classifier and optimized it using a GridSearchCV pipeline.
The grid search tuned hyperparameters such as:max_depth (tree complexity)
This allowed the model to adapt to the structure of the Spotify feature data while helping avoid overfitting.

3. Random Forest Classifier + GridSearchCV

Building on the Decision Tree experiments, I trained a Random Forest Classifier, again using GridSearchCV for hyperparameter tuning.
Parameters explored included:max_depth n_estimators (number of trees)
The ensemble method improved stability and performance by reducing model variance and better capturing relationships between track features.

4. Scaled Decision Tree Pipeline

To incorporate feature scaling and ensure consistent preprocessing, I built a pipeline using:
StandardScaler DecisionTreeClassifier (max_depth=30) This pipeline standardized inputs before training, reducing feature imbalance and improving generalization on the test set.


### Conclusion
After evaluating multiple models, the Random Forest Classifier emerged as the most effective choice for this Spotify recommendation system. Unlike Logistic Regression—which struggled with the nonlinear nature of audio features—and standalone Decision Trees—which tended to overfit—Random Forest provided the best balance of accuracy, stability, and generalization. Its ensemble structure allowed it to capture complex relationships between track attributes such as energy, danceability, loudness, and acousticness, while remaining resilient to noise and variability in the raw Spotify data. Additionally, its built-in feature importance metrics offered valuable interpretability, helping reveal which musical characteristics contributed most to the model’s predictions. Overall, Random Forest delivered the most reliable performance and aligned best with the real-world complexity of music recommendation tasks.







