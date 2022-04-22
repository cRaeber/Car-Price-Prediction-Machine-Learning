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

## Plots

For the initial relationship evaluation a pair plot was used to help visualize any correlations between attributes. From this, I determined that a cars milage and year made had the strongest correlation to its price. 
![My Image](/images/pairPlot.png)


Below, is the scatter plot of points related to price and milage. As we can see, there appears to be a downward trend suggesting that as a vehicles miles go up, its price goes down.
![My Image](/images/milesPrice.png)
 
From the below line and bar charts showing the relationship to a car's year and its price we can see a very obvious upwards trend. However, there is an unexpected uptick in the cars from years 1980-1981. I am hypothesising that there are a number of highly valued classic cars from these years found in the dataset. 
![My Image](/images/yearPriceBar.png)
![My Image](/images/yearPrice.png)


The remaining graphs shown below are just for expirimintation. From them we can see that color, and make have very little impact on price and that the engine capacity has only a slight correlation of increased price with increased size. 
![My Image](/images/colorPrice.png)
![My Image](/images/makePrice.png)
![My Image](/images/enginePrice.png)
## Summary


