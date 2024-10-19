# Academic Paper Ranking and Recommendation System

This project implements a system to help researchers find high-impact academic papers, specifically in the field of High Energy Physics (HEP), using advanced techniques like TF-IDF, NMF factorization, WordVectorizer, and PageRank.

## Table of Contents
- [Overview](#overview)
- [Datasets](#datasets)
- [Methodology](#methodology)
  - [Preprocessing](#preprocessing)
  - [Feature Engineering](#feature-engineering)
  - [Paper Recommendation System](#paper-recommendation-system)
  - [PageRank for Paper Ranking](#pagerank-for-paper-ranking)
- [Results](#results)
- [Future Improvements](#future-improvements)
- [Installation](#installation)
- [Usage](#usage)
- [Contributors](#contributors)
- [License](#license)

## Overview
The goal of this project is to create a recommendation and ranking system for academic papers using metadata provided by arXiv. With over 1.7 million STEM-related papers, this system aims to identify connections between papers and estimate their impact using various natural language processing (NLP) techniques.

## Datasets
- **Dataset 1:** Up-to-date arXiv metadata, including title, abstract, authors, and categories.
- **Dataset 2:** Older arXiv dataset that includes citation information, enabling us to rank papers by their impact based on citation counts.

Example data point:
{ "id": "0704.0001", "submitter": "Pavel Nadolsky", "authors": "C. Balázs, E. L. Berger, P. M. Nadolsky, C.-P. Yuan", "title": "Calculation of prompt diphoton production cross sections at Tevatron and LHC energies", "comments": "37 pages, 15 figures; published version", "journal-ref": "Phys.Rev.D76:013009,2007", "doi": "10.1103/PhysRevD.76.013009", "abstract": "...", "report-no": "ANL-HEP-PR-07-12", "categories": ["hep-ph"], "versions": ["v1", "v2"] }


## Methodology
### Preprocessing
Data cleaning was performed to handle sparsity and inconsistencies. Abstracts were preprocessed using tokenization, punctuation removal, and stop word filtering. Word frequency analysis helped us reduce the dataset dimensions.

### Feature Engineering
- **TF-IDF (Term Frequency - Inverse Document Frequency):** Used to create word vectors for papers.
- **NMF (Non-negative Matrix Factorization):** Applied to cluster similar papers based on topic.
- **WordVectorizer:** Utilized to identify relationships between paper abstracts and create clusters for recommendation purposes.

### Paper Recommendation System
A cosine similarity method was implemented using the processed abstract data to find and recommend papers related to a user’s query.

### PageRank for Paper Ranking
A modified PageRank algorithm was used to rank papers based on citation data. The system built a sparse matrix of papers and their citations, applying power iteration to calculate each paper's rank.

## Results
The results include:
- **Topic Clustering:** Grouping of top words and similar papers in High Energy Physics.
- **Recommendation System:** Query a paper title and find the most similar papers using cosine similarity.
- **PageRank:** A ranked list of the most impactful papers based on citation data.

## Future Improvements
- Incorporating more datasets, such as peer-reviewed journal articles from sources like Elsevier.
- Enhancing the recommendation system using more advanced neural network models.
- Improving handling of multi-word queries to offer more precise recommendations.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/academic-paper-ranking.git
2. Install required dependencies:
   pip install -r requirements.txt
3. Download the arXiv dataset:
   kaggle datasets download -d Cornell-University/arxiv
Usage
Data Preprocessing: Run the data_preprocessing.py script to clean and prepare the dataset.
Paper Recommendation: Use the recommendation_system.py to get paper recommendations based on a query.
PageRank Analysis: Run the pagerank_analysis.py script to rank papers by their impact.
