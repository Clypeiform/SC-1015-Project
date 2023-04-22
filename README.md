# SC-1015-Project: AniFame Succesful Apps

Our Motivation:
- Mobile Games are currently increasing in popularity, experiencing a 3.5% increase in installments from November 2020 to October 2021 (SensorTower,2021)
- The industry experienced a 23.5% increase in revenue within the same period
- As the Mobile Gaming Industry is at a crossroads where it experiences incremental growth, we wished to observed the characteristics which went into a successful game


Dataset Used:
- We utilised the 17k Strategy Games dataset which was found on Kaggle: https://www.kaggle.com/datasets/tristan581/17k-apple-app-store-strategy-games
- The dataset included all games classified under the Strategy Genre within the Apple App Store

Overview of data cleaning:
- As the dataset itself contained certain variables which we found irrelevant to our project, we cleaned it by removing them, namely URL ; ID ; Subtitle ; Icon URL ; Description ; Size ; Primary Genre
- We created a new binary variable, which we determined whether an app was succesful
- The criteria for deciding whether an app was succesful was based on an app having a minimum of 4000 user ratings, and a minimum average user rating of 4
- The successful games were then extracted into a new dataframe

Overview of data preparation:
- We altered 3 variables, genre, languages, and Original Release Date & Current Version Release Date
- Genre Problem:
        - “Games” was included in all the rows
        - The variable is in a string format
        
        Fix:
        - Remove the word “Games,” at the start of the string
        - Split the string using “,” and Create a new column “GenresList” to store the genres in as a list
- Language Problem:
        - The variable is in a string format
        
        Fix:
        - Split the string using “,” and 
        - Create a new column “LanguagesList” to store the languages in as a list
- Original Release Date & Current Version Release Date Problem:
                                                      - The date is in string format
                                                      - The date uses “/” but Jupyter only recognised date by “-”
                                                      
                                                      Fix:
                                                      - Replace the “/” for “-”
                                                      - Change the date from string to date time
                                                      
Exploratory Data Analysis                                                      
                                 


