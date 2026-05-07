# Fake News Detection Using Machine Learning
link to csv :- https://drive.google.com/file/d/18i8OAx4CkghnKVF-mhzdyKo21VNOfHhi/view?usp=sharing
## Overview

Fake News Detection is a Machine Learning project developed to classify news articles as **Fake** or **Real** based on textual content. The system uses Natural Language Processing (NLP) techniques along with machine learning algorithms to analyze news articles and identify misinformation.

The project demonstrates the complete workflow of text classification, including:

* Text preprocessing
* Data cleaning
* Tokenization
* Stopword removal
* Stemming
* Feature extraction using Bag of Words (BoW)
* Model training and evaluation
* Prediction of news articles

This project helps in understanding how machine learning and NLP can be applied to detect fake news efficiently.

---

# Features

* Detects whether a news article is Fake or Real
* Uses Natural Language Processing techniques
* Implements text preprocessing and stemming
* Converts text into numerical vectors using Bag of Words
* Trains machine learning classification models
* Evaluates model performance using accuracy and confusion matrix
* Predicts new unseen news articles

---

# Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* NLTK
* Scikit-learn
* Jupyter Notebook

---

# Dataset Information

The dataset contains news articles and labels indicating whether the article is fake or real.

## Dataset Columns

* `title` → News headline
* `text` → News article content
* `label` → Fake or Real news

## Target Variable

* `label`

  * `0` = Fake News
  * `1` = Real News

---

# Project Workflow

## 1. Importing Libraries

The required Python libraries are imported for data processing, visualization, NLP, and machine learning.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

---

# 2. Data Loading

The dataset is loaded using Pandas.

```python
df = pd.read_csv("news.csv")
```

---

# 3. Data Preprocessing

Text preprocessing is performed to clean and prepare the data.

## Preprocessing Steps

* Convert text to lowercase
* Remove special characters
* Remove punctuation
* Remove stopwords
* Apply stemming

Example:

```python
import re
from nltk.corpus import stopwords
from nltk.stem.porter import PorterStemmer
```

---

# 4. Stemming

Stemming reduces words to their root forms.

Example:

* Running → Run
* Playing → Play
* Connected → Connect

```python
ps = PorterStemmer()
```

---

# 5. Bag of Words (BoW)

The cleaned text data is converted into numerical vectors using the Bag of Words technique.

```python
from sklearn.feature_extraction.text import CountVectorizer

cv = CountVectorizer(max_features=5000)
X = cv.fit_transform(corpus).toarray()
```

---

# 6. Splitting the Dataset

The dataset is divided into training and testing sets.

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

---

# 7. Machine Learning Models Used

The following machine learning models are implemented:

## Logistic Regression

Used for binary text classification problems.

## Naive Bayes

A probabilistic classifier commonly used in NLP tasks.

## Random Forest Classifier

An ensemble learning algorithm that improves prediction accuracy.

---

# 8. Model Training

The selected model is trained using the training dataset.

Example:

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier()
model.fit(X_train, y_train)
```

---

# 9. Model Evaluation

The model performance is evaluated using:

* Accuracy Score
* Confusion Matrix
* Classification Report

Example:

```python
from sklearn.metrics import accuracy_score

accuracy = accuracy_score(y_test, y_pred)
print(accuracy)
```

---

# 10. Prediction

The trained model predicts whether a news article is Fake or Real.

Example:

```python
sample_news = ["Breaking news article text here"]

prediction = model.predict(cv.transform(sample_news))
```

---

# Output

* `0` → Fake News
* `1` → Real News

---

# Exploratory Data Analysis (EDA)

The project includes data visualization techniques such as:

* Fake vs Real news distribution
* Word frequency analysis
* Count plots
* Confusion matrix heatmap

---

# Results

The project successfully:

* Cleans and preprocesses text data
* Converts textual data into machine-readable format
* Trains machine learning models
* Detects fake news with good accuracy
* Predicts unseen news articles effectively

---

# Project Structure

```bash
Fake-News-Detection/
│
├── Fake_News_Detection.ipynb
├── news.csv
├── README.md
└── requirements.txt
```

---

# Installation

## Clone the Repository

```bash
git clone https://github.com/your-username/Fake-News-Detection.git
```

---

## Navigate to Project Folder

```bash
cd Fake-News-Detection
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Requirements

```txt
pandas
numpy
matplotlib
seaborn
nltk
scikit-learn
jupyter
```

---

# How to Run

1. Open Jupyter Notebook
2. Open `Fake_News_Detection.ipynb`
3. Run all cells step by step
4. Train the model
5. Test predictions using custom news articles

---

# Future Improvements

* Improve model accuracy using advanced NLP techniques
* Use TF-IDF instead of Bag of Words
* Implement Deep Learning models like LSTM
* Deploy using Flask or Streamlit
* Add real-time news verification
* Integrate web scraping for live news analysis

---

# Applications

* News verification systems
* Social media monitoring
* Journalism and media analysis
* Misinformation detection
* Online content filtering

---

# Conclusion

This project demonstrates how Machine Learning and Natural Language Processing can be used to detect fake news efficiently. By applying preprocessing techniques, stemming, and Bag of Words vectorization, the model learns textual patterns and predicts whether news content is fake or real.

The project provides a strong foundation for building advanced misinformation detection systems.

---

# Author

Geo Mathew

---

# License

This project is developed for educational and learning purposes.
