# Militarized Interstate Confrontations (MICs) Analysis

This project analyzes New York Times articles (2015-2023) to identify and extract information about Militarized Interstate Confrontations (MICs), including dates, involved countries, and casualty numbers.


## Data Processing Pipeline

1. **Country Data Processing**:
   - Load and clean `states2016.csv`
   - Extract active countries (2015-2023)
   - Save to `EState.csv`

2. **Article Processing**:
   - Load NYT articles (2015-2023)
   - Clean text (lowercase, remove stopwords, lemmatize)
   - Classify articles as MIC-related using:
     - Regex patterns (bad results)
     - Zero-shot classification (facebook/bart-large-mnli)

3. **Information Extraction**:
   - Extract dates of military deaths (NER + regex)
   - Extract involved countries (NER + regex)
   - Extract casualty numbers (regex patterns)
   - QA extraction (distilbert-base-uncased-distilled-squad)

## Requirements

Python 3.8+ with packages listed in `requirements.txt`

## Usage

  1. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
    

## Results

  Final output (Final_data.csv) contains

  1. Article metadata (year, filename, content of Articles)

  2. Extracted dates of military deaths

  3. Involved countries

  4. Casualty numbers/estimates

