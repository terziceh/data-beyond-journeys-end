# Episode 3 — Movie Rating Predictor: From Idea to System Design

> 🎥 **Full Project Walkthrough Presentation:**  
> https://www.canva.com/design/DAHEa1EaYQQ/EEVuxZr6ZKcJhJw9PqaOOw/edit?utm_content=DAHEa1EaYQQ&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton

## 🎬 Overview

Today I mapped out the full design for a new data science project: a system that predicts how a user will rate a movie *before* watching it.

This project is designed to simulate how real-world platforms (Netflix, Spotify, TikTok) model user preferences and predict behavior using data.

Rather than jumping straight into building, I focused on structuring the project into two clear phases:

- Phase 1: Analytical MVP  
- Phase 2: Production-Grade System  

---

## 🎯 Core Problem

Most recommendation systems react to user behavior after the fact.

This project explores a more difficult question:

> Can we predict how a specific user will feel about a movie before they watch it?

This requires combining:
- user behavior data  
- movie metadata  
- (eventually) text-based signals  

---

## 🧠 System Design Approach

To keep the project realistic and buildable, I broke it into two phases.

---

## ⚙️ Phase 1 — Base Model (MVP)

**Goal:**  
👉 Prove the prediction system works end-to-end

**Pipeline:**
SQL → pandas → model → Streamlit


### What this phase includes:
- SQL dataset creation (users, movies, ratings)
- Feature engineering in pandas
- Baseline model (XGBoost / Random Forest)
- Model evaluation (RMSE / MAE)
- Simple Streamlit app for predictions

### Key Focus:
- clean, usable dataset  
- strong feature engineering  
- interpretable model  
- working user-facing output  

---

## 📊 Feature Engineering Plan

Initial features to be created:

- user average rating  
- user genre preferences  
- director affinity  
- actor frequency  
- movie popularity  
- release year trends  

> This layer is critical — the model is only as good as the features.

---

## 🤖 Modeling Strategy

Start simple, then scale:

**Phase 1:**
- XGBoost (primary baseline)
- Random Forest (comparison)

**Phase 2:**
- PyTorch neural network
- user embeddings
- movie embeddings
- optional NLP embeddings (reviews/summaries)

---

## 🚀 Phase 2 — Production System

**Goal:**  
👉 Transform the MVP into a scalable, reproducible data system

### Planned Stack:
- AWS S3 → raw + processed data storage  
- Databricks → data platform / transformations  
- Airflow → pipeline orchestration  
- Docker → environment reproducibility  
- Git → version control workflow  
- PyTorch → advanced modeling  

### Pipeline Vision:

S3 → Databricks → Feature Engineering → PyTorch Model → Predictions → App


---

## 🧱 What “Production-Grade” Means Here

Not over-engineering — but real structure:

- modular codebase  
- repeatable pipelines  
- scalable data handling  
- tracked experiments  
- deployable app  
- clear architecture  

---

## 📱 End Goal

A working application where a user can:

- select themselves  
- select a movie  

and receive:
- predicted rating  
- explanation of prediction  
- insights into their taste profile  

---

## 💼 Why This Project Matters

This project is intentionally designed to reflect real data science work.

It demonstrates:
- data extraction (SQL)  
- feature engineering (pandas)  
- predictive modeling (ML + PyTorch)  
- system design (pipeline architecture)  
- communication (Streamlit app)  

---

## 🔥 Key Insight

Phase 1 proves the idea works.  
Phase 2 proves I can build it like a real system.

---

## 🎯 Next Steps

- Define dataset schema  
- Build SQL queries for base dataset  
- Implement feature engineering in pandas  
- Train baseline model  
- Build initial Streamlit app  

---

## 🧩 Reflection

Today was focused on **thinking like a data scientist and engineer**, not just writing code.

Instead of rushing into implementation, I designed:
- the problem  
- the system  
- the roadmap  

This sets up the project to be both:
- buildable  
- portfolio-worthy  


