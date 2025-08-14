# PaperSense: Medical Literature Topic and Success Analysis

This project focuses on exploring medical research papers and hospital data using unsupervised Natural Language Processing (NLP) techniques. This time, I worked with an unsupervised task and tried my best to extract meaningful insights. The process began with comprehensive preprocessing using tokenization and lemmatization, followed by baseline modeling approaches.

For topic modeling (**Task 1**), I applied **LDA**, **NMF**, and **BERTopic**.  
For sentiment analysis (**Task 2**), I used **VADER**, **TextBlob**, and **SentiWordNet**.  
I tuned all three topic modeling models and found that NMF performed best. In sentiment analysis, VADER emerged as the most consistent model due to its lexicon and rule-based structure. After selecting the best models, I analyzed the results using a series of visualizations to answer key research questions. Even though the task was unsupervised, I still tested the models on unseen data for further validation.

This project was particularly challenging due to:
- Managing two parallel tasks
- The time-consuming nature of tuning unsupervised models
- Difficulty in choosing appropriate evaluation metrics in the absence of labeled data

---

## Project Requirements

### System Requirements
- Python 3.8+ (recommended: Python 3.9 or higher)
- RAM: Minimum 8GB (16GB recommended for processing 200k papers)
- Storage: 5GB free space for datasets and model outputs
- Processing: Multi-core CPU recommended (BioBERT embeddings are computationally intensive)

### Core Python Libraries
- `pandas` — Data manipulation and analysis  
- `numpy` — Numerical computing  
- `scipy` — Scientific computing utilities  
- `nltk` — Tokenization and preprocessing  
- `spacy` — Advanced NLP processing  
- `gensim` — Topic modeling (LDA)  
- `transformers` — BioBERT embeddings  
- `bertopic` — BERT-based topic modeling  
- `scikit-learn` — NMF implementation, TF-IDF vectorization  
- `vaderSentiment` — Lexicon-based sentiment analysis  
- `textblob` — Sentiment scoring and polarity  
- `sentiwordnet` — Lexical sentiment resource  
- `umap-learn` — Dimensionality reduction  
- `hdbscan` — Density-based clustering  
- `scikit-learn` — ML utilities and metrics  
- `matplotlib` — Plotting  
- `seaborn` — Statistical visualization  
- `plotly` — Interactive plots  
- `wordcloud` — Word cloud generation  
- `requests` — API calls to MeSH  
- `json` — Handling API responses  
- `re` — Regular expressions for text cleaning  

### Dataset Requirements
- **Primary Dataset**: "200,000 Medical Research Paper Summary" (Kaggle)  
- **Format**: CSV with columns — ID, BACKGROUND_OBJECTIVES, METHODS, RESULTS_CONCLUSIONS  
- **Size**: ~2–3GB  
- **Source**: Based on PubMed 200k RCT dataset  

### Optional Enhancements
- `jupyter` — Interactive environment  
- `tqdm` — Progress bars  
- `pickle` — Model serialization  

---

## Project Sections

### 1. Importing Libraries
All required libraries for data manipulation, visualization, NLP, modeling, and evaluation were imported.

### 2. Reading and Transforming Both Datasets
- Loaded the research paper dataset and retained: `ID`, `OBJECTIVE_BACKGROUND`, `METHODS`, `RESULTS_CONCLUSIONS`
- Loaded the hospital dataset, combining all columns (excluding Age Group and Gender) into `Medical_Information`
- Used first 50,000 rows from both datasets for consistency and efficiency

### 3. Exploratory Data Analysis (EDA) on Raw Data
- Most frequent terms in research papers  
- Distribution of mathematical terms and formulas by section  

### 4. Data Cleaning
Applied to both datasets:
- Removed URLs  
- Removed mathematical formulas  
- Removed lone characters  
- Removed excessive spaces/tabs/newlines  
- Converted to lowercase  
- Removed stopwords  
- Removed punctuation  

### 5. Pattern Discovery and Visualization on Cleaned Data

**Univariate Analysis**
- Top 20 research goals from `OBJECTIVE_BACKGROUND`
- Common phrasing in conclusions
- KMeans clustering on `METHODS`
- Most common unigrams/bigrams per section

**Bivariate Analysis**
- Readability vs length (Flesch Reading Ease)

**Multivariate Analysis**
- Vocabulary richness, readability (Flesch), complexity (Gunning Fog Index)
- Structural coherence (TF-IDF cosine similarity)

### 6. Preprocessing
Applied tokenization and lemmatization to all text data.

### 7. Modeling

**Task 1: Topic Modeling**
- LDA, NMF, BERTopic  
- NMF selected after tuning

**Task 2: Sentiment Analysis**
- VADER, TextBlob, SentiWordNet  
- VADER selected for consistency and clarity

### 8. Hyperparameter Tuning
- Custom grids for all three topic models  
- NMF showed highest topic coherence and interpretability

### 9. Testing on Unseen Data
- Evaluated generalization and consistency despite being unsupervised

---

## Final Notes
This project explored linguistic, structural, and thematic patterns in medical texts.  
Handling two datasets, multiple unsupervised tasks, and metric selection posed challenges, but systematic experimentation and visualization enabled meaningful insights and final model selection for both tasks.
