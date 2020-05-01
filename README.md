# AirBnB Amenities
### The impact of price and review score.

*[Emily Horton, Ilse Espino Barros, Thomas Bentler]*

*[Data Analytics, Berlin & 01-May-2020]*

## Content
- [Project Description](#project-description)
- [Questions & Hypotheses](#questions-hypotheses)
- [Dataset & Data Cleaning](#dataset-data-cleaning)
- [Database](#database)
- [Workflow](#workflow)
- [Organization](#organization)
- [Analysis](#analysis)
- [Conclusions](#conclusions)
- [Limitations](#limitations)
- [Links](#links)

## Project Description
AirBnB is known as a global disruptor in the hotel and lodging industry, with consumers valuing the unique and bespoke locations the platform offers. However, consumers still value the same, homey comforts such as full kitchens, wifi, and washer/dryers. The company places great value in quality host/guest reviews, and amenities could be an influencing factor in that review score. We decided to focus on this relationship between amenities, review score, and location.

## Questions & Hypotheses
- Does Airbnb follow the same model as hotels: more amenities and better reviews equal a  higher price?
- Do listings with a greater quantity of amenities have a higher price?
- Do listings with a greater quantity of amenities have higher review scores?
- Do certain amenities more strongly influence review scores than others?
- Are there more valuable amenities in certain countries/cities?

## Dataset & Data Cleaning
Although Airbnb’s API is exclusively available to partners, we were able to access historic data from 2017 through [Kaggle](https://www.kaggle.com/samyukthamurali/airbnb-ratings-dataset). The dataset has information from almost every country that Airbnb has a presence in, with over 1 million rows. 

We found the most valuable information in the data set was a column of amenities and the review score for each step in the stay (from booking to checkout). 

Even though most of the data was already clean, we encountered issues with numerous NULL value rows; discrepancies within the Street, City, and Neighborhood columns; and the structure of the amenities column. By the end of our cleaning, we had just under 400,000 rows to work it. See the Workflow section for how we addressed these challenges.


## Database
From our original dataset, we broke the information down into three dataframes. 
1. [Country-level data](https://drive.google.com/file/d/1AOpBARwohZFfC64L-gNkwsQuMaKtxEui/view?usp=sharing) - Because of the state of the data from different regions, we decided to first use a country level granularity. 
2. [US only data](https://drive.google.com/file/d/1FHxw-eR6Z2-_Jz778ukWdhvSid7oTQUY/view?usp=sharing)  - The US data was much more complete, which gave us the ability to look at different cities and states. 
3. [All locations with columns for each amenity and review score](https://drive.google.com/file/d/1GYfu0ZDxmnYGu5JM53SIn3ktGiXUzSeJ/view?usp=sharing) - This table allows us to compare the presence of each individual amenity with the review score and to use regression to predict the most important amenity. 


## Workflow
The following workflow was implemented:

1. Choosing the data set
2. Deciding on the focus for the project
    - After creating the mind map, we decided to explore the listings’ amenities.
3. Defining tasks to be done
    - Tasks were separated on [Trello](https://trello.com/b/EC0kcusx/module-2-board) in order to begin the data cleaning and analysis.
4. Data cleaning and wrangling
    - Deletion of rows with column Last Review Date as Null and as  NA
    - Deletion of rows with Reviews Score Rating as 0
    - Deletion of rows with Amenities as empty
    - Adjustment of Amenities column, splitting strings into lists
    - Creation of new column with quantity of amenities per listing
    - Verify data types
    - Creating final three Data Frames
5. [Analysis](#analysis)
6. [Conclusions](#conclusions)
7. Visualization


## Organization
In order to break the data set into questions, we used a [Miro](https://miro.com/welcomeonboard/AmPzXtQbyMq5ttWYdQmMxnK8IdizbCVX5lQK95cJnG96UEo8EtKUjotrIX85S7hM) board to create a mind map of ideas we could work on. After deciding on the questions to analyze, the different tasks and activities were set up on [Trello](https://trello.com/b/EC0kcusx/module-2-board).

This repository is divided by Data files and Notebook files.
**Notebooks**

Data Cleaning: Recommended Order
- [Data_Cleaning_1](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Data_Cleaning/Data_Cleaning_1.ipynb)
- [Data_Cleaning_2](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Data_Cleaning/Data_Cleaning_2.ipynb)
- [Data_Cleaning_3](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Data_Cleaning/Data_Cleaning_3.ipynb)
- [Data_Cleaning_3.2_Amenities_Table](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Data_Cleaning/Data_Cleaning_3.2_Amenities_Table.ipynb)

Analysis: Recommended Order
- [Amenity Count vs. Review Score](https://github.com/ilse-espino/visualizing_real_world_data/tree/master/notebooks/Analysis/Amenity_Count_vs_Review_Score)
    - [Amenity_Count_vs_Review_Score_Rating](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Analysis/Amenity_Count_vs_Review_Score/Amenity_Count_vs_Review_Score_Rating.ipynb)
    - [Amenity_Count_vs_Review_Score_Rating_2](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Analysis/Amenity_Count_vs_Review_Score/Amenity_Count_vs_Review_Score_Rating-2.ipynb)
- [Amenity Count vs. Price](https://github.com/ilse-espino/visualizing_real_world_data/tree/master/notebooks/Analysis/Amenity_Count_vs_Price)
    - [Amenity_Count_vs_Price](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Analysis/Amenity_Count_vs_Price/Amenity_Count_vs_Price.ipynb)
    - [Perfecting_Regression_Model](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Analysis/Amenity_Count_vs_Price/Perfecting_Regression_Model.ipynb)
- [Amenity_Breakdown](https://github.com/ilse-espino/visualizing_real_world_data/tree/master/notebooks/Analysis/Amenity_Breakdown)
    - [Top_Amenities](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Analysis/Amenity_Breakdown/Top_Amenities.ipynb)
    - [Top_Amenities_Per_Country](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Analysis/Amenity_Breakdown/Top_Amenities_Per_Country.ipynb)
- [USA](https://github.com/ilse-espino/visualizing_real_world_data/tree/master/notebooks/Analysis/USA)
    - [USA_EDA](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Analysis/USA/USA_EDA.ipynb)
    - [Top_Amenities_US](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Analysis/USA/Top_Amenities_US.ipynb)
    - [Amenities_Table_US](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Analysis/USA/Amenities_Table_US.ipynb)
    - [LA_Amenity_Count_vs_Popularity](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Analysis/USA/LA_Amenity_Count_vs_Popularity.ipynb)

Optional Notebooks:
- [Data_Cleaning_Extras_(Amenities_Table)](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Optional_Notebooks/Data_Cleaning_Extras_(Amenities_Table).ipynb)
- [Amenity_Count_Predictor](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Optional_Notebooks/Amenity_Count_Predictor.ipynb)
- [Amenity_Count_vs_Price_2](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Optional_Notebooks/Amenity_Count_vs_Price_2.ipynb)
- [US_Cities_DataframeDa](https://github.com/ilse-espino/visualizing_real_world_data/blob/master/notebooks/Optional_Notebooks/US_Cities_Dataframe.ipynb)

Since the data had large file sizes, we created a [Google Drive Folder](https://drive.google.com/drive/folders/1ssziRVpxfZZzppWxBJCF7bg-P9GbS0Po?usp=sharing) in which you may find all the csv and pickle files used for each step. In the Drive, you can also find our final presentation with the key findings.

## Analysis
**Amenity Count**

By looking at the descriptive statistics for amenity count, it was found out that the median was 15 amenities and that only 25% of the listings had more than 20 amenities, with the maximum at 87. When registering a new listing, AirBnB has an amenities checklist consisting of 13 expected amenities and 5 safety amenities. This correlates to the findings that at least 50% of the listings have 15 amenities, which may be those initially suggested by AirBnB.

**Amenity Count vs Review Score**

When plotting amenity count vs average review score, a positive correlation can be appreciated going from 0 to 30 amenities. Afterwards, the relationship becomes less clear. This indicates that after 30 amenities, the review scores do not necessarily increase. Looking at the descriptive statistics, we decided to limit our scope to listings with 30 amenities or less. This accounted for 97.5% of the original data and limited our outliers.

Although there seems to be a clear relationship between amenity count and average rating for up to 30 amenities, there is still a lot of variation between them, giving an R2 value of 0.24.

**Amenity Count vs Price**

In order to compare different countries, we normalized the prices by creating a new column that computed the individual listing price divided by the average price in each country. Afterwards, the number of amenities was plotted against the average normalized price for each amenity. This showed a positive trend, estimating that the higher the number of amenities, the higher was the increase in price. As stated before, this trend was mostly clear for 97.5% of the listings, which have less than or equal to 30 amenities, so a cut off was made for up to 30 amenities.

**Regression Models**

We tried two different models of regression - polynomial and simple linear with constants.
    1. Polynomial - We created up to a 5-factor polynomial regression; however, we decided that this model was overfit because we only have a sample. We then moved on to a more simple linear regression.
    2. Linear Regression with constants - We created a linear regression model that included a number of constants (Country Dummies, GDP, Tourism, Size of the listing, and Property/Room Type). We found that this was the best fit model - but after plotting the residuals, we found that we are either missing important independent variables or are encountering an interaction term. Therefore we could not use the coefficients or p-values for further analysis


## Conclusions
Our analysis shows there is probably not a strong relationship between the number of amenities and price or the number of amenities and review score. We decided there must be additional external factors, such as seasonality for price and individual experience for review score. 

Additionally, most listings have around 14 amenities, so if you plan on starting to host on Airbnb, 14 amenities should be more than enough to fit in with the average listings.


## Limitations
We believe that our original Kaggle data set was compiled through web scraping, based on the variation in column content - especially Street, City, and Neighborhood. Because of this, our data may not be completely accurate. Based on the Last Review Score column, we have also found that our data is from 2017.

## Links

- [Kaggle AirBnB Data](https://www.kaggle.com/samyukthamurali/airbnb-ratings-dataset)
- [Trello](https://trello.com/b/EC0kcusx/module-2-board)
- [Miro](https://miro.com/welcomeonboard/AmPzXtQbyMq5ttWYdQmMxnK8IdizbCVX5lQK95cJnG96UEo8EtKUjotrIX85S7hM)
- [Slides](https://docs.google.com/presentation/d/1BdT7BaYwwsZVphZvse5H8v5XI8XyRGIGhGo56wG0QTY/edit?usp=sharing)