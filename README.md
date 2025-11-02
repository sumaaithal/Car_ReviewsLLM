# Car_ReviewsLLM

# 🚗 Car-ing Is Sharing — LLM Prototype Chatbot

> A prototype chatbot leveraging pre-trained LLMs to analyze customer car reviews — including sentiment detection, English–Spanish translation, question answering, and text summarization.

---

## 🧠 Overview

This project is a **proof-of-concept chatbot application** developed for **“Car-ing is Sharing”**, a car sales and rental company.  
It demonstrates how **Large Language Models (LLMs)** can automate diverse natural language processing tasks on customer reviews.

---

## 📊 Project Tasks

### 1️⃣ Sentiment Classification

**Goal:**  
Classify the sentiment (positive/negative) of five car reviews from the dataset `car_reviews.csv`.

**Steps:**
- Use a pre-trained sentiment analysis model.
- Generate predicted labels → `predicted_labels`
- Convert predictions to binary list `{0,1}` → `predictions`
- Evaluate performance:
  - Accuracy → `accuracy_result`
  - F1 Score → `f1_result`

**Outputs:**
```python
predicted_labels   # Model sentiment predictions
predictions        # Binary mapped labels
accuracy_result    # Accuracy metric
f1_result          # F1 metric


### 2️⃣ English–Spanish Translation

**Objective:**  
Translate the first two sentences of the **first review** in the dataset into Spanish, and evaluate the translation quality.

**Steps:**
1. Extract the first two sentences from the first review in `car_reviews.csv`.  
2. Use a **pre-trained English–Spanish translation LLM** (e.g., `Helsinki-NLP/opus-mt-en-es`) to generate the translation.  
3. Compare the model’s output against the **reference translations** provided in `reference_translations.txt`.  
4. Compute the **BLEU score** to measure how closely the generated translation matches the reference.  
5. Store:
   - The translated text → `translated_review`
   - The BLEU score → `bleu_score`


### 3️⃣ Extractive Question Answering (QA)

**Objective:**  
From the **second review** in the dataset, answer the question:  
> “What did he like about the brand?”

**Steps:**
1. Load the second review text as the context.  
2. Use a **pre-trained extractive QA model**, such as `deepset/minilm-uncased-squad2`.  
3. Define the inputs:
   ```python
   question = "What did he like about the brand?"
   context = <text_of_second_review>

### 4️⃣ Review Summarization

**Objective:**  
Summarize the **last review** from the dataset into a concise version of about **50–55 tokens**, preserving the key points and tone.

---

**Steps:**
1. Load the dataset `car_reviews.csv` and extract the last review.  
2. Use a **pre-trained summarization model**, such as `facebook/bart-large-cnn`.  
3. Generate a summary that captures the main ideas in fewer words.  
4. Store the summarized text in the variable `summarized_text`.

---

