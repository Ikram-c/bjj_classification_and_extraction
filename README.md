# Bjj classification and Extraction (Sports Data Web scrape and Supervised ML classification)


## Overview of project

The aim of the project was to generate an automated system to analyze Brazilian Jiu-Jitsu (Bjj) data and make predictions about a player’s performance using supervised classification models. Data was scraped from a reputable source for Bjj (https://www.bjjheroes.com) which contains an online database of competitors and their competition performance. The notebook was designed to be used by someone who has very little/ no understanding of coding which is why a series of user inputs are given. If work on this project is continued it would be used to generate a GUI which can then be used as a computer program and eventually a mobile app.

## Libraries used

For the web scraping ***Selenium*** and ***bs4*** was used.
For Data frame creation and manipulation ***pandas*** and ***numpy*** were used.
The following ML models were used for classification (***Sklearn***):

-***Logistic Regression***

-***Support Vector Machine***

-***Random Forest Classifier***

-***KNN***

-***Naive bayes***

-***Decision Tree Classifier***

For assessing the accuracy of the models the following metrics were used (***Sklearn***):

-confusion matrix
- f1 score

## How to notebook works:

The first name and Last name is scraped from the fighter list table (https://www.bjjheroes.com/a-z-bjj-fighters-list) along with the hyperlink to the fighter’s page which is stored in a dictionary. 

![alt text](https://github.com/[Ikram-c]/[bjj_classification_and_extraction]/blob/[main]/sample of the initial bjj heroes website.jpg?raw=true)

Sample of fighter list table

A user input is given which asks for the fighter name and then uses a function to see if the fighter exists in the previously defined dictionary and then selenium goes into the fighter page to scrape the fight history database. The function returns whether the fighter search was successful and whether the scraped fight history database as a Pandas DataFrame, the generated database is also stored locally as a CSV. 

![alt text](https://github.com/[Ikram-c]/[bjj_classification_and_extraction]/blob/[main]/Fight history sample image.jpg?raw=true)

Sample of fight history

A user input is then given to run a basic data cleaner function which takes the csv created and drops nulls, for the sake of simplicity, all matches resulting in draws are also removed and common string errors found in the scraped data frame such as an incorrect weight are also modified. A user input is then given to save the cleaned data frame as a CSV which if selected yes, will run a function to save the cleaned copy.

Early analysis (EDA) is then done by providing a user input. If yes is inputted, the DataFrame is analyzed to get the fighter’s best submissions (way of winning) and the fighter’s most common ways of losing, this is outputted in a list.

The feature to be predicted is then selected via another user input, after which the relevant features are encoded using the ***LabelEncoder*** and the data is scaled using the ***StandardScaler***. A ***histogram*** is plot to visualize the effect of the scaler (before and after it has been run).

The machine learning models (stated in the libraries used) are then run with elbow plot optimisations (visually plot in notebook) being used on the KNN and Random Forest classifier models to get the optimum value for the K value and n neighbors value. The models are then assessed using the f1 score to identify which model is the best to use. 

A user input is given to choose what to use for predicting the fighter’s success rate e.g. if the feature selected was move, the user should now input which move they want to input to see if the fighter will have success with, if the feature they selected was weight, they should input the weight class they want the fighter to fight at to see if they have success. A function is then ran to see if the fighter is expected to have success with this variable and which model was used to predict it.

## Future work
Imports have been made to use other accuracy models as well such as the sklearn accuracy score and classification report. The machine learning models also need to be optimized further with hyperparameter tuning and more testing with other fighters and features. Eventually the draws would also need to be added back to get a more holistic view of a fighter’s performance. As stated in the overview, the project was aimed to be developed eventually into a running EXE and eventually a mobile app.


