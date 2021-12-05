# Function Descriptions

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
