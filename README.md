

# Fine Tuning Used Car Lot Inventory

## Objectives

The objective of this investigation was two fold.
  
1. Extract useful insights from the dataset of car sales to assist with inventory decisions.
2. Create a model to predict a car's sale price

## Data Preparation

Several decisions were made in an attempt to improve the peformance of our predictive model. All of these assumptions may be revisited based on client preferences.

1. 'Region' was removed because the data field contained semantically different values : states, counties, town, etc. More can be done to clean the data, but the 'State' feature is likely sufficient for our purposes.
2. Sales prices less than $500 and more than $80,000 were dropped to prevent extreme outliers from having an outsized impact on our model.
3. Sales with a Title Status of 'salvage', or 'parts only' were dropped under the assumption a used car lot would not sell these. Likewise, sales of cars with a Condition of 'salvage' were also dropped.
4. A new feature 'Miles Driven Per Year' was created to penalize new cars with many miles driven and reward older cars with fewer miles.
5. The dataset contained very few luxury car sales relative to less expensive cars. More data would improve the predictive performance of our model for luxury car brands like ferrari, aston-martin, land rover, etc.

## Data Insights

### Top features that tended to reduce the sales price

1. The age of a car was the biggest determining factor in reduced sale price. After 35 years, however, the avg sale price rises and remains fairly high relative to cars aged 20-35 years.
2. odometer values also had a large negative impact on price. For every 100K miles, there appears to be between a 15K-20K drop in the highest observed sale price.
3. fwd (front wheel drive), sedans and vehicles in 'fair', or 'good' condition had the next largest negative impact on price, followed by SUVs, hatchbacks and cars manufactured by Saturn.

### Top features that tended to increase the sales price
1. Trucks, diesel engines, 4wd, 8 cylinder engines, convertibles and coupes all contributed to higher sales prices.

### Additional Insights
1. Full size vehicles have a higher average sale price.
2. The sale price of a car drops quickly from 0-35 years old, after which the average sale price increase and remains relatively high relative to vehicles between 20-35 yrs old.
3. Cars of all types rarely sell for more than 10K if they've been driven more than 20K+ miles per year.

### Predictive Model Evaluation
The model produced was able to predict a car's sale price within 5K of the actual sale price 62.5% of the time. 

This accuracy could be improved by including model information, which was omitted to preserve speed. Future work could reduce the 4K+ unique model types by creating generalized groups for each manufacturer.

## Recommendations

Without knowing more about the specific location of a dealership, the supply of cars or the dealer purchase price relative to the average sale price, only general recommendations can be made. 

The results of the investigation show a focus on trucks, diesel and 8 cylinder vehicles would result in higher sale prices on average. 

Vintage dealerships should focus on cars older than 35 years.

Regardless of car type, limiting sales to vehicles that have been driven less than 20K miles per year on average will also result in higher sales prices on average.
