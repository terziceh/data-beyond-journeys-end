## Episode 6 — Upgrading the Movie Predictor with User Preference Modeling

Today I pushed the Movie Predictor past the “basic recommendation” stage and started turning it into a more personalized rating prediction system.

The earlier version of the model leaned more on general movie performance and broad user behavior, which gave me a starting point, but it still felt too generic. It could estimate ratings, but it was not really capturing *why* a specific user would like one movie more than another.

To improve that, I introduced a user preference layer based on genre history.

---

## What I Changed

I first merged the ratings data with the movie metadata so that each user rating could be tied directly to movie titles and genres. After that, I one-hot encoded the movie genres and used those genre columns to build user-level preference profiles.

Instead of only looking at how many ratings a user gave or what their average rating was, I created a genre preference matrix by weighting genre indicators with the user’s ratings. This gave me a way to estimate how strongly each user tends to favor genres like Action, Comedy, Drama, Thriller, and others.

From there, I tied together three levels of information:

### User Behavior
- Average rating  
- Number of ratings  
- Rating variability  

### Movie Performance
- Average movie rating  
- Number of ratings per movie  

### User Taste Alignment
- Genre preference scores  
- Interaction features between movie genres and user preferences  

This was the first version of the predictor that felt meaningfully personalized.

---

## What I Learned

The biggest improvement was conceptual.

Before this update, the model mostly answered:

> “Is this movie generally liked?”

Now it is starting to answer:

> “Is this movie likely to be liked by *this specific user*?”

That is a much better framing for a recommender system.

I also started evaluating performance at the user level instead of only looking at an overall score. That made it easier to see where the model was performing well and where it was still struggling.

One of the clearest takeaways was that the model tends to smooth predictions toward the middle range. It captures general taste patterns, but struggles with extreme preferences (very high or very low ratings). This suggests that while the feature engineering improved the model, the regression approach still has limitations.

---

## Why This Matters

This update moved the project from a simple movie-rating exercise into something closer to a real recommendation pipeline.

The system now includes:

- Data merging and preparation  
- User-level exploratory analysis  
- Genre-based preference modeling  
- Personalized interaction features  
- Predictive modeling for ratings  

This is a much stronger foundation for building a real-world data science project.

---

## Next Steps

The next iteration will focus on improving accuracy and model expressiveness:

- Normalize ratings relative to each user’s average  
- Try a stronger model (XGBoost)  
- Improve interaction features  
- Evaluate prediction quality more deeply per user  
- Explore matrix factorization (SVD) approaches  

---

## Final Thought

This was not the final version of the predictor, but it was a real step forward.

The project now feels less like “predicting movie scores” and more like building a system that understands user taste. That shift is important and moves the project closer to a portfolio-level data science system.
