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

## Potential Use Cases  

These datasets are suitable for various **machine learning** and **data analysis** applications, including:  

- **Multi-label classification**: Predicting genres based on textual and visual features.  
- **Content-based recommendation**: Suggesting films or TV programmes based on genre similarities.  
- **Poster-based genre classification**: Using images to infer likely genres.  
- **Natural Language Processing (NLP) tasks**: Analysing synopses and metadata to improve content tagging.  
