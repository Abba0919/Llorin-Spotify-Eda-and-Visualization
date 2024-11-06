# Exploratory Data Analysis on Spotify 2023 Dataset

## Guideline
in this deliverable, you will make an exploratory data analysis on a dataset containing information about popular tracks on Most Streamed Spotify Songs 2023. ). This task aims to analyze, visualize, and interpret the data to extract meaningful insights.

## Introduction
In this project, we will conduct Exploratory Data Analysis (EDA) on a dataset containing Spotify's most streamed songs of 2023, available on Kaggle. This dataset includes critical features such as track popularity, streaming counts, music attributes like tempo and energy, and the release dates of the songs. Through Data analysis, we can explore what really drives a song to the top of the chart and revealing what the listeners wants to hear. 

## Importing Python Libarary 
before anything else, you need to import python tools such as pandas, matplot and seaborn

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

- After importing the python library, you need to load the data using the `pd.read_csv()`. 



## Overview of Dataset

How many rows and columns does the dataset contain?
What are the data types of each column? Are there any missing values?

## Basic Descriptive Statistics
What are the mean, median, and standard deviation of the streams column?
What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?

## Top Performers
Which track has the highest number of streams? Display the top 5 most streamed tracks.
Who are the top 5 most frequent artists based on the number of tracks in the dataset?

## Temporal Trends
Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year.
Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases?

## Genre and Music Characteristics
Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most?
Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?

## Platform Popularity
 How do the numbers of tracks in spotify_playlists, spotify_charts, and apple_playlists compare? Which platform seems to favor the most popular tracks?
 
## Advanced Analysis
Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)?
Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts.
