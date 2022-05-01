# Machine-Learning-Final-Project-Raeber-Chris

For this dataset, I will attempt to predict the price of a car given:

- Make
- Model
- Year
- Transmission Type
  - Manual
  - Automatic
- Color
- Miles
- Fuel Type
  - Gasoline
  - Diesel
  - Electric
- Engine Capacity
  - Cylinder volume
- Body
  - SUV
  - Sedan
  - etc...
- Drivetrain
  - Four Wheel
  - Reer Wheel
  - Front Wheel
- Time it has been listed for sale

## Initial Data Analysis Plots

For the initial relationship evaluation a pair plot was used to help visualize any correlations between attributes. From this, I determined that a cars milage and year made had the strongest correlation to its price. 
![My Image](/images/pairPlot.png)


Below, is the scatter plot of points related to price and milage. As we can see, there appears to be a downward trend suggesting that as a vehicles miles go up, its price goes down.
![My Image](/images/milesPrice.png)
 
From the below line and bar charts showing the relationship to a car's year and its price we can see a very obvious upwards trend. However, there is an unexpected uptick in the cars from years 1980-1981. I am hypothesising that there are a number of highly valued classic cars from these years found in the dataset. 
![My Image](/images/yearPriceBar.png)
![My Image](/images/yearPrice.png)


The next three graphs shown below are just for expirimintation. From them we can see that color, and make have very little impact on price and that the engine capacity has only a slight correlation of increased price with increased size. 
![My Image](/images/colorPrice.png)
![My Image](/images/makePrice.png)
![My Image](/images/enginePrice.png)

The final graph shows the counts of each of the makes. For future analysis this will be switched to counts of the car models so that I an eliminate all models that have very small occurences in the data. This will help reduce the number of models which as it stands is at 520, all of which have string representations. 
![My Image](/images/makeCounts.png)

## Abstract
My plan going forward is to leverage the dataset found in this repository to attempt to predict the price of a car. From the findings of the initial project research (shown in the above graphs) I believe that there is a strong enough correlation between the input data and price to produce an accurate model. I hypothesize that milage and year of make will be the most important input features in this dataset. 

## Target Distributions
![My Image](/images/priceDistribution.png)
From the above graph we see the distribution of the car prices. As we can see, the vast majority of the cars in the dataset are less than $15,000

## NaN and String Values

- In this data set the only Nan values in this are for engine capacity, a metric that was found to have a mild correlation to price, these NaN values will be replaced with the median value so as to limit their impact
- Transmision type is label encoded as there are only two possible values.
- All other string values were one-hot encoded. This lead to a very large number of columns but lead to the most accurate models as there are no continuous string values in the dataset and I wanted to minimize the numerical impact that comes from label encoding. 

## Aggregation Functions
The creation of aggregate columns was performed prior to string conversions as many of the useful columns were dropped during one-hot encoding. The aggregate functions used for this data set are:
- The average price by make
- The average price by model
- The average price by year
- The standard deviation by make

## Comparison of Model Accuracy

- Linear Regression
  - Accuracy for Test Size: 10 : 86.8568
  - Accuracy for Test Size: 20 : 84.7785
  - Accuracy for Test Size: 35 : 84.5205
  - Accuracy for Test Size: 50 : 84.8112
  - Accuracy for Test Size: 65 : 83.657
  - Accuracy for Test Size: 80 : 83.3336
  - Accuracy for Test Size: 95 : 78.6692
![My Image](/images/LinearResiduals.png)
From the above Residuals Plot we can see two things. First, the model is much better at predicting the values of low priced cars. This is most likely because, as pointed out in the output distribution graph, the vast majority of data points in this data set are for cars priced below $15,000. Second, the model performs very poorly on cars worth between $20,000 and $30,000. Again this is likely because of availability of data points in this range. Another cause could be that cars in this range are "mid-tier" for this dataset and they likely have many similarities between both the more expensive and cheaper cars making it harder to predict in this range. 

- SGD Regression
  - Accuracy for Test Size: 10 : 84.1906
  - Accuracy for Test Size: 20 : 85.1506
  - Accuracy for Test Size: 35 : 84.4041
  - Accuracy for Test Size: 50 : 84.3622
  - Accuracy for Test Size: 65 : 83.5554
  - Accuracy for Test Size: 80 : 83.072
  - Accuracy for Test Size: 95 : 80.8419


![My Image](/images/AccuracyScores.png)
As can be seen from the above accuracy scores and graph. The Linear Regression model had a higher test accuracy for 5 out of 7 test sizes. 

![My Image](/images/Predictions.png)
From the above graph we can see how the logistic model is predicting on the test set. In a perfect model we would see all of the point aranged on a straight line indicating prediction = actual value. Unlike the linear model which performed worst on the "mid-tier" cars, this graph implies that the logistic model is worse at predicting "high-tier" expensive cars. This is shown by how spread out the datapoints are on the right side of the graph. 


## Conclusion 
All in all, these models both had very similar accuracies and are both viable options for this data set. However, the Linear Regression model performed slightly better so if I had to chose between the two I would go with that. 
