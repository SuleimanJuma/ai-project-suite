# NLP with spaCy: Amazon Product Reviews Analysis

## Overview
This README explains **step-by-step what is happening and why** while performing **Named Entity Recognition (NER) and rule-based sentiment analysis** on Amazon product reviews using spaCy and pandas, with enough context for beginners to follow and understand.

## About the Dataset
- **Source:** Amazon product reviews dataset.
- **Content:** Millions of customer reviews with star ratings.
- **Labels:**
  - `__label__1` (1-2 stars): Negative Sentiment.
  - `__label__2` (4-5 stars): Positive Sentiment.
  - Neutral reviews (3 stars) are excluded.
- Reviews typically include a **title followed by the review text**.

## Project Goals
- ✅ Use **Named Entity Recognition (NER)** to extract product names and brand names using spaCy.
- ✅ Perform **rule-based sentiment analysis** using star ratings as ground truth.
- ✅ Provide **clean, readable outputs and explanations** for learning and GitHub documentation.

## Why This Project?
Understanding how to extract structured information (product names, brands) and sentiment from unstructured reviews is critical for **real-world NLP tasks**, such as:
- Monitoring customer feedback.
- Analyzing brand perception.
- Identifying product-specific issues or praise.

## Step-by-Step Detailed Explanation

### 1️⃣ Import Required Libraries
```python
import spacy
import pandas as pd
import numpy as np
import re
```
**Why?**
- `spaCy` for NLP tasks and NER.
- `pandas`, `numpy` for structured data manipulation.
- `re` for regex-based extraction of labels from text.

### 2️⃣ Load spaCy's English Model
```python
nlp = spacy.load("en_core_web_md")
```
**Why?** Loads a pre-trained medium English model to enable entity recognition with high accuracy.

### 3️⃣ Load Amazon Reviews Data
You will load either:
- Extracted `.txt` files with reviews.
- Compressed `.bz2` files for efficient storage and reading.

**Why?** To work with real-world, large-scale review data for practical learning.

### 4️⃣ Extract Labels and Review Text
Using regex, extract:
- **Labels (`1` or `2`):** Determine sentiment.
- **Review text:** For cleaning and NER processing.

**Why?** Star ratings provide a **rule-based sentiment label** to evaluate against the text.

### 5️⃣ Data Cleaning
Clean each review by:
- Lowercasing.
- Removing stop words and punctuation.
- Lemmatizing tokens.

**Why?** Clean data improves the quality of NER and helps in consistent text analysis.

### 6️⃣ Rule-Based Sentiment Analysis
Based on extracted labels:
- `label == 2`: **Positive Sentiment.**
- `label == 1`: **Negative Sentiment.**

**Why?** This method provides a straightforward baseline sentiment analysis using explicit labels.

### 7️⃣ Named Entity Recognition (NER)
Pass cleaned reviews into spaCy to extract:
- `PRODUCT`: Names of products mentioned.
- `ORG`: Brand names mentioned.

**Why?** Extracting entities helps identify which products and brands are discussed in reviews, providing structured business insights from unstructured data.

### 8️⃣ Display Results
For each review, display:
- The cleaned review.
- Extracted label and interpreted sentiment.
- Extracted products and brand names.

## Sample Output
```
clean_review: label__2 great cd lovely pat great voice generation listen cd year love good mood ...
Extracted label: 2
Sentiment: Positive
Brands: []
Products: []
```

**This structured output helps visualize how text is processed into actionable information.**

## Key Learnings
✅ Using **spaCy for NER in practical NLP projects.**
✅ Applying **rule-based sentiment analysis** using labeled data.
✅ Building a **clean, understandable NLP pipeline**.
✅ Extracting structured information from unstructured text data.



