# DSCI 511 Project: Building Anime and K-Pop Datasets with Web Scraping and Writing A Kaggle File Downloader 

## About the Code Files

**kaggle_file_downloader:**  This code uses Kaggle's API to download specific datasets from Kaggle. As written, it currently downloads a csv of K-Pop data by Kaggle user _daffa shiddiq_. The kpop_artist_dictionary uses the output of this tool.
<br>
<br>
**kpop_artist_dictionary:** This code scrapes the K-Profile website (https://kprofiles.com/) using BeautifulSoup to get discography information for artists from the KPop csv that's downloaded by the kaggle_file_downloader script. It returns a dictionary of artists, all their albums, and the album track lists and release dates as a JSON file.
<br>
<br>
**anime_list:** This code scrapes the Anime Filler List website (https://www.animefillerlist.com/) using BeautifulSoup to make a table. The table documents the amount of filler and canon episodes for each series.<br>

## Applications
**Kaggle File Downloader** <br>
Use to download specifc files from Kaggle without accessing the website (aside from using it to locate the file you want). Good for team collaborations on projects using Kaggle data since team members can run this script to download the file. As written, the script will download a K-Pop CSV. 

**K-Pop data** <br>
Use to find new songs or albums by K-Pop artists (or groups) they may not be aware of. K-Pop fans could also filter and sort to compare the amount of songs and albums produced by that group. Data is formatted as a dictionary.

**Anime data**<br>
Users can use this data to find new shows to fit their viewing needs and availability. For example, if someone has limited free time for watching anime and is looking for a show that is not a large viewing committment (i.e., low episode count), he/she could use this data to find a series with a lower episode count. Users could also look at anime with longer episode counts to see if it has a high filler episode account, which would reduce the time committment (since the viewer could skip the filler episodes).

## Getting Started
**Required Python Packages** <br>
PIP install the following to your python evironment to use our files.

- requests
- from bs4 import BeautifulSoup
- re (regular expressions)

**kaggle_file_downloader**<br>
Complete the following to run this script.

1. Sign into your Kaggle account at https://www.kaggle.com/. If you do not have an account, create one.
2. While signed in, navigate to your Kaggle Account settings. Scroll down until you reach the API section. Click the button "Create New API Token". This will download a Kaggle API token as a .json file. NOTE: this file **must** be saved to your **downloads folder** for the script to work.
3. Run the script. It will download this KPop CSV file: https://www.kaggle.com/daffashiddiq/kpop-4th-gen-sales

**kpop_artist_dictionary** <br>
To run the K-Pop script, you need to download the K-Pop CSV file using the Kaggle File Downloader script because it uses this file to build the artist list for the K-Profile website scraping.

**anime_list** <br>
No other requirements to run. 

## Project Contributors
- Willie Hood & Jamia Mason: Anime data & Kaggle File Downloader 
- Dior Billups & Kelsey Fox: K-Pop data
