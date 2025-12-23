---
title: Lexicon based sentiment analysis
---

## Lexicon-Based Sentiment Analysis and Machine Learning Classification

This project was part of my learning to get some good habits when working in NLP. and we've selected the sentiment analysis because it is one of the well known NLP tasks, and can be impactful when analyzing customer feedback.

Sentiment analysis helps in finding the emotional tone of a sentence. It helps businesses, researchers and developers to understand opinions and sentiments expressed in text data which is important for applications like social media monitoring, customer feedback analysis and more.

Vader is a lexicon and rule-based tool that is designed for social media text, customer reviews, and other short, informal pieces of communication. It doesn't just look at whether a word is "good" or "bad"; it understands valence (the intensity of the emotion). For example, it knows that "excellent" is more positive than "good," and recognizes :) as positive and :( as negative, and it combines lexicon and heuristics to achieve this.

[NLTK](https://www.nltk.org/) is a python library designed for Natural Language Processing. It provides a suite of tools for tasks such as tokenization, stemming, tagging, and parsing. In this analysis, we used the **NLTK VADER (Valence Aware Dictionary and sEntiment Reasoner)** lexicon to generate initial sentiment scores.

**Data Preprocessing**

Processing textual data differs fundamentally from handling numerical or ordinal data. To restructure raw information for lexicon-based analysis and reporting, we implemented a rigorous cleaning pipeline. The preprocessing steps included:
- **Punctuation and Digit Removal:** Eliminating non-alphabetic characters to reduce noise.
- **Stopword Removal:** Filtering out common words (e.g., "the", "is") that carry little semantic value.
- **Stemming and Lemmatization:** Reducing words to their root forms to consolidate similar meanings.
- **Synonym Handling:** Standardizing vocabulary to ensure consistency across the dataset.

**Model Selection**

Once the review data was cleaned, we transitioned to a supervised machine learning approach to classify reviews as either positive or negative. For this task, we implemented **Logistic Regression**, a "shallow" learning model. Despite its simplicity, Logistic Regression is highly effective for binary classification and offers excellent interpretability.

**Feature Engineering and Vectorization**

Because machine learning models require numerical input, we must represent textual data in a mathematical vector space. We compared two primary techniques for this transformation:

- **Bag of Words (BoW):** This approach treats a document as an unordered collection of tokens. It builds a vocabulary of unique words and represents each document as a vector of word counts. While straightforward and effective for topic classification, its main limitation is that it treats all words as equally important, regardless of their frequency across the dataset.
- **TF-IDF (Term Frequency–Inverse Document Frequency):** This is a statistical heuristic that improves upon BoW by weighting terms. It downweights high-frequency words that appear across all documents and boosts rarer, more informative terms that are specific to certain reviews.

**Training and Evaluation**

To ensure the model's ability to generalize to unseen data, we partitioned the dataset into **training and testing sets**. 

Following the training phase, we aimed to validate the relationship between our computational results and human feedback by addressing the following research question: *To what degree do the lexicon-derived sentiment scores correlate with the explicit venue ratings provided by the users?*