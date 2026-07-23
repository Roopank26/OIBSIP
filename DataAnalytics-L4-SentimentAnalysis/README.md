# Sentiment Analysis on Airline Tweets

**Oasis Infobyte Data Analytics Internship**  
**Track:** Data Analytics | **Level:** L4  
**Project:** Sentiment Analysis

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-latest-green)
![NLTK](https://img.shields.io/badge/NLTK-NLP-orange)
![Matplotlib](https://img.shields.io/badge/matplotlib-latest-red)

---

## Overview

This project builds a sentiment classifier for airline passenger tweets. The goal is to automatically label tweets as **Positive**, **Negative**, or **Neutral** using classical NLP techniques. It covers the full pipeline — text cleaning, TF-IDF vectorization, model training, evaluation, and error analysis.

The dataset contains synthetic airline tweets inspired by the popular Twitter US Airline Sentiment dataset (February 2015).

---

## Objectives

- Load and explore a labeled text dataset
- Clean raw tweet text using an NLP preprocessing pipeline
- Convert text to features with TF-IDF vectorization
- Train and compare three ML models: Naive Bayes, Logistic Regression, and Linear SVM
- Evaluate models using accuracy, precision, recall, and F1-score
- Generate WordClouds and confusion matrices for interpretation
- Analyze misclassified examples to understand model weaknesses

---

## Dataset

- **Size:** 3,000 tweets
- **Sentiment Classes:** Positive, Negative, Neutral
- **Key Columns:** `text`, `airline_sentiment`
- **Airlines:** American, Delta, Southwest, United, US Airways, Virgin America, JetBlue, Alaska

---

## Technologies

- **Python 3.10+**
- **Pandas** — Data handling
- **NumPy** — Numerical operations
- **Matplotlib / Seaborn** — Visualization
- **Scikit-learn** — ML models and metrics
- **NLTK** — Text preprocessing
- **WordCloud** — Word cloud generation
- **Jupyter Notebook** — Analysis environment

---

## Installation

```bash
git clone https://github.com/Roopank26/OIBSIP.git
cd OIBSIP/DataAnalytics-L4-SentimentAnalysis

pip install -r requirements.txt
```

---

## Folder Structure

```
DataAnalytics-L4-SentimentAnalysis/
│
├── dataset.csv                          # Airline tweet dataset
├── Sentiment_Analysis.ipynb             # Full analysis notebook
├── requirements.txt                     # Dependencies
├── README.md                            # Documentation
├── LICENSE                              # MIT License
└── images/
    ├── sentiment_distribution.png
    ├── wordcloud_positive.png
    ├── wordcloud_negative.png
    ├── wordcloud_neutral.png
    ├── confusion_matrices.png
    ├── model_comparison.png
    └── tfidf_visualization.png
```

---

## Notebook Sections

1. **Setup** — Import libraries and configure NLTK
2. **Load Dataset** — Inspect shape, columns, and sample rows
3. **EDA** — Missing values, duplicates, sentiment distribution, airline breakdown
4. **Text Cleaning** — Lowercase, URL/hashtag/mention removal, lemmatization, stopword removal
5. **Feature Engineering** — TF-IDF with bigrams
6. **Train/Test Split** — 80/20 stratified split
7. **Model Training** — Naive Bayes, Logistic Regression, Linear SVM
8. **Evaluation** — Classification reports, confusion matrices, comparison table
9. **Visualizations** — WordClouds, TF-IDF bar charts
10. **Error Analysis** — Misclassified examples with explanations
11. **Conclusion** — Findings, limitations, real-world context

---

## Results

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Naive Bayes | ~0.78 | ~0.76 | ~0.78 | ~0.76 |
| Logistic Regression | ~0.83 | ~0.82 | ~0.83 | ~0.82 |
| Linear SVM | ~0.85 | ~0.84 | ~0.85 | ~0.84 |

Linear SVM performed best across all metrics. The main sources of confusion were sarcasm, short ambiguous tweets, and neutral statements that used emotionally charged vocabulary.

---

## Visualizations

All plots are saved in the `images/` folder at 300 DPI.

| Visualization | File |
|---------------|------|
| Sentiment distribution | `images/sentiment_distribution.png` |
| Positive WordCloud | `images/wordcloud_positive.png` |
| Negative WordCloud | `images/wordcloud_negative.png` |
| Neutral WordCloud | `images/wordcloud_neutral.png` |
| Confusion matrices | `images/confusion_matrices.png` |
| Model comparison | `images/model_comparison.png` |
| TF-IDF top words | `images/tfidf_visualization.png` |

---

## Key Observations

- **Lemmatization** reduced vocabulary size while keeping word meanings intact, which helped TF-IDF work better.
- **Bigrams** (`ngram_range=(1,2)`) captured phrases like "customer service" and "lost luggage" that carry strong sentiment.
- **Class imbalance** pushed all models toward predicting negative. Using `class_weight='balanced'` helped but didn't eliminate the bias.
- **WordClouds** showed clear sentiment signatures: negative tweets feature delays and lost baggage; positive tweets mention gratitude and crew; neutral tweets read like scheduled updates.

---

## Limitations

- **Sarcasm** — Hard to catch without contextual or user-history features
- **Short texts** — Tweets under ~10 words don't have enough signal
- **Dataset size** — 3,000 tweets is good for a portfolio demo, but production systems need way more data
- **Linear models** — Miss deeper semantic relationships that BERT-style models capture

---

## Possible Improvements

- Try contextual embeddings (BERT, RoBERTa)
- Add hand-crafted features (emoji counts, exclamation marks)
- Use SMOTE or class weights to better handle imbalance
- Experiment with ensemble methods (VotingClassifier, Stacking)
- Deploy as a web app with Streamlit or Gradio

---

## How to Run

```bash
jupyter notebook Sentiment_Analysis.ipynb
```

Run all cells in order. All visualizations will be saved to `images/`.

---

## Author

**Roopank Battu**  
Oasis Infobyte Data Analytics Intern  
[LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/Roopank26)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
