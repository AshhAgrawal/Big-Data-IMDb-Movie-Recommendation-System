# Big Data IMDb Movie Recommendation System

> A scalable, hybrid recommendation engine for IMDb movies using PySpark.

---

## Table of Contents

- [Project Overview](#project-overview)  
- [Features](#features)  
- [Technologies Used](#technologies-used)  
- [Dataset](#dataset)  
- [Project Structure](#project-structure)  
- [Prerequisites](#prerequisites)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Notebook Walkthrough](#notebook-walkthrough)  
- [Results & Evaluation](#results--evaluation)  
- [Future Work](#future-work)

---

## Project Overview

This is a big-data course project (CS-GY 6513) taught by Amit Patel in Fall 2024. The system implements a **hybrid recommendation engine** that combines:

- **Collaborative Filtering** (ALS) to leverage user–item interaction patterns  
- **Content-Based Filtering** using TF-IDF on movie metadata and cosine similarity  

It is designed to process large IMDb datasets and deliver personalized movie suggestions in real time, powered by PySpark for distributed computation.

---

## Features

- **Scalable** processing of millions of ratings and movie records  
- **Hybrid** approach for balanced recommendations  
- **Fast model training & inference** via Spark’s MLlib  
- **Modular notebook** allowing easy experimentation  
- **Clear evaluation** of top-K recommendation quality  

---

## Technologies Used

- **Apache Spark (PySpark)** for distributed data processing  
- **Spark MLlib** for ALS collaborative filtering  
- **scikit-learn** for TF-IDF vectorization and cosine similarity  
- **Pandas & NumPy** for auxiliary data manipulation  
- **Jupyter Notebook** for interactive development  
- **Python 3.x** programming language  

---

## Dataset

We use the publicly available IMDb datasets:

- **Ratings**: `ratings.csv`  
- **Movies metadata**: `movies.csv`, `genres.csv`, etc.  

Download all files from the [IMDb Datasets](https://datasets.imdbws.com/) site and place them in a local `data/` directory.

---

## Project Structure

    .
    ├── AAA_BDA1.ipynb         # Main Jupyter Notebook with end-to-end pipeline
    ├── requirements.txt       # Python dependencies
    └── README.md              # This file

---

## Prerequisites

- Python 3.7+  
- Java 8+ (for Spark)  
- Apache Spark 3.x  
- Git  

---

## Installation

1. **Clone the repository**  
    
        git clone https://github.com/AshhAgrawal/Big-Data-IMDb-Movie-Recommendation-System.git
        cd Big-Data-IMDb-Movie-Recommendation-System
    
2. **Create & activate a virtual environment**  
   
        python3 -m venv venv
        source venv/bin/activate
    
3. **Install dependencies**  
   
        pip install -r requirements.txt

---

## Usage

1. **Download IMDb datasets** into `data/` (see [Dataset](#dataset)).  
2. **Launch Jupyter Notebook**  
   
        jupyter notebook AAA_BDA1.ipynb
    
3. **Run all cells** in order:  
   - Data loading & preprocessing  
   - Building ALS model  
   - Computing TF-IDF features  
   - Generating hybrid recommendations  
   - Evaluating precision@K and recall@K  

4. **Experiment** with parameters such as `rank`, `regParam`, `maxIter`, and TF-IDF vector size to fine-tune performance.

---

## Notebook Walkthrough

The `AAA_BDA1.ipynb` notebook covers:

1. **Environment Setup** – Spark session initialization  
2. **Data Ingestion** – Loading CSVs into Spark DataFrames  
3. **Preprocessing** – Cleaning & splitting ratings  
4. **Model Training** – ALS collaborative filtering  
5. **Content Features** – TF-IDF on movie synopses/genres  
6. **Hybrid Logic** – Weighting & merging CF + CB scores  
7. **Evaluation** – Metrics for Top-K recommendations  

Refer to the notebook’s markdown cells for detailed explanations.

---

## Results & Evaluation

| Metric             | Value  |
|--------------------|--------|
| Precision@10       | 0.12   |
| Recall@10          | 0.08   |
| RMSE (ALS)         | 0.92   |

> *Example*: For user 123, top-5 recommendations include _The Shawshank Redemption_, _Forrest Gump_, …

Adjust the evaluation scripts in the notebook to generate your own metrics.

---

## Future Work

- Incorporate **user and item biases** in ALS  
- Use **word embeddings** (Word2Vec/BERT) instead of TF-IDF  
- Deploy model as a **REST API** for real-time serving  
- Add **UI** for interactive movie discovery  

---
