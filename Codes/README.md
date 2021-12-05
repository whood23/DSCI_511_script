# **Function Descriptions**

### **kaggle_file_downloader.ipynb**

*Description: This code uses Kaggle's API to download specific datasets from Kaggle. As written, it currently downloads a csv of K-Pop data by Kaggle user _daffa shiddiq_. The kpop_artist_dictionary uses the output of this tool.*

#### Functions Used

* downloadpathlib()
  * *Uses os, sys, and subprocess to call a system command to download pathlib using pip install.*
* downloadkaggle()
  * *Uses os, sys, subprocess to call a system comand to download kaggle using pip install.*
* createfile()
  * *Uses shutil, os, sys, and pathlib to check if the kaggle token exists within the user downloads folder if this arguement passes it then checks if the user has the appropiate kaggle folder under the user directory. If the arguement passes the kaggle token is relocated to that folder for use with the kaggle package; if not the path is created then the token is relocated.*
* renamefile()
  * *This renames the downloaded dataset to a more friendly file name.*

#### Notes

*The script will be processed via the kaggle api. For use with other kaggle files simply fill line 53 where it says api.dataset_download_file with the appropiate information. For more details check kaggle API notes. On line  58 and 59 you can change the name of the file to whatever dataset you are using.*

### **kpop_artist_dictionary**

*Description: This code scrapes the K-Profile website (https://kprofiles.com/) using BeautifulSoup to get discography information for artists from the KPop csv that's downloaded by the kaggle_file_downloader script. It returns a dictionary of artists, all their albums, and the album track lists and release dates as a JSON file.

#### Functions Used
* load_kaggle_csv_data()
  * *Uses csv to open & load Kaggle Kpop CSV file contents as a list.*
* get_kpop_artist_list()
  * *Generates a list of kpop artists (from the Kaggle CSV file) to use for other functions.*
* slugify_kpop_artist_list()
  * *Formats artist names for use in URLs for KProfile site web scraping in other functions. Replaces space characters with hyphens.*
* get_album_content()
  * *Uses BeautifulSoup and requests to get webpage content for artist web pages from KProfile site.*
* get_album_title_content()
  * *Gets albums titles for all Kpop artists from Kprofile webpage content.*
* get_album_titles()*
  * *Creates a list of album titles for the Kpop artist (from the webscraping).*
* get_release_dates_content()
  * *Uses regex and unicodedata to get release dates from artist discograhy page (removes 'release date' and only returns date)*
* get_loona_release_dates_content()
  * *Reduces album release dates to a single release dates since Loona has two release dates for two albums (digital and physical releases).*
* clean_release_dates()
  * *Uses regex to clean release date formatting, removing letters from dates (e.g. 2nd, 1st, 3rd, 24th).*
* format_release_dates()
  * *Uses dateutil and datetime to return a list of ablum release dates in the MM/DD/YYYY format ('%m/%d/$Y') instead of 'Month, day, year'.*
* get_album_release_dates()
  * *Given a Kpop group name, this function returns a list of album release dates, formatted as MM/DD/YYYY, for each album.*
* get_album_tracks_if_ordered()
  * *Uses BeautifulSoup to get a list of album tracks for each album for web pages with ordered list formatting and consistent ptags.*
* get_album_tracks_if_####()*
  * *Uses BeautifulSoup and regex to get a list of album tracks for artist pages that have unqiue formatting issues.*
* clean_release_dates()
  * *Uses regex to clean release date formatting, removing letters from dates (e.g. 2nd, 1st, 3rd, 24th).*
* get_album_tracks():
  * *Returns a list of album tracks for each kpop artist by applying the other album track functions.*
* make_discography()
  * *Creates a dictionary for a single artist. Key is artist name and values are release date and a list of album tracks*
* get_artist_dict_from_csv()*
  * *Uses Kpop CSV file name to generate artist list & returns artist dictionary by webscraping artist names from KProfile site. Applies earlier functions*

*(The #### in this function is a placeholder for the various artist names. It stands in for ateez, treasure, or verivery. Ex. get_album_tracks_if_treasure)

#### Notes

*The first cell uses functions to load the CSV file from the Kaggle Download Tool and generate a list of artist names for web scraping the K-Profile website. The second cell contains all the functions that get album content & titles by scraping the K-Profile website with BeautifulSoup. The third cell uses the release date functions to clean and build a list of release dates. The fourth cell gets the album tracks, applying unique functions for specific artists web pages (since not all pages were formatted & coded the same way). The fifth cell defines the function that makes the discorgraphy dictionary for a single artist, which is then used in the sixth cell to make an artist dictionary of all the artsits from the CSV file. Finally, the seventh cell saves this artist dictionary as a JSON file. For more info on functions, see wikis for packages.*

### **anime_list.ipynb**

*Description: This code scrapes the Anime Filler List website (https://www.animefillerlist.com/) using BeautifulSoup to make a table. The table documents the amount of filler and canon episodes for each series.*

#### Functions Used

* extend_dataframe()
  * *Used to add the correct columns to the original dataframe.*
* data_shaper()
  * *Used to append the web scraped data to the original dataframe.*
* show_filter()
  * Used to filter through the different attributes on the webpage.
* duplicate_removal()
  * *Used to remove duplicate episodes from the filler and mixed episode counts.*
* storage_checker()
  * *This is used to back the logic in data_shaper function. It ensures no episodes were counted twice in the storages and adds N/A to any storage with no entries.*
* show_####_filter()*
  * *Used to sort through attributes in the webpages.*

*(The #### in this function are just a placeholder for the various filters, it can represent manga, anime, mixed, or filler. Ex. show_manga_filter)

#### Notes

*The second cell is used to run the initial portions for the code. In this cell requests beautiful soup and pandas are used to scrape the episode names and information links from the page and create a dataframe housing all the info. All of the functions used for the second portion of the script are found in cell 3, and execution of the second portion of the script is preformed in cell 4. final_anime_df will contain the final dataframe for further work. It take the initial dataframe created in cell 2 of the jupyter notebook as an input. For more information on functions check out the wiki pages for beautifulsoup4, requests, regex for python, and pandas.*
