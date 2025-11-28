# Python -- Descriptive-Analytics-on-Netflix-Movie-Data-1990-1999-
This project explores movie data from the Netflix catalog, focusing specifically on the decade of the 1990s (1990–1999).
Using pandas for data manipulation and matplotlib for visualization, the goal is to identify duration trends and characteristics of movies released during this period.

## Dataset: netflix_data.csv
The dataset contains information about shows and movies available on Netflix.
Relevant columns include:

| Column       | Description                           |
|--------------|---------------------------------------|
| show_id      | Unique ID for each title              |
| type         | Type of content (Movie or TV Show)    |
| title        | Title of the content                  |
| director     | Director of the title                 |
| cast         | Cast of the show or movie             |
| country      | Country of origin                     |
| date_added   | Date the title was added to Netflix   |
| release_year | Year of the content’s release         |
| duration     | Duration of the content in minutes    |
| description  | Description of the content            |
| genre        | Genre of the title                    |

## Objectives

1. Identify the most frequent movie duration among movies released between 1990 and 1999.
2. Count the number of short action movies (duration under 90 minutes) released in the 1990s.

## Methodology

### 1. Filter movies released in the 1990s

```python

# Importing pandas and matplotlib
import pandas as pd
import matplotlib.pyplot as plt

# Read in the Netflix CSV as a DataFrame
netflix_df = pd.read_csv("netflix_data.csv")
type(netflix_df)

# Filter years 1990 & 2000
netflix_year90s = netflix_df[
    (netflix_df["release_year"] >= 1990) &
    (netflix_df["release_year"] < 2000)
]

#Find the most frequent movie duration
duration = int(netflix_year90s["duration"].mode()[0])

# Count short action movies (< 90 minutes)
short_movie_count = netflix_year90s[
    (netflix_year90s["duration"] < 90) &
    (netflix_year90s["genre"] == "Action")
].shape[0]

### Results:
Most frequent movie duration in the 1990s: 94 minutes
Number of short action movies released in the 1990s: 7
