# xyz-adopter-prediction

Predictive modeling project to identify potential premium subscribers on a freemium music-listening social platform. Built using an imbalanced dataset from a prior marketing campaign, this project develops a classification model to help XYZ effectively target users likely to adopt the premium service in the next 6 months.

---

## 🎯 Business Context

XYZ is a music-based social networking platform that uses a freemium model—offering basic services for free and premium features via subscription. To optimize its marketing budget and boost conversion rates, XYZ needs to predict which users are most likely to convert to paid subscribers when targeted by future campaigns.

---

## 📁 Dataset Overview

- **Total records**: 41,540 users
- **Positive class (adopters)**: 1,540 users (3.7%)
- **Negative class (non-adopters)**: 40,000 users (96.3%)
- **Target variable**: `adopter` (1 = converted, 0 = did not convert)
- **Features**: 25+ demographic, behavioral, and time-delta features

Key variable types:
- Demographic: age, gender, good_country
- Network: friend count, subscriber friend count
- Engagement: songs listened, loved tracks, posts, playlists
- Temporal changes: `delta_` variables indicate behavior changes over the 3 months prior to the campaign

---

## 🧠 Modeling Approach

We evaluated multiple classifiers and feature selection strategies, including:

### Models Explored:
- **K-Nearest Neighbors (KNN)**
- **Naive Bayes**
- **Decision Tree** ✅ *(Final Model)*

### Key Techniques:
- **Oversampling using `ROSE`** to handle severe class imbalance
- **Information Gain** for feature selection (for KNN and Naive Bayes)
- **5-Fold Cross-Validation** for robust evaluation

---

## 📊 Metrics Philosophy

We selected **Recall** as the primary metric, aligned with business needs:
> “Better to target more non-adopters than to miss a potential high-value adopter.”

### Evaluation Metrics:
- **Recall**: 85.1%
- **F1 Score**: 0.11
- **AUC**: 0.72
- **Threshold Optimization**: Final model tuned at a 0.4 threshold for best Recall-F1 trade-off

---

## 🚀 Key Insight

Top 25% users (by predicted probability) are **twice as likely** to convert compared to a random sample. This makes the lift curve a valuable targeting strategy for future campaigns.

---

## 📌 Final Recommendation

XYZ should:
- Use the Decision Tree model to predict likely adopters
- Target the top 25% scorers for maximum lift and marketing efficiency
- Adjust decision thresholds based on budget constraints:
  - Lower threshold = High Recall, more aggressive targeting
  - Higher threshold = Higher Precision, cost-controlled targeting

---

## 📂 Deliverables

- `Codefile.pdf` – Full technical write-up with code, metrics, and visualizations
- `presentation.mp4` – 5-minute executive-level presentation (managerial document)
  🎥 [Watch the 5-minute presentation](docs/presentation.mp4)


---

## 👥 Team Members

- Harshal Sable  
- Abraham George  
- Aakash Patil  
- Rahma Hassan  
- Charlotte Wang  
