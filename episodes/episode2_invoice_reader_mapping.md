# Episode 2 — Framing the Problem

## 📽️ Presentation

View the full Invoice Reader System presentation here:  
👉 [Invoice Reader Presentation (Google Slides)](https://docs.google.com/presentation/d/1l5cnoLCeXrX6UQbcsl3nOJtV1AcXdxatOv4FU4stKr4/edit?usp=sharing)


Today focused on stepping back from development and designing the full story behind the invoice reader system.

Instead of just building the tool, I worked on clearly defining:
- the current workflow
- existing inefficiencies
- how a data-driven system would improve the process

---

## 🧾 Current State Analysis (Existing Workflow)

### Objective
Understand how utility invoice processing currently works and identify friction points before introducing automation.

### Observations
- Invoice data is manually reviewed and entered into AIM (legacy system)
- Data exists in unstructured PDF format
- Repetitive entry tasks increase time and risk of human error
- No standardized structure for extracting or validating key fields
- Limited ability to analyze data beyond basic entry

### Key Pain Points
- Time-intensive manual entry
- Inconsistent data quality
- Lack of visibility into trends (cost, usage, anomalies)
- Workflow is task-driven, not data-driven

---

## 🧠 System Design Thinking

### Objective
Reframe invoice processing from a manual task into a structured data pipeline.

### Proposed Shift
Instead of:
> “Enter invoice data into a system”

The process becomes:
> “Transform raw documents into a reusable data asset”

### Conceptual Pipeline
1. PDF Invoice (unstructured input)
2. Data Extraction (Gemini / OCR)
3. Data Structuring (Python processing)
4. Validation Layer (rules + checks)
5. Storage (SQL database)
6. Analytics Layer (Excel / Tableau dashboards)

---

## 📊 Presentation Planning (For Professors)

### Goal
Explain both:
- **Why the current system is inefficient**
- **How the redesigned process improves it**

### Approach
- Start with current workflow (swimlane or process diagram)
- Highlight bottlenecks and inefficiencies
- Introduce redesigned pipeline
- Show how structured data enables:
  - faster processing
  - better accuracy
  - analytics and decision-making

---

## 🔗 Key Insight

The biggest realization today:

This is not just an automation project —  
it is a **business process redesign problem supported by data engineering**.

---

## 🚧 Challenges
- Clearly mapping a legacy workflow that is not formally documented
- Translating a technical solution into a business-friendly explanation
- Designing something that improves the process without replacing AIM

---

## 🔜 Next Steps
- Create swimlane diagram of current vs future state
- Build visual pipeline diagram for presentation
- Continue refining invoice extraction pipeline
- Begin linking structured data to dashboards

---

## 💡 Reflection

Today was less about coding and more about thinking like a systems designer.

Before building anything further, I needed to answer:
“What problem am I actually solving?”

That clarity will drive everything moving forward.
