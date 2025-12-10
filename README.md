

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

### Conclusion








