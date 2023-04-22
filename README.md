# SC-1015-Project: AniFame Succesful Apps

## Our Motivation:
- Mobile Games are currently increasing in popularity, experiencing a 3.5% increase in installments from November 2020 to October 2021 (SensorTower,2021)
- The industry experienced a 23.5% increase in revenue within the same period
- As the Mobile Gaming Industry is at a crossroads where it experiences incremental growth, we wished to observed the characteristics which went into a successful game


## Dataset Used:
- We utilised the 17k Strategy Games dataset which was found on Kaggle: https://www.kaggle.com/datasets/tristan581/17k-apple-app-store-strategy-games
- The dataset included all games classified under the Strategy Genre within the Apple App Store

## Overview of data cleaning:
- As the dataset itself contained certain variables which we found irrelevant to our project, we cleaned it by removing them, namely URL ; ID ; Subtitle ; Icon URL ; Description ; Size ; Primary Genre
- We created a new binary variable, which we determined whether an app was succesful
- The criteria for deciding whether an app was succesful was based on an app having a minimum of 4000 user ratings, and a minimum average user rating of 4
- The successful games were then extracted into a new dataframe

## Overview of data preparation:
- We altered 3 variables, genre, languages, and Original Release Date & Current Version Release Date
### - Genre Problem:
        - “Games” was included in all the rows
        - The variable is in a string format
        
        Fix:
        - Remove the word “Games,” at the start of the string
        - Split the string using “,” and Create a new column “GenresList” to store the genres in as a list
### - Language Problem:
        - The variable is in a string format
        
        Fix:
        - Split the string using “,” and 
        - Create a new column “LanguagesList” to store the languages in as a list
### - Original Release Date & Current Version Release Date Problem:
        - The date is in string format
        - The date uses “/” but Jupyter only recognised date by “-”
                                                      
         Fix:
        - Replace the “/” for “-”
        - Change the date from string to date time
                                                      
## Exploratory Data Analysis 
### Distrubution:
#### Genre Distrbution:
Popular Genres: 
Entertainment games, Simulation games, and Action

Unpopular Genres: 
Business, Trivia, Reference, Books, Word, Casino
#### Language Distrubution
Popular Language: 
English & Chinese(ZH)
### Genre Trend:
Role-playing has an upward trend

Although on a declining trend, many Entertainment, Action, and Simulation genre of games are still released.
### Comparison utilising User Rating Count
#### Against Average User Rating Count Based on Genres
-  The genres Action and Entertainment seems to have games with high user rating count with relatively high user rating of 4.5 .
- Games with Simulation genre also holds high average user rating but has a lower user count as compared to the other 2 genres mentioned
#### Against Price
- Majority of "successful" games are free 
- Games that are free or have a price of 2.99 generally have high user count
- Looking at the median, Games with the price 99 cents has a higher user rating count compared to free games
- Games above the price of 4.99 seems to have lesser “successful” games and have a lower user rating count
#### Against Age Rating
- The number of games with the age rating 4, 9, and 12 are quite similar to each other 
- Games with the age rating 17+ although having lesser games, has the highest median of user count

### Comparison between Free and Paid Games
#### Utilising Age Rating
- For both price types, not many games have the age rating of 17+
- Games with 9+ age rating have a higher user count
- Free games with the age rating of 4+ and 9+ tend to have a higher user rating count
#### Utilising User Rating Count and Add-ons
- Both free and paid games within the “successful” game dataset all have add-ons to their game
- This suggest that games with add-ons are more likely to succeed
#### Utilising User Rating Count and Average User Rating
- Both free and paid games within the “successful” game dataset all have add-ons to their game
- This suggest that games with add-ons are more likely to succeed

## Model Training
### Linear Regression
- For linear regression, we tried to see the correlation between the price of the game and average user rating
- R-square indicated that the strength of the correlation between the two variables are not strong. So from there we decided to try another method of analysis
### Decision Tree
- The existing decision tree is shown to be highly accurate, because "User Rating Count" is utilised as a predictor. As "User Rating Count" was initially one of the conditions used to determine whether a game is considered to be successful
- As the majority of the variables in the dataset with correlations with a game's success were categorical, we were ultimately only able to utilise 2 predictors in this decision tree
### Random Forest
- To use random forest as part of our analysis, we have to separate the genre and age rating into binary variable
- In order to do that, we have to perform one hot encoding and dropped the original variable of genre and age rating as seen in the picture
- After this we performed the random forest and got an accuracy of 99.39 percent
- The statistics here include precision, recall and f1_score 
- For precision, it is the probability of predicting the positive correctly while recall is the true positive rate
- F1_score is takes into account both precision and recall, with more weight assigned to the lower value.

## Key Insights
### Prediction of Success
- There existed clear trends as to the factors which influenced success 
- However these factors were categorical
- We were thus limited in terms of what we could utilise in linear regression and decision trees
### Characteristics of successful games
- A large proportion of “successful” games were part of the entertainment genre
- The vast majority offered language support for English and Mandarin
- Frequency of developers who produced “successful” games was largely evenly distributed
- A large portion of games which were considered “successful” were free, a total of 438/508
- Age Rating had little influence on a games success

## Contributions:
Data Cleaning and preparation: Joy
EDA & Visualization: Joy & Olery
Regression: Joelle
Decision Tree: Olery
Random Forest: Joelle
GitHub ReadMe: Olery


## References
https://www.kaggle.com/datasets/tristan581/17k-apple-app-store-strategy-games
https://sensortower.com/blog/app-revenue-and-downloads-2021








                                 


