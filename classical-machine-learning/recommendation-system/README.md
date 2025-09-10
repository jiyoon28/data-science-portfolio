# Recommendation System Project

This project builds a complete recommendation engine for article suggestions using multiple approaches: **Rank-Based Recommendations**, **User-User Collaborative Filtering**, **Content-Based Filtering**, and **Matrix Factorization (SVD)**.  
The goal is to explore and compare different recommendation techniques for users with no history, limited history, and rich interaction history.

---

## Getting Started

Follow these steps to run this project on your local machine.

### Dependencies

```bash
Python >= 3.8
pandas
numpy
matplotlib
seaborn
plotly
scikit-learn
```

### Testing

This project includes test functions to validate your implementation.

Break Down of Tests
sol_1_test()  # Verifies EDA outputs (unique users, articles, interactions)
sol_2_test()  # Confirms top article retrieval (by popularity)
sol_3_test()  # Validates user-user similarity results
sol_4_test()  # Checks recommendations for new/cold-start users
sol_5_test()  # Confirms matrix factorization reconstruction quality


Run all tests:

!pytest project_tests.py

If no errors appear, your implementation matches the expected solution.

### Project Instructions

This project is divided into the following key parts:

1. Exploratory Data Analysis (EDA)
- Handle missing values ("unknown_user" for null emails)
- Compute descriptive statistics (unique users, articles, interactions)
- Identify most-viewed articles

2. Rank-Based Recommendations
- Recommend top-n most popular articles
- Simple yet effective for new users (cold start)

3. User-User Collaborative Filtering
- Build a user-item interaction matrix
- Compute cosine similarity between users
- Recommend unseen articles from similar users

4. Content-Based Recommendations
- Vectorize article titles with TF-IDF
- Apply TruncatedSVD (LSA) for dimensionality reduction
- Cluster articles using KMeans
- Recommend similar articles within the same cluster, ranked by popularity

5. Matrix Factorization (SVD)
- Perform TruncatedSVD on the user-item matrix
- Select number of latent features based on metric performance (e.g., 200)
- Recommend articles with highest cosine similarity in latent space

## Summary
This project demonstrates:
- Popularity-based recommendations for cold-start users
- Collaborative filtering for users with interaction history
- Content-based clustering using TF-IDF + KMeans
- Matrix factorization for latent feature discovery

These approaches can be combined into a hybrid recommender system for improved accuracy across all user scenarios.