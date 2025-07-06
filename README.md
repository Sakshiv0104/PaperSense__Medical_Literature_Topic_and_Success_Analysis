# BDA_PART-B
Part B (Big Data Analysis)

# “Mapping Medical Research: 
 A Multi-Level Analysis of Methods, Topics, and Outcomes”

## Workflow Overview

### 1. Importing Libraries
I started by importing all the required libraries for data handling, visualization, and text analysis.

---

### 2. Reading and Transforming Both Datasets
- I loaded both the research paper dataset and the hospital dataset.
- For the research papers, I retained only 4 essential columns: `ID`, `OBJECTIVE_BACKGROUND`, `METHODS`, and `RESULTS_CONCLUSIONS`.
- For the hospital data, I combined all columns (excluding `Age Group` and `Gender`) into a single column called `Medical_Information`.
- I limited the dataset to the first 50,000 rows for manageable and efficient analysis.

---

### 3. EDA on Raw Data

- **Plot 1**: Most Frequent Terms in Research Papers  
- **Plot 2**: Count of Papers Containing Mathematical Terms / Formulas / Equations (analyzed by section)

---

### 4. Data Cleaning

I performed a series of cleaning steps to prepare the text data:

- Removed URLs  
- Removed mathematical equations and formulas (digits and math symbols)  
- Removed lone characters (e.g., `'n'`)  
- Removed extra spaces, newlines, and tabs  
- Converted all text to lowercase  
- Removed stopwords  
- Removed punctuations

---

### 5. Pattern Discovery and Visualization on Cleaned Data

#### Univariate Analysis

- **Plot 3**: Top 20 Dominant Research Goals Identified from Study Objectives  
- **Plot 4**: How Do Medical Papers Conclude?  
  I analyzed sentiment distribution using pretrained VADER sentiment classifier  
- **Plot 5**: How Diverse Are Medical Methods?  
  I used KMeans clustering on the `METHODS` section  
- **Plot 6**: Top Unigrams & Bigrams by Section  
  This gave a linguistic snapshot of each section

---

#### Bivariate Analysis

- **Plot 7**: Readability vs Length of Full Papers  
  I used the Flesch Reading Ease Score to explore the relationship between document length and readability

---

#### Multivariate Analysis

- **Plot 8**: Section-wise Linguistic Analysis of Medical Papers  
  I compared the following metrics across sections:  
  - Vocabulary Richness  
  - Flesch Reading Ease  
  - Gunning Fog Index

- **Plot 9**: Structural Coherence Across Research  
  I used TF-IDF vectors and cosine similarity to measure semantic alignment between sections

---

## Final Notes

This analysis helped me explore the structure, clarity, and complexity of medical research texts using NLP techniques.
