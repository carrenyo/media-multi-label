# Films and TV Programmes Multi-Label Genre Datasets  

## Overview  

This repository contains two multi-label datasets:  
1. **`filmaffinity-film.csv`** – A dataset of **56,637 films** sourced from **Filmaffinity**.  
2. **`imdb-tv.csv`** – A dataset of **9,110 TV programmes** curated from **IMDb**.

Each dataset entry includes multiple genre labels, enabling tasks such as **multi-label classification, content-based recommendations, and genre prediction**.  



## Dataset Details  

### Data Sources  
- **Films:** Filmaffinity (`filmaffinity-film.csv`)  
- **TV Programmes:** IMDb (`imdb-tv.csv`)

### Total Instances  
- **Films:** 56,637  
- **TV Programmes:** 9,110  

### Genre Combinations  
- **Films:** 88 unique combinations from 8 genres  
- **TV Programmes:** 94 unique combinations from 20 genres

### Genre Labels

#### Films (8 genres):
- **Action**
- **Animation**
- **Comedy**
- **Drama**
- **Horror**
- **Kids**
- **Romance**
- **Thriller**

#### TV Programmes (20 genres):
- **Action**
- **Adventure**
- **Animation**
- **Biography**
- **Comedy**
- **Crime**
- **Documentary**
- **Drama**
- **Family**
- **Fantasy**
- **Game-Show**
- **History**
- **Music**
- **Mystery**
- **News**
- **Reality-TV**
- **Romance**
- **Sci-Fi**
- **Sport**
- **Talk-Show**

### Genre Standardisation  
- Genres were reordered **alphabetically** to maintain consistency.  
- **Rare combinations were removed:**  
  - For **Films**, single-instance genre combinations were excluded.  
  - For **TV Programmes**, combinations with fewer than **10 instances** were filtered out.  

## Features Included  

Each dataset entry contains the following fields:  

- **`id`**: Unique identifier for each entry.  
- **`title`**: Title of the film or TV programme.  
- **`genre`**: Multi-label genre assignment (e.g., Comedy, Drama).  
- **`director`**: Name(s) of the director(s).  
- **`cast`**: Main cast members featured in the media content.  
- **`synopsis`**: Brief summary or description of the content’s plot.  
- **`content_url`**: URL to the source website for content details.  
- **`poster_url`**: URL to the poster image.  

## Additional Meta-Model Datasets: Genre Prediction

Alongside the original datasets **`filmaffinity-film.csv`** and **`imdb-tv.csv`** datasets, this repository includes two additional datasets used to feed the meta-model, combining **CLIP** and **BERT** model predictions:

1. **`filmaffinity-film-metamodel.csv`** – Contains genre predictions and probabilities for films.
2. **`imdb-tv-metamodel.csv`** – Contains genre predictions and probabilities for TV programmes.

Each dataset includes the following additional features for genre prediction:

- **`pred_genre_CLIP`**: Genre predicted by the **CLIP** model based on image features (posters downloaded from **`poster_url`**).
- **`pred_genre_BERT`**: Genre predicted by the **BERT** model based on textual features (**`title`**, **`synopsis`**, **`director`**, and **`cast`**).
- **Genre Probabilities**:
  - **`Action_CLIP_prob`, `Animation_CLIP_prob`, `Comedy_CLIP_prob`, ...**: The **CLIP** model's probability scores for each genre for the corresponding media entry.
  - **`Action_BERT_prob`, `Animation_BERT_prob`, `Comedy_BERT_prob`, ...**: The **BERT** model's probability scores for each genre for the corresponding media entry.
- **Genre Predictions**:
  - **`Action_CLIP_pred`, `Animation_CLIP_pred`, `Comedy_CLIP_pred`, ...**: The **CLIP** model's genre prediction as binary (1) or non-prediction (0) for each genre.
  - **`Action_BERT_pred`, `Animation_BERT_pred`, `Comedy_BERT_pred`, ...**: The **BERT** model's genre prediction as binary (1) or non-prediction (0) for each genre.

Each dataset includes the original features (e.g., title, synopsis, director, cast, etc.) along with the predicted genres and probabilities from the **CLIP** and **BERT** models.

---

## Results for Analysis Datasets

All the results obtained from CLIP, BERT, BERT-CLIP, and MM models are included for further analysis in the repository:

1. **`filmaffinity-film-results-for-analysis.csv`** – Contains results for film genre predictions from multiple models.
2. **`imdb-tv-results-for-analysis.csv`** – Contains results for TV programme genre predictions from multiple models.

Each dataset includes the following additional features:

- **`pred_genre_BERT-CLIP`**: Predicted genre using a combined **BERT** and **CLIP** model.
- **`pred_genre_MM`**: Predicted genre using the **MM** model.
  
For each genre (e.g., Action, Animation, Comedy, Drama, Horror, Kids, Romance, Thriller), the dataset provides the predicted probabilities and classifications from the following models:

- **CLIP model**: `Action_CLIP_prob`, `Animation_CLIP_prob`, etc.
- **BERT model**: `Action_BERT_prob`, `Animation_BERT_prob`, etc.
- **BERT-CLIP model**: `Action_BERT-CLIP_prob`, `Animation_BERT-CLIP_prob`, etc.
- **MM model**: `Action_MM_prob`, `Animation_MM_prob`, etc.

Each entry also includes:

- **Title**, **director**, **cast**, **synopsis**
- **URLs** for film details and posters
- **Predicted genre labels** for each model (e.g., `pred_genre_CLIP`, `pred_genre_BERT`, etc.)
- **Genre probability values** (e.g., `Action_CLIP_prob`, `Drama_BERT_prob`, etc.)
- **Genre predictions** for each model (e.g., `Action_CLIP_pred`, `Comedy_BERT_pred`, etc.)

---



