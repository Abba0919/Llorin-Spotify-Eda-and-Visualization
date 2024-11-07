# Exploratory Data Analysis on Spotify 2023 Dataset

## Guideline
in this deliverable, you will make an exploratory data analysis on a dataset containing information about popular tracks on Most Streamed Spotify Songs 2023. This task aims to analyze, visualize, and interpret the data to extract meaningful insights.

## Introduction
In this project, we will conduct Exploratory Data Analysis (EDA) on a dataset containing Spotify's most streamed songs of 2023, available on Kaggle. This dataset includes critical features such as track popularity, streaming counts, music attributes like tempo and energy, and the release dates of the songs. Through Data analysis, we can explore what really drives a song to the top of the chart and revealing what the listeners wants to hear. 

## Importing Python Libarary 
before anything else, you need to import python tools such as pandas, matplot and seaborn

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```



## Overview of Dataset
- After importing the python library, you need to load the data using the `pd.read_csv()`.
```python
df = pd.read_csv('spotify-2023.csv', encoding='ISO-8859-1')
df
```
 - I used ISO-8859-1 to ensure that the characters in the csv file are properly interpreted and file of the spotify-2023 contains special characters like accented letters.

| | track_name |	artist(s)_name |	artist_count |	released_year |	released_month |	released_day |	in_spotify_playlists |	in_spotify_charts |	streams |	in_apple_playlists |	... |	bpm |	key |	mode |	danceability_% |	valence_% |	energy_% |	acousticness_% |	instrumentalness_% |	liveness_% |	speechiness_% |
| -- |------------|----------------|--------------|---------------|----------------|--------------|----------------------|-------------------|---------|--------------------|-----|-----|-----|------|----------------|-----------|----------|----------------|--------------------|------------|---------------|
| 0 | Seven (feat. Latto) (Explicit Ver.) |	Latto, Jung Kook |	2 |	2023 |	7 |	14 |	553 |	147 |	141381703 |	43 |	... |	125 |	B |	Major |	80 |	89 |	83 |	31 |	0 |	8 |	4 |
| 1 | LALA       | Myke Towers    | 1 |	2023 |	3 |	23 |	1474 |	48  |	133716286  |	48  |	... |	92  |	C# |	Major |	71 |	61 |	74 |	7 |	0 |	10 |	4 |
| 2	| vampire    |	Olivia Rodrigo |	1 |	2023 |	6 |	30 |	1397 |	113 |	140003974  |	94  |	... |	138 |	F  |	Major |	51 |	32 |	53 |	17 |	0 |	31 |	6 |
| 3	| Cruel Summer |	Taylor Swift |	1 |	2019 |	8 |	23 |	7858 |	100 |	800840817  |	116 |	... |	170 |	A  | Major	| 55 |	58 |	72 |	11 |	0 |	11 |	15 | 
| 4	| WHERE SHE GOES |	Bad Bunny  |	1 |	2023 |	5 |	18 |	3133 |	50  |	303236322  |	84  |	... |	144 |	A  |	Minor |	65 |	23 |	80 |	14 |	63 |	11 | 6 |
| ... | ...          | ...        | ... | ... | ... | ... | ... | ... | ... | ... |... |... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |
| 948 |	My Mind & Me | Selena Gomez | 1 | 2022 | 11 | 3 | 953 | 0 | 91473363 | 61 | ... | 144 | A | Major | 60 | 24 | 39 | 57 | 0 | 8 | 3 |
| 949 |	Bigger Than The Whole Sky |	Taylor Swift |	1 |	2022 |	10 |	21 |	1180 |	0 |	121871870 |	4 |	... |	166 |	F# |	Major |	42 |	7 |	24 |	83 |	1 |	12 |	6 |
| 950 |	A Veces (feat. Feid) |	Feid, Paulo Londra |	2 |	2022 |	11 |	3 |	573 |	0 |	73513683 |	2 |	... |	92 |	C# |	Major |	80 |	81 |	67 |	4 | 0 |	8 | 6 |
| 951 |	En La De Ella | Feid, Sech, Jhayco |	3 |	2022 |	10 |	20 |	1320 |	0 |	133895612 |	29 |	... |	97 |	C# |	Major |	82 |	67 |	77 |	8 |	0 |	12 |	5 |
| 952 |	Alone	Burna Boy |1 |	2022 |	11 |	4 |	782 |	2 |	96007391 |	27 |	... |	90 |	E	| Minor |	61 |	32 |	67 |	15 |	0 |	11 |	5 |


  - I used this code to know what I will input in the markdown for output.
```python
print(df.head().to_markdown())
```
    
- How many rows and columns does the dataset contain?
  - The dataset contains 953 rows × 24 columns
    
- What are the data types of each column? Are there any missing values?
  - To know the data types of each column we need to input:
```python
df.info()
```

  - Output:
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 953 entries, 0 to 952
Data columns (total 24 columns):

| # | Column | Non-Null Count | Dtype |
|---|--------|---------------|-------|
| 0 | track_name | 953 non-null | object |
| 2 | artist_count |          953 non-null |    int64 | 
| 3 | released_year |         953 non-null |    int64 | 
| 4 | released_month |        953 non-null |    int64 | 
| 5  | released_day |          953 non-null |    int64 | 
| 6  | in_spotify_playlists |  953 non-null |    int64 | 
| 7  | in_spotify_charts |     953 non-null |    int64 | 
| 8  | streams |               953 non-null |    object |
| 9  | in_apple_playlists |    953 non-null |   int64 | 
| 10 | in_apple_charts |       953 non-null |   int64 | 
| 11 | in_deezer_playlists |   953 non-null |   object |
| 12 | in_deezer_charts |      953 non-null |   int64 | 
| 13 | in_shazam_charts |      903 non-null |   object |
| 14 | bpm |                   953 non-null |   int64 | 
| 15 | key |                   858 non-null |   object |
| 16 | mode |                  953 non-null |    object |
| 17 | danceability_% |        953 non-null |    int64 | 
| 18 | valence_% |             953 non-null |   int64 | 
| 19 | energy_% |              953 non-null |    int64 | 
| 20 | acousticness_% |        953 non-null |    int64 | 
| 21 | instrumentalness_% |    953 non-null |    int64 | 
| 22 | liveness_% |            953 non-null |    int64 | 
| 23 | speechiness_% |         953 non-null |    int64 | 

dtypes: int64(17), object(7)

memory usage: 178.8+ KB

 - By using `df.info()` , you can know if there are any missing values. The key and in_shazam_charts has 858 and 903 non-null count while all of the column contains 953 non-null count. This means that these two contains misisng values. Also, by using this panda function, you can see the data type of the 24 columns that has been displayed.  
## Basic Descriptive Statistics
- What are the mean, median, and standard deviation of the streams column?
  
- What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?

## Top Performers
- Which track has the highest number of streams? Display the top 5 most streamed tracks.
```python
df.nlargest(5, 'streams')[['track_name', 'streams']]
```
- Output:

| | track_name | streams |
|--|-----------|---------|
| 55 | Blinding Lights |	3.703895e+09 |
| 179 | Shape of You |	3.562544e+09 |
| 86 | Someone You Loved | 2.887242e+09 |
| 620 | Dance Monkey |	2.864792e+09 |
| 41 | Sunflower - Spider-Man: Into the Spider-Verse |	2.808097e+09 |
This outputs the top 5 most streamed tracks, and the top 1 track is the Blinding Lights.



- Who are the top 5 most frequent artists based on the number of tracks in the dataset?
   - To know the top 5 mos frequent artist, you need to input:
```python
df['artist(s)_name'].value_counts().head(5).nlargest(5)
```
 - Output:
   
| artist(s)_name | |
|----------------|-|
| Taylor Swift | 34 |
| The Weeknd | 22 |
| Bad Bunny | 19 |
| SZA | 19 |
| Harry Styles | 17 |

Name: count, dtype: int64

  - This displaces the top 5 most frequent artists and the most frequent artist based on the number of tracks in Taylor Swift.
    
## Temporal Trends
- Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year.
- Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases?

## Genre and Music Characteristics
- Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most?
- Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?

## Platform Popularity
 - How do the numbers of tracks in spotify_playlists, spotify_charts, and apple_playlists compare? Which platform seems to favor the most popular tracks?
 
## Advanced Analysis
- Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)?
- Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts.
