# Python -- Descriptive-Analytics-on-Netflix-Movie-Data-1990-1999-
This project explores movie data from the Netflix catalog, focusing specifically on the decade of the 1990s (1990–1999).
Using pandas for data manipulation and matplotlib for visualization, the goal is to identify duration trends and characteristics of movies released during this period.

Dataset: netflix_data.csv

The dataset contains information about shows and movies available on Netflix.
Relevant columns used in this project include:

Column	Description
show_id	Unique ID for each title
type	Type of content (Movie or TV Show)
title	Title of the content
director	Director of the title
cast	Main cast
country	Country of origin
date_added	Date the title was added to Netflix
release_year	Year of the content’s original release
duration	Duration in minutes
description	Description of the content
genre	Genre of the movie or show
Objectives

Identify the most frequent movie duration among movies released between 1990 and 1999.

Count the number of short action movies (defined as movies with a duration under 90 minutes) released in the 1990s.

Methodology
1. Filter movies released in the 1990s
netflix_year90s = netflix_df[
    (netflix_df["release_year"] >= 1990) &
    (netflix_df["release_year"] < 2000)
]

2. Find the most frequent movie duration
duration = int(netflix_year90s["duration"].mode()[0])

3. Count short action movies (< 90 minutes)
short_movie_count = netflix_year90s[
    (netflix_year90s["duration"] < 90) &
    (netflix_year90s["genre"] == "Action")
].shape[0]

Results

Most frequent movie duration in the 1990s: 94 minutes

Number of short action movies released in the 1990s: 7

Tools Used

Python

Pandas

Matplotlib

Jupyter Notebook / DataCamp Workspace

Conclusion

The analysis indicates that movies from the 1990s in the Netflix catalog most frequently run around 94 minutes.
Short action movies were relatively uncommon during this decade, with only seven titles meeting the criteria.
