---
title:       "The Most Famous Musicians You've Never Heard Of"
date:        2022-12-04
author:      Sarah Helmbrecht and JT McDermott
image:       "/img/post/DataScienceFinal/Musical-map.png"
slug:        datasciencefinal
draft: false
---

# The Most Famous Musicians You've Never Heard Of  
by Sarah Helmbrecht and JT McDermott  

## **I. Introduction**  
With the advent of music streaming services such as Spotify, Apple Music, and others, it has never been easier to discover new music and artists than it is today. Despite the overall trend towards globalization and unprecedented access to historic catalogs, music tastes are still largely stratified by demographics. This inspired our question: **who are the most famous artists and bands that we have never heard of?**  

#### **An Example: Cultural Disparities**
Do you recognize the person in this artist? If you aren't from India, probably not. This is King, one of the most popular artists in India, gaining more than 17 million streams this week alone. He's one of many examples of a popular artist that is relatively unknown outside of their primary target audience, in this case based on nationality and language.  
![King](/img/post/DataScienceFinal/King.jpeg)  

#### **Context**  
To understand our approach to answering this question, it helps to understand the perspective of us, the authors. We are both Gen-Z college students that were raised in the United States and primarily speak English.  

The main factors that might hide an otherwise popular artist from us are language, geography, time, and our own personal preferences. Language and geography are simple to understand; people are generally unlikely to be exposed to media in a language they don't speak from a foreign country. This is increasingly changing with the advent of the international stars like Bad Bunny and others, but there are still many artists hidden from the rest of the world behind cultural barriers.  

#### **Motivation**  
The initial motivation for this study was pure curiosity, stemming from a desire to better understand the world and the people who live in it. There are practical motivations as well, namely:  

1. Identifying potential partners for advertisers  
2. Understanding global trends in media and entertainment  

Celebrity endorsements continue to be a major tool for advertisers, and can dramatically improve the ethos of a company when trying to penetrate a new market. Knowledge of famous musicians and particularly where and why they are famous is important for a successful partnership. For creators and producers of music, understanding trends and expanding horizons invites new influences, new ideas, and ultimately a better end product.  

#### **Our Model**  
In our exploration, we decided use our data to relate international trends in musician popularity to understand domestic trends. Using streaming data from dozens of countries, our model captures which countries are the best predictors of an artist's fame among US Millenials.  

#II. Our Data  
The rise of the internet and ubiquity of streaming services has created vast amounts of data about music habits. For our analysis, we focused on data that relates demographic factors to listening patterns. Our data comes from three main sources:  


*   [Spotify](https://kworb.net/spotify/) (via Kworb) - data of top 200 streamed artistis in countries around the world  
*   [YouGov](https://today.yougov.com/ratings/entertainment/popularity/all-time-music-artists/millennials) - polling of Millenials regarding their familiarity with 200 popular artists  
* [Acclaimed Music](http://www.acclaimedmusic.net/) - Collection of top 1000 artists of all time and decade-by-decade data of their releases  

The importation of this data was done primarily with webscraping. We explain in more detail the unique challenges each data set presented below.  

# **III. ETL & EDA**  
'''{python}  
#Mount Google Drive and move into correct directory  
from google.colab import drive  
drive.mount('/content/drive')  
%cd /content/drive/MyDrive/cmps3160  
'''

#### **Tools for Analysis**  

This section will keep track of the tools we will use for our analysis, namely imported Python libraries.   

'''{python}
#This cell imports libraries for analysis  

import pandas as pd  
from bs4 import BeautifulSoup  
import numpy as np  
import matplotlib.pyplot as plt  
import requests  
import re  
'''

### **YouGov Music Artists Poll**  

The following section will use a national poll to identify what percentage of American millenials have heard of certain musical artists.  

The dataset, sourced from [YouGov](https://today.yougov.com/ratings/entertainment/fame/contemporary-music-artists/millennials), ranks artists by the percentage of people polled (born from 1949 to 1999) who have heard of them, as of 2022. This website is particularly difficult to scrape because it has a "Load More" button and does not store the data in tabular format. We typed the data into an Excel spreadsheet instead of scraping it.  
