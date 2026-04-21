# Data: Beyond Journey's End

School built the foundation.  
This is where the real journey begins.

This repository documents my continued development across **data analytics, data engineering, data science, and early-stage AI systems** through hands-on projects and applied learning.

Each entry is structured like an **episode in a walkthrough series** — capturing what was built, how it was built, what went wrong, and what was learned.

The goal is simple:

> Treat learning like an engineering log — and build in public.

---

## 🧭 Current Focus

- Building **end-to-end systems**, not isolated analyses  
- Strengthening fundamentals in **SQL, Python, and data modeling**  
- Developing **recommendation systems and predictive models**  
- Exploring **automation workflows and AI-assisted systems**  

---

## 🧠 Topics Explored

- Data analytics and dashboard design  
- System design and workflow mapping  
- Python (pandas) for data manipulation  
- Recommendation system fundamentals  
- Machine learning basics (regression, evaluation)  
- Early AI agent and automation concepts  
- Data pipeline thinking  

---

## 🏗️ Structure

Each episode includes:

- The problem being explored  
- The system or idea being built  
- Technical approaches used  
- Challenges encountered  
- Key lessons learned  

Some entries are quick experiments.  
Others represent deeper system and architectural thinking.

---

## 📂 Episode Log

### Episode 0 — Fitness Meal Planner AI Agent (Prototype)

Initial exploration into building a simple AI agent for personalized nutrition planning based on fitness goals and preferences.

---

### Episode 1 — Invoice Reader System Design

Mapped out the current utility invoice workflow and identified inefficiencies in manual processing. Designed a conceptual pipeline to transform unstructured invoices into structured data.

---

### Episode 2 — Invoice Reader Workflow Mapping

Focused on breaking down the system into a clearer data flow, thinking through how inputs, processing, and outputs connect in a real workflow.

---

### Episode 3 — Movie Rating Predictor (Mockup)

Began exploring recommendation systems and rating prediction using movie data. Practiced thinking about user behavior, aggregation logic, and how predictions could be structured.

---

### Episode 4 — Analytics → Systems Thinking

Shifted mindset from building individual analyses to thinking in terms of full systems and pipelines. Began focusing on how components connect end-to-end.

---

### Episode 5 — Movie Recommendation System (Prototype)

Built an end-to-end recommendation system using the MovieLens dataset.

This iteration moved beyond a mockup into a working pipeline:

- Engineered user-level and movie-level features  
- Trained a regression model to predict user ratings  
- Generated recommendations for simulated and real users  
- Evaluated outputs against actual user behavior  

**Key takeaway:**

> A recommender system is not just about predicting ratings — it’s about understanding how user behavior, content features, and system design interact.

This version serves as a **baseline system**, highlighting both the strengths of simple models and the limitations of popularity-driven approaches.

---

### Episode 6 — Personalized Movie Predictor (User Preference Modeling)

Upgraded the recommendation system to incorporate **user-specific taste modeling** using genre-based preference engineering.

This iteration introduced a more advanced feature pipeline:

- Built **user-level genre preference profiles** using weighted ratings  
- Engineered **interaction features** between user preferences and movie genres  
- Combined:
  - user behavior  
  - movie performance  
  - personalized genre alignment  
- Evaluated model performance at both **global and per-user levels**  

**Key takeaway:**

> Moving from general prediction to personalization is the turning point in building real recommendation systems.

This version revealed important limitations:

- Regression models tend to **smooth predictions toward the average**  
- Extreme preferences (loves/hates) are harder to capture  
- Model performance improves significantly with **more user data**  

This episode marks the transition from a basic recommender to a **true personalized prediction system**, and sets the stage for more advanced approaches like gradient boosting and matrix factorization.

---

### Filler — Rest Days

Short entries used to maintain consistency and reflection, even on lighter or non-technical days.

---

## 💡 Philosophy

> Keep building. Keep learning. Keep documenting.

Progress comes from iteration, not perfection.

---

## 🚀 Direction

This repository is evolving toward:

- Stronger **data science rigor** (modeling, evaluation, experimentation)  
- Real-world **automation systems and pipelines**  
- AI-assisted tools and intelligent systems  

**Long-term goal:**

> Build end-to-end systems that combine data, automation, and intelligence to support real-world decision making.
