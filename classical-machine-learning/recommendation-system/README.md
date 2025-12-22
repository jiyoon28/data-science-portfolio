# Recommendation System

## Project Overview

This project builds a complete recommendation engine for article suggestions using multiple approaches. The system addresses different user scenarios from cold-start (new users) to users with rich interaction history, demonstrating the strengths and trade-offs of various recommendation techniques.

---

## Recommendation Approaches

| Approach | Use Case | Method |
|----------|----------|--------|
| Rank-Based | Cold-start users | Recommend most popular articles |
| User-User Collaborative Filtering | Users with history | Find similar users, recommend their unseen articles |
| Content-Based Filtering | Item similarity | TF-IDF vectorization + KMeans clustering |
| Matrix Factorization (SVD) | Latent features | TruncatedSVD on user-item matrix |

---

## Key Findings

- **Cold Start Solution**: Popularity-based recommendations effectively serve new users with no interaction history
- **Collaborative Filtering**: Users with similar reading patterns benefit most from user-user similarity recommendations
- **Content Clustering**: TF-IDF combined with KMeans successfully groups thematically related articles
- **Latent Features**: Matrix factorization with 200 latent dimensions achieved optimal recommendation quality

---

## Methodology

1. **Exploratory Data Analysis**: Handle missing values, compute descriptive statistics, identify popular articles
2. **Rank-Based Recommendations**: Recommend top-n most viewed articles for new users
3. **User-User Collaborative Filtering**: Build user-item matrix, compute cosine similarity between users
4. **Content-Based Filtering**: Vectorize article titles with TF-IDF, apply dimensionality reduction (LSA), cluster with KMeans
5. **Matrix Factorization**: Perform TruncatedSVD, recommend articles with highest cosine similarity in latent space

---

## Project Structure

| Path | Description |
|------|-------------|
| src/ | Implementation notebooks and test files |
| data/ | User-article interaction data |

---

## Technologies Used

- **Language**: Python 3.8+
- **Libraries**: pandas, numpy, scikit-learn, matplotlib, seaborn, plotly
- **Techniques**: Collaborative Filtering, Content-Based Filtering, TF-IDF, SVD, KMeans Clustering

---

## Testing

The project includes validation tests for each recommendation approach:

```bash
pytest project_tests.py
```

Test coverage includes:
- EDA outputs verification
- Top article retrieval validation
- User-user similarity results
- Cold-start user recommendations
- Matrix factorization reconstruction quality