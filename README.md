# 📊 Customer Sentiment Analysis Using NLP

### Transforming App Reviews into Business Intelligence

---

## 🚀 Project Summary

This project analyzes real-world Chat GPT application reviews using **Natural Language Processing (NLP)** to extract customer sentiment and generate actionable business insights.

Instead of relying only on star ratings, this project evaluates the **actual emotional tone** of review text using polarity scoring and sentiment classification.

The objective was to answer:

* Are customer ratings aligned with textual sentiment?
* What percentage of users are truly satisfied?
* Are there hidden dissatisfaction patterns?
* How does sentiment trend over time?

---

## 🧠 Problem Statement

Star ratings alone can be misleading.

Example from dataset:

* ⭐ 1-star rating with text: *"great app"* → Positive sentiment
* ⭐ 3-star rating with complaint → Negative polarity

This creates a **Rating–Sentiment Mismatch Problem**, which businesses often overlook.

This project solves that using NLP-based sentiment scoring.

---

## 🛠️ Tech Stack

| Category      | Tools Used    |
| ------------- | ------------- |
| Language      | Python        |
| Data Handling | Pandas, NumPy |
| NLP           | TextBlob      |
| Visualization | Matplotlib    |
| Environment   | Google Colab  |

---

## 📂 Dataset Features

| Column                   | Description              |
| ------------------------ | ------------------------ |
| review_id                | Unique identifier        |
| review                   | Customer review text     |
| ratings                  | Star rating (1–5)        |
| review_date              | Timestamp                |
| sentiment_polarity       | Score (-1 to +1)         |
| sentiment                | Classified label         |
| sentiment_polarity_group | Grouped sentiment        |
| month_year               | Extracted monthly period |

---

## 🔍 Methodology

### 1️⃣ Data Preprocessing

* Converted review_date to datetime
* Extracted month_year
* Handled missing values
* Structured polarity grouping

---

### 2️⃣ Sentiment Scoring

Used TextBlob polarity:

* -1 → Fully Negative
* 0 → Neutral
* +1 → Fully Positive

```python
from textblob import TextBlob

df['sentiment_polarity'] = df['review'].apply(
    lambda x: TextBlob(str(x)).sentiment.polarity
)
```

Classification logic:

* polarity > 0 → Positive
* polarity = 0 → Neutral
* polarity < 0 → Negative

---

### 3️⃣ Sentiment Distribution Analysis

* Calculated frequency of Positive, Neutral, Negative
* Identified overall customer mood
* Measured satisfaction ratio

---

### 4️⃣ Rating vs Sentiment Comparison

Key finding:

Text sentiment and star ratings do not always match.

This insight is critical because:

> Businesses relying only on star ratings may misinterpret customer emotion.

---

### 5️⃣ Monthly Trend Analysis

Grouped by month_year:

```python
sentiment_over_time = df.groupby(
    ['month_year','sentiment']
).size().unstack(fill_value=0)
```

This enables:

* Trend monitoring
* Sentiment tracking post updates
* Release impact evaluation

---

## 📊 Key Insights

### ✅ Majority Reviews Are Positive

High polarity scores indicate strong user satisfaction.

### ⚠️ Rating-Sentiment Mismatch Exists

Multiple reviews show contradiction between rating and emotional tone.

### 🤖 Emoji & Short Review Limitation

Reviews like:

* 👍
* ❤️
* “best”

Often return polarity = 0
Showing limitation of basic lexicon-based models.

### 📈 Strong Engagement in August 2024

High review density in 2024-08 indicates peak activity period.

---

## 💼 Business Impact

This project demonstrates how sentiment analysis can:

* Detect hidden dissatisfaction
* Improve product feedback loop
* Support feature prioritization
* Identify misleading rating trends
* Improve customer retention strategy

---

## 📌 Why This Project Stands Out

✔ Combines structured + unstructured data
✔ Applies NLP in real business context
✔ Extracts strategic insights (not just charts)
✔ Identifies system limitations
✔ Demonstrates analytical thinking

---

## 🧠 Skills Demonstrated

* NLP Fundamentals
* Sentiment Classification
* Data Cleaning & Feature Engineering
* GroupBy & Aggregation
* Business Insight Extraction
* Data Storytelling
* Analytical Thinking

---

## 👤 Author

Hrushikesh Rokade
Data Analyst | Python | SQL | Excel | Power BI

---
