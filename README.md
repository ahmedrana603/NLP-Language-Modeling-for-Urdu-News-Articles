# 📰 Urdu News Language Modeling & Text Generation System

An end-to-end Natural Language Processing (NLP) pipeline for Urdu news articles built from scratch using real-world data from BBC Urdu.

This project scrapes, preprocesses, models, and generates BBC-style Urdu news articles using statistical language models without relying on pretrained NLP libraries.

---

## 🚀 Project Overview

The system performs:

- Scraping 200–300 real Urdu news articles  
- Unicode normalization and text cleaning  
- Custom Urdu linguistic preprocessing  
- Statistical language model training (Unigram, Bigram, Trigram)  
- BBC-style Urdu article generation  
- Perplexity-based evaluation  

All components — tokenization, stemming, lemmatization, smoothing, and backoff — are implemented from scratch.

---

## 📥 Data Collection

Source: https://www.bbc.com/urdu  
Articles Scraped: 200–300 complete news articles  
Each article is assigned a unique identifier.

---

## 🧹 Text Preprocessing Pipeline

Urdu presents unique preprocessing challenges due to Unicode variation, optional diacritics, and mixed scripts. The following cleaning steps are applied:

### Diacritics Removal (optional Urdu diacritics to reduce lexical sparsity)

### Noise Removal (URLs, Emojis, Navigation elements, Web artifacts)

### Non-Urdu Text Filtering (English words, Roman Urdu, Mixed-script tokens)

### Sentence Segmentation (Urdu punctuation: ۔ ؟ !)

### Whitespace Normalization (standardized spacing and formatting inconsistencies)

---

## 🔠 Custom Linguistic Processing

All linguistic tools are implemented manually.

### Urdu Tokenization (word boundary detection, punctuation handling, postposition handling, numbers replaced with `<NUM>`)

### Urdu Stemming (rule-based suffix stripping to reduce words to root forms)

### Urdu Lemmatization (plural normalization, gender normalization, rule-based mapping)

---

## 🧠 Language Models

The following statistical language models are implemented:

- Unigram Model (used for evaluation and backoff)  
- Bigram Model  
- Trigram Model with Backoff  

---

## 🔁 Backoff Strategy

Hierarchical backoff is applied:

Trigram → Bigram → Unigram

If a trigram context is unseen, the system falls back to bigram probability.  
If the bigram is also unseen, it falls back to unigram probability.

---

## 📊 Smoothing Techniques

To handle unseen n-grams and prevent zero probabilities:

### Laplace (Add-One) Smoothing

### Add-k Smoothing

These techniques ensure stable probability estimation and improved generalization.

---

## 📰 Article Generation System

The generation module supports:

- Language model selection (Bigram / Trigram)  
- Custom seed prompt input (5–8 Urdu words)  
- Automatic article generation  
- Right-to-Left (RTL) formatted output  
- Length and sentence constraints  

---

## 📏 Generation Constraints

- Minimum length: 200 words  
- Target length: 200–250 words  
- Maximum length: 300 words  
- At least 5 sentences required  
- Forced termination if EOS is not generated  

The generated text is designed to be original, formal, structured, coherent, and readable.

---

## 📈 Evaluation

Generated articles are evaluated using:

- Fluency  
- Grammatical correctness  
- Coherence  
- Readability  
- Perplexity score  

Comparative analysis includes:

- Raw vs. Cleaned preprocessing pipelines  
- Bigram vs. Trigram with Backoff  

---

## 🖥 Interface

- Console-based article generation interface  
- Model selection  
- Seed prompt validation  
- RTL Urdu display formatting  

---

## 📂 Project Structure

├── notebook.ipynb  
├── Metadata.json  
├── raw.txt  
├── cleaned.txt  
├── README.md  

---

## ⚙️ How to Run

1. Open the Jupyter Notebook  
2. Run the preprocessing pipeline  
3. Train the language models  
4. Launch the article generation interface  
5. Provide a valid 5–8 word Urdu seed prompt  

---

## 🎯 Key Features

- Fully custom Urdu NLP pipeline  
- No pretrained NLP libraries used  
- Statistical modeling from scratch  
- Backoff language modeling  
- Perplexity-based evaluation  
- RTL-aware Urdu text rendering  


---

## 📜 License

This project is developed for educational and research purposes only.

BBC content is used strictly for non-commercial academic experimentation.
