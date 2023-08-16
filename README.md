# SC1015    Mini Project

## Project Overview

This project was done for NTU's SC1015 course (Introduction to Data Science & Artificial Intelligence) in AY21/22 S2. We used the Airbnb Amsterdam dataset from kaggle (linked in our notebook) and investigated how an Airbnb host could make the most of their property. 

## Contributors
- Lee Haoguang
- Lee Rou Yin
- Li Lin

## Problem Definition
**Main Problem**
- How does an airbnb host maximise their property?

**Sub-problems**
1. What is a reasonable rent for a particular listing?
2. Where is the ideal area for listings?
3. What factors affect the number of bookings?
4. What ratings would a particular listing get?

## Detailed Work
### Data Preparation
We cleaned the dataset by dropping irrelevant columns. After removing the '$' from the price column, we dropped rows with severe outliers in price (price per night >1000), as well as some categorical data with low counts (such as house type: castle). We then split the dataset into numeric and categorical dataframes for analysis. 

### 1. What is a reasonable rent for a particular listing?
We made use of 3 regression models:
- Linear Regression
- Random Forest Regression
- XGBoost

For each model, we trained and tested the model 10 times with different random train test splits and took the average explained variance of the 10 iterations to get a good estimate. We found that Random Forest Regression yielded the highest explained variance, followed by XGBoost and finally Linear Regression.

### 2. Where is the ideal area for listings?
Here we made use of the functions:
- Folium
- Groupby

We used Folium to plot a graph to visualise the location of listings in Amsterdam. We could get a general idea of how the listings were distributed, but not details. We then used the groupby function to group and sort the neighbourhoods by mean number of reviews and price of all listings in each neighbourhood. This gave us a good idea of which neighbourhoods were more popular with guests and which ones charged higher prices. 

### 3. What factors affect the number of bookings?
We made use of functions:
- Counter
- WordCloud

We initially use counter to count the number of listings that offer each different amentity. We believe that the host can include the most common ammenities in their Airbnb to remain competitive. Additionally, we added a WordCloud to analyse the textual reviews by past guests to see which words came up the most. This would give us an idea of what people sought in an Airbnb that caused them to choose it. 

### 4. What ratings would a particular listing get?
Similar to question 1, we made use of regression models, iterated 10 times. We found that explained variance was similar for the models used. 

## Conclusion
We want an airbnb host to be able to make the most of their property and ensure that their listings are successful. From our project, we have a few suggestions for them. 
1. Firstly, based on the characteristics of their property, they should be able to predict a typical price of a similar property and be able to price their property appropriately. 
2. Second, for a host looking to put up a listing in Amsterdam, some of the best areas to put up listings will be in the central area. These areas are the most popular and also fetch the highest prices. However there are also the most listings in these areas. If they wish to offer a listing in somewhere with less competition, they should choose somewhere with less listings but ranks relatively highly in popularity and price. They should avoid regions that rank very poorly in both price and number of reviews.
3. Thirdly, the location of the listing is extremely important to guests. To make sure their listing is popular, they should get properties that are near the city center and within walking distance to amenities. A good host is also important to guests. 
4. Finally, they will also be able to predict how high a rating they would get based on the characteristics of their property and possibly aim to improve it. 
