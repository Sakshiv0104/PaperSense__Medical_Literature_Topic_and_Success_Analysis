# Unveiling Themes and Sentiments in Biomedical Abstracts with BERTopic, LDA, NMF, and Sentiment Tools

This project focuses on exploring medical research papers and hospital data using unsupervised Natural Language Processing (NLP) techniques. This time, I worked with an unsupervised task and tried my best to extract meaningful insights. The process began with comprehensive preprocessing using tokenization and lemmatization, followed by baseline modeling approaches.

For topic modeling (Task 1), I applied LDA, NMF, and BERTopic. For sentiment analysis (Task 2), I used VADER, TextBlob, and SentiWordNet. I tuned all three topic modeling models and found that NMF performed best. In sentiment analysis, VADER emerged as the most consistent model due to its lexicon and rule-based structure. After selecting the best models, I analyzed the results using a series of visualizations to answer key research questions. Even though the task was unsupervised, I still tested the models on unseen data for further validation.

This project was particularly challenging due to the need to manage two parallel tasks, the time-consuming nature of tuning unsupervised models, and the difficulty of choosing appropriate evaluation metrics in the absence of labeled data.

## 1. Importing Libraries

All required libraries for data manipulation, visualization, NLP, modeling, and evaluation were imported.

## 2. Reading and Transforming Both Datasets

- Loaded the research paper dataset and retained the following four columns:  
  `ID`, `OBJECTIVE_BACKGROUND`, `METHODS`, `RESULTS_CONCLUSIONS`  
- Loaded the hospital dataset and combined all columns (excluding Age Group and Gender) into one: `Medical_Information`  
- Used the first 50,000 rows from both datasets for consistency and efficiency

## 3. Exploratory Data Analysis (EDA) on Raw Data

- Most frequent terms in research papers  
- Distribution of mathematical terms and formulas by section  

## 4. Data Cleaning

Steps applied to both datasets:

- Removed URLs  
- Removed mathematical formulas (digits and symbols)  
- Removed lone characters  
- Removed excessive spaces, tabs, and newlines  
- Converted all text to lowercase  
- Removed stopwords  
- Removed punctuation  

## 5. Pattern Discovery and Visualization on Cleaned Data

**Univariate Analysis:**  
- Top 20 research goals from `OBJECTIVE_BACKGROUND`  
- Common phrasing in research conclusions  
- Clustering of `METHODS` using KMeans  
- Most common unigrams and bigrams per section  

**Bivariate Analysis:**  
- Readability vs length using Flesch Reading Ease Score  

**Multivariate Analysis:**  
- Vocabulary richness, readability (Flesch), and complexity (Gunning Fog Index) per section  
- Structural coherence using TF-IDF cosine similarity  

## 6. Preprocessing

Applied tokenization and lemmatization to all text data prior to modeling.

## 7. Modeling

**Task 1: Topic Modeling**  
- Applied LDA, NMF, and BERTopic  
- NMF selected as final model after tuning and evaluation  

**Task 2: Sentiment Analysis**  
- Used VADER, TextBlob, and SentiWordNet  
- VADER selected based on performance and clarity of results  

## 8. Hyperparameter Tuning

All three topic modeling approaches were tuned using custom parameter grids. NMF showed the most coherent and interpretable topics.

## 9. Testing on Unseen Data

Though unsupervised, models were evaluated on unseen test data to verify generalization and consistency.

## Final Notes

This project aimed to explore the linguistic, structural, and thematic patterns in medical texts. The challenges of handling two datasets, working across multiple unsupervised tasks, and choosing appropriate evaluation metrics were significant. However, through systematic experimentation and visualization, meaningful insights were achieved and final models were selected for both tasks.
