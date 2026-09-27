# World News Topic Analysis: Automated Categorization using LDA

## Project Overview

This project applies data science methodologies to analyze world news articles, aiming to automatically discover latent thematic structures. The implementation follows a systematic approach encompassing data collection, preprocessing, exploratory analysis, modeling, and interpretation.

The project demonstrates the practical application of web scraping, text mining, and topic modeling techniques, providing a framework for automated news categorization and trend analysis.

**Course:** Introduction to Data Science Final-Term Project  
**Institution:** American International University-Bangladesh (AIUB)  
**Semester:** Fall 2025-2026  

## Team Members

| ID | Name | Contribution Details |
| :--- | :--- | :--- |
| 22-47146-1 | MST AFRIN BINTE AMIN | Data Collection + Dataset Setup (Scraping & Storage) |
| 22-47597-2 | MONJILA KABIR MEGH | Data Cleaning + Text Preprocessing |
| 22-47155-1 | MD ABDULLAH AL NOMAN | Modeling + Visualization + Result Interpretation |

## Dataset Description

The dataset consists of 15 world news articles manually curated to represent diverse topics. Each article includes:

*   **Article_ID:** Unique identifier (1-15)
*   **Title:** Article headline
*   **Category:** Automatically assigned based on URL/section
*   **Article_Text:** Full article content scraped from web
*   **URL:** Source link from The Daily Star
*   **Cleaned_Text:** Preprocessed text (lowercase, special characters removed)
*   **Word_Count:** Number of words after cleaning

**Dataset Statistics:**
*   Total articles: 15
*   Categories: 5 distinct categories
*   Average article length: Approximately 23 words after cleaning

## Research Objectives

*   To collect real-world unstructured textual data from online news articles using web scraping techniques.
*   To transform raw textual data into a structured format through systematic text preprocessing and cleaning.
*   To analyze the cleaned text data using text mining methods in order to understand word usage and patterns.
*   To apply Latent Dirichlet Allocation (LDA) for topic modeling to identify hidden thematic structures within the article corpus.
*   To extract and interpret dominant topics and their most representative terms.
*   To evaluate whether topic modeling can effectively summarize and organize large collections of unstructured text.

## Methodology

### 1. Data Collection (Web Scraping)
The project implements a web scraping function for **The Daily Star**. It attempts to fetch articles from various sections including News, Business, Sports, Entertainment, and Lifestyle. In case of scraping failures, a fallback sample dataset is utilized to ensure analysis continuity.

### 2. Data Preprocessing
Text cleaning is performed to prepare data for modeling. The process includes:
*   Converting text to lowercase.
*   Removing special characters, numbers, and punctuation.
*   Removing English stopwords.
*   Stripping whitespace.

### 3. Exploratory Data Analysis (EDA)
EDA is conducted to understand dataset characteristics, including category distribution and word count analysis. Visualizations include bar charts for category distribution and histograms for word counts.

### 4. Modeling (LDA)
Latent Dirichlet Allocation (LDA) is employed for topic modeling with 5 topics (k=5). The model is trained on a Document-Term Matrix (DTM) created from the cleaned text.

## Visualizations

### 1. Exploratory Data Analysis
The initial analysis shows the distribution of articles across categories and the word count distribution.

![Distribution of Articles by Category](images/category_dist.png)
![Distribution of Raw Article Word Counts](images/raw_word_count.png)
![Distribution of Cleaned Article Word Counts](images/cleaned_word_count.png)

### 2. Topic Modeling Results
The LDA model identified distinct topics within the news corpus. Below are the top terms for each topic and the overall topic distribution.

![Top Terms in Each Topic](images/top_terms.png)
![Distribution of Articles Across Topics](images/topic_dist.png)

### 3. Word Clouds and Heatmaps
Word clouds highlight the most frequent terms, while heatmaps show the probability distribution of topics across individual documents.

![Word Cloud: Most Frequent Terms](images/wordcloud.png)
![Topic Proportions per Article](images/heatmap.png)
![Topic 1 Word Cloud](images/topic1_wordcloud.png)

## Key Findings

Based on the LDA model and analysis of the news corpus:

1.  **Topic 1:** Global, effectiveness, trials, clinical, renewable energy.
2.  **Topic 2:** International agreements, economic, technology, leaders.
3.  **Topic 3:** Energy, implementing, projects, renewable, solar, funding.
4.  **Topic 4:** Government, companies, growth, solar projects.
5.  **Topic 5:** Economic, world, reduce, funding, increased projects.

**Topic Distribution:**
*   Topic 5: 33.3% of articles
*   Topic 2: 20% of articles
*   Topic 4: 20% of articles
*   Topic 1: 13.3% of articles
*   Topic 3: 13.3% of articles

The most prevalent topics relate to **Economic/International** news and **Environmental/Energy** news.

## Requirements

To run this analysis, you need R installed along with the following packages:

```r
install.packages(c("tm", "topicmodels", "tidytext", "dplyr", 
                   "ggplot2", "wordcloud", "RColorBrewer", "stringr", 
                   "rvest", "httr", "xml2", "purrr"))
