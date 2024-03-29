# Quebec Wildfire Project
## Team members:
<br/> - [Christopher Mahadeo](https://github.com/cmahadeo)
<br/> - [Murat Uyar](https://github.com/murat1uyar)
<br/> - [Nihal Uyar](https://github.com/Nihalyurdakul)
<br /> - [Rohan Sarkar](https://github.com/SarkarRohan1)

## Project Description
The year 2023 is the season where the most area burned in Canada’s history. About 5% of entire forest are of Canada was burned. Even though the number of wildfires has decreased since 80s, the area burned in Canada has increased. Consequently, Quebec affected in the same way.
The plot below shows wildfire in Quebec between 2011 and 2021.
![numberoffiresperyear](https://github.com/Nihalyurdakul/Quebec-Wildfire/assets/136121004/64584ab5-d18a-4dc3-a7cd-0498954372bb) <br />
Additionally, the following plot shows the size of burned areas per year. <br />
![sizebyyear](https://github.com/Nihalyurdakul/Quebec-Wildfire/assets/136121004/d52493a8-1690-44c1-a91d-a1ed7967cdb7) <br />
Our project aims predicts forestfires by analysing weather data so that firefighters, local governments and local people can be prepared beforehand if there is a risk of forest fire.


There are two main distinctions in the cause of wildfires in Quebec: lightning and human. We prefer to focus on lightning caused fires because average size of a lightning caused fire is 48.5 times bigger than average size of a human caused fire although the number of human caused wildfires is 4 times bigger than lightning caused wildfires according to our dataset. Lightning caused fires pose far more danger to wildlife, humans and nature. 

## Data and Model Details

1) In the data preparation phase, weather data for Quebec is collected, consolidated, and augmented with Canadian wildfire data, focusing on lightning-caused wildfires between 2011 and 2021. Steps involve addressing duplicates, refining geographical boundaries, and associating each fire with the nearest weather station.
A 15-day temporal window is established for predictive modeling, and the dataset is refined by replicating rows for each fire, handling NaN values, and addressing missing values using tailored methods. 
The addition of a 'class' column distinguishes between fire and non-fire instances.
2) In the data refinement process, duplicates are eliminated, resulting in a structured format where rows represent original fire data or non-fire instances.
Further refinement includes addressing NaN values, particularly in columns indicative of snow and rain variables, by appropriately filling them with 0. 
The imputation strategy involves employing aggregation methods tailored to each variable, with mean aggregation for temperature-related features and pchip interpolation for max and min relative humidity. 
The resulting refined wildfire dataset is poised for predictive models.
3) In the data modeling process, the preliminary tests indicate the viability of decision tree, random forest, gradient boosting, logistic regression, k-nearest neighbors, support vector       machine, and na"ive bayes models. Subsequent cross-validation and hyperparameter tuning reveal excellent performance for all tuned models, as depicted in a table of accuracy.

   <img width="313" alt="accuracy_table" src="https://github.com/Nihalyurdakul/Quebec-Wildfire/assets/62392536/4e39983c-cb8c-4e91-8265-b6cfbe3933e9">

   The analysis identifies data limitations, primarily stemming from the non-linear nature of meta-features, such as recent atmospheric conditions and lightning storm occurrences. The          study uses aggregated weather data, emphasizing recent atmospheric conditions, and highlights the importance of a more robust dataset for improved predictions. Additionally, the             investigation into feature importance shows that total precipitation ranks as the most influential factor in all models, contradicting expectations based on the dataset's structure. 
   ![feature_importance](https://github.com/Nihalyurdakul/Quebec-Wildfire/assets/62392536/0665ac3e-8802-48dd-b7b5-5cc539beb3f3)

    The study underscores the promising capabilities of the selected models and encourages further research to refine predictions and address the complexities of wildfire forecasting.

## Dependencies
Running the code requires the following Python packages:
<br /> pandas, numpy, scipy, folium, matplotlib, seaborn, sklearn 

## Data Access

The weather data is publically available here: https://climatedata.ca/download/#station-download
<br />
The wildfire data is publically available here:
https://www.kaggle.com/datasets/ulasozdemir/wildfires-in-canada-19502021/data
<br />
Weather dataset and the wildfire dataset can be found here as two different .zip files. 
<br /> For notebooks 'Canada Wildifre Data Exploration' and 'Fire data with class 1' use datasets 'weather_df.csv', 'CANADA_WILDFIRES.csv', 
<br /> For the notebook 'Fire data with class 0' use datasets 'weather_df.csv', 'merged_df.csv',
<br /> For the notebook 'haversinedistance' use datasets 'climatetotalcoord1.csv', 'canadawildfiresupdated1_2011to2021.csv',
<br /> For the notebook 'wildfire_modeling' use dataset 'fire_0_df.csv', 'fire_1_df.csv'.
## Future Work

We have 2 future works:
<br />
1) We want to develop an app like an alert system that analyses weather data.
2) We want to predict human-caused wildfires in Quebec using weather and infrastructure data.
