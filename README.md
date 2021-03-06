# Data Science Portfolio

> Projects developed as part of OptusU Data Science program.

## Table of Contents
* [Analysis of Cycling Data](#portfolio-1---analysis-of-cycling-data)
* [Sport Vouchers Program Analysis](#portfolio-2---sport-vouchers-program-analysis)
* [Mobile Customer Churn](#portfolio-3---mobile-customer-churn)
* [Airbnb New User Bookings](#airbnb-new-user-bookings)
* [What explains domestic violence rates in NSW?](#what-explains-domestic-violence-rates-in-NSW)
* [Contact](#contact)

## Analysis of Cycling Data

### Background
In this task we have analysed four files containing four cycling record that include GPS location data as well as some measurements related to cycling performance like heart rate and power etc. All the event took place in the same track by same rider. The goal is to perform some exploration and analysis of this data. Questions to explore with the data:

- What is the overall distance travelled for each of the rides? What are the average speeds etc. Provide a summary for each ride.
- Compare the range of speeds for each ride, are time trials faster than road races?
- Compare the speeds achieved in the two time trials (three years apart). As well as looking at the averages, can you see where in the ride one or the other is faster.
- From the elevation_gain field you can see whether the rider is climbing, descending or on the flat. Use this to calculate the average speeds in those three cases (climbing, flat or descending). Note that flat might not be zero gradient but might allow for slight climbs and falls.

### Methods
We have used Pandas descriptive statistics like mean, max etc. to analyse the race done on the given periods. The dataset is a time-lapse snapshot of the riding. As this is a time-lapse data, to smoothen the data, we have used rolling mean for a small window. Then we have used Matplotlib to visualize the speed, elevation data to compare the rider’s performance. When determining climbing or decent we have considered a little tolerance limit -0.2 <= elevation <= 0.2 is considered as flat elevation. The data have a measure of the number of rotations of the pedals per minute (cadence) and a measure of speed. Using these two variables we have derived a measure of development which would effectively tell us which gear the rider was using at the time. Using Matplotlib the evaluation, speed and development is visualized.

### Findings
An interesting insight is discovered the race done in 2016 speed was a little better than in 2019. But the rider’s gear usage skill has improved in 2019. This might indicate the rider’s fitness level hasn’t increased but the riding skill has improved.

## South Australia Sport Vouchers Program Analysis

### Background
This task we shall explore data from the Federal Government Sport Vouchers program - this is a program that provides up to two $100 vouchers for kids to participate in organised sport. Along with the sports voucher data we have also given with ABS SEIFA data by LGA which shows a few measures of Socioeconomic Advantage and Disadvantage for every Local Government Area. Using the data we have tried to answer following questions

- Describe the distribution of vouchers by: LGA, Sport - which regions/sports stand out?
- Are some sports more popular in different parts of the state?
- Are any electorates over/under represented in their use of vouchers?
- Is there a relationship between any of the SEIFA measures and voucher use in an LGA?

The dataset contains the sorts voucher utilization of different LGA from South Australia.

### Methods
At first the ABS SEIFA data is joined with the vouchers dataframe to create one master data frame containing both the voucher data and the SEIFA measures. With this dataframe using pandas powerful aggregation feature we have summarized the data in various dimension. The summarized data is visualized with Geopandas, matplotlib and seaborn to extract insight visually.

### Findings
Some interesting insight was extracted from the dataset. ONKAPARINGA, SALISBURY and TEA TREE GULLY are top 3 LGA by voucher utilization. On the other side COOBER PEDY, PETERBOROUGH and FLINDERS RANGES are bottom 3 LGA by voucher utilization. Interestingly Australian Rules, Netball and Football (Soccer) are top 3 sports across the state. Most of the high voucher utilization LGA from mid Socio-economic index (IRSAD). Most of the low Socio-economic index (IRSAD) LGA have very low voucher utilization. These LGA can be incentivize more to be more active. 

## Mobile Customer Churn

### Background
In this task a dataset of some Mobile Customer Churn data is provided to characterising customers who churn and building a simple predictive model to predict churn from available features. Primary goal of this project to find if there are any significant cluster exist in the data. Also build a predictive model to predict churn.

### Methods
As the dataset did not came with enough background information, we have first explored the data with Hierarchical Clustering. The dendrogram of a Hierarchical Clustering is an excellent tool when no prior knowledge available on the cluster. As per the dendrogram analysis we have determined that we could build 2-4 cluster on the data set. Using this knowledge, we have built a KMean cluster model on the dataset. There is no suitable method to visualize the cluster if there are more than 3 dimensions on the dataset. That why we need to determine the most importance 2 variables that can explain most of the variance of the data. We have used the Principle Component Analysis (PCA) to determine the variable that can explain most of the variance of the data. We have determined to use SERVICE_TENURE and MONTHLY_SPEND are the 2 main component and used these two variables to visualize the cluster. 
As this is a classification problem, we have used Logistic Regression model to predict the churn from the dataset. A confusion matrix of the model performance was generated to evaluate the model performance. 

### Findings
We could find some clear cluster and visually project the clusters with distinct feature of each cluster clearly visible. The predictive model performed moderately better with AUC score achieved 0.699.

## Airbnb New User Bookings
The data contains information of new users on Airbnb and country a new user will make their first booking. The task is to predict in which country a new user will make his or her firsting booking. By accurately predicting where a new user will book their first travel experience, Airbnb can share more personalised content with their community, decrease the average time to first booking, and better forecast demand. It is informed that all users are from the USA.

Where could be Airbnb user’s first booking destination?
- Business importance
- Solution Approach
- Machine learning : Multi-class classification problem

## What explains domestic violence rates in NSW?
Domestic violence (DV) is dark stain in modern society. DV can be defined as any form of mistreatment including physical, phycological, financial, sexual take place within domestic circumstances perpetrated by member of intimate relationship. Any member of household can be victim of DV, while women and children are most vulnerable to this crime. The World Health Origination(WHO) has described the violence against women is a global problem of public health which need immediate attention[1]. Australia is not Immune to this crime, especially NSW suffer with this crime heavily. Hance it is very important the understand the nature of this crime and identify the factors having most influence. In this project we shall try find these factors and try to prove following hypothesis by implementing a linear model.
- Null Hypothesis (H 0 ): There is no relationship between income, education and employment with DV.
- Alternative Hypothesis (H A ): There is strong correlation between income, education and employment with DV.


## Contact
Created by [@Masud Jubaier](mailto:jubaier@gmail.com) - feel free to contact me!
