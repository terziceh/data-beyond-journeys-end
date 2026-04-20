# Episode X — Building a Movie Recommendation System (Baseline)

### 📍 Context

Today I built a full end-to-end movie recommendation system using the MovieLens dataset.
The goal wasn’t perfection — it was to understand how a real recommendation pipeline works from raw data to predictions.

---

### 🧱 What I Built

A baseline recommendation system that:

* Learns user behavior (average rating, rating consistency)
* Learns movie quality (average rating, popularity)
* Uses genre features to capture content similarity
* Predicts how a user would rate unseen movies
* Recommends top movies based on predicted ratings

This was built using a regression-based approach.

---

### ⚙️ Pipeline

Raw Data → EDA → Feature Engineering → Regression Model → Recommendations

Steps included:

* Merging ratings + movie metadata
* Creating user-level features:

  * average rating
  * number of ratings
  * rating standard deviation
* Creating movie-level features:

  * average rating
  * number of ratings
* One-hot encoding genres
* Training a Linear Regression model
* Generating predictions for unseen movies

---

### 📊 Model Performance

* RMSE: ~0.86
* Predictions clipped to rating range (0.5–5.0)

The model performs well as a baseline predictor of user ratings.

---

### 🎯 What I Observed

The system produces **high-quality recommendations**, but not fully personalized.

It tends to recommend:

* highly rated movies
* popular content
* globally “safe” picks

Example recommendations included:

* Planet Earth II
* Band of Brothers
* The Godfather
* Parasite

---

### ⚠️ Limitations

This version lacks deep personalization.

Main issues:

* Strong bias toward popular movies
* Limited user-specific taste modeling
* No collaborative filtering (user-to-user or item-to-item learning)
* Genre features are too simple to capture nuanced preferences

---

### 🧠 Key Insight

This is a **baseline recommender**, not a final system.

It behaves like:

> “Recommend the best movies overall for a user profile”

Not yet:

> “Recommend movies uniquely tailored to this specific user”

---

### 🚀 What’s Next

Next phase is turning this into a real system:

* Add user preference weighting (genre-based personalization)
* Introduce collaborative filtering (SVD / embeddings)
* Move pipeline into:

  * SQL Server (data layer)
  * Databricks / PySpark (processing)
* Build this as a scalable data product

---

### 📦 Artifact

Notebook for this episode:

`/assets/movie_recommender_poc.ipynb`

---

### 🧭 Reflection

This was the first time I built a recommendation system end-to-end.

The biggest takeaway wasn’t the model — it was understanding:

* how data flows through a system
* how features actually drive predictions
* why personalization is harder than it looks

This is the starting point.
