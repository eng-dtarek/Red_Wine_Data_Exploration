# Red Wine Data Exploration

## Summary

This project aims to explore the red wine dataset by getting an overview of the features characteristics, extracting the most interesting feature and analyze it across all the other variables to understand the impact of the variables on it.

## Univariate Analysis

### What is the structure of your dataset?

1599 red wines in the dataset with 13 features (x, fixed.acidity, volatile.acidity, citric.acid, residual.sugar, chlorides, free.sulfur.dioxide, total.sulfur.dioxide, density, pH, sulphates, alcohol and quality). All variables are num except for X and quality which are int.

Other observations: The quality is a discrete variable while all others are continuous variables.

Quality variable has a normal distribution

volatile.acidity, fixed.acidity and sulphates appear to have normal distribution when plotting them on log 10 base.

chlorides and residual.sugar have heavy tailed distribution with alot of outliers.

free.sulfur.dioxide and total.sulfur.dioxide have a long tailed distribution.

density and pH are normally distributed.

The quality of 75% of red wines are less than or equal to 6.

Many wines have 0 citric.acid

Min Quality is 3 and Max quality is 8.

Median fixed.acidity is 7.90.

Max volatile.acidity is 1.58.

Median PH is 3.31.

X variable is just an identifier of the observations.

### What is/are the main feature(s) of interest in your dataset?

I am very interested in the quality of red wine. I want to explore the variables affecting it.

### What other features in the dataset do you think will help support your investigation into your feature(s) of interest?

From googling and the variables descriptions, I think that the bellow variables will support my investigation into the quality variable

- Acids [Fixed, Volatile and citric]
- alcohol
- pH
- total sulfur dioxide

### Did you create any new variables from existing variables in the dataset?

- quality_rating: which is a categorical variable of quality variable
- total.fixed.acids: sum of fixed and citric acids in wine

### Of the features you investigated, were there any unusual distributions? Did you perform any operations on the data to tidy, adjust, or change the form of the data? If so, why did you do this?

There were long tailed and heavy tailed distributions besides normal. All I did with these data just setting binwidth and transform data to get better visualization.

## Bivariate Analysis

### Talk about some of the relationships you observed in this part of the investigation. How did the feature(s) of interest vary with other features in the dataset?

Quality correlates fairly with alcohol and volatile.acidity, high quality wines have high value of alcohol and low value of volatile.acidity.

quality has low positive correlation with fixed.acidity, citric.acid, sulphates and total.fixed.acids.It has low negative correlation with density, total.sulfur.dioxide and chlorides.

It seems that quality has a weak correlation with pH, residual.sugar and free.sulfur.dioxide.

### Did you observe any interesting relationships between the other features (not the main feature(s) of interest)?

Yes I observed the relationship between total_acids and pH Which seems to be exponential with strong negative correlation, which is logical as pH is a measure of acids.

Also the relationship between fixed.acidity and total.fixed.acids was observed linear relationship.

### What was the strongest relationship you found?

The relationship between fixed.acidity and total.fixed.acids

## Multivariate Analysis

### Talk about some of the relationships you observed in this part of the investigation. Were there features that strengthened each other in terms of looking at your feature(s) of interest?

By faceting the plots by quality rating, I can visualize the relationships between many variables and thier impact on the quality.

Starting with alcohol which has the highest correlation with quality, I notice that when alcohol increases the volatile.acidity decreases and wine quality increases.which is meaningful as we know from variable description that good wines have low value of volatile.acidity.

There is no relationship between alcohol and total.fixed.acids but both variables correlate with quality.good wines have high values of alcohol and total.fixed.acids.

Fixed.acidity and citric.acid are correlated to each others and have a little impact on quality. good wines have high values of both Fixed.acidity and citric.acid.

free.sulfur.dioxide and total.sulfur.dioxide are strongly correlated. we can see no impact for free.sulfur.dioxide on the quality but total.sulfur.dioxide has a little positive impact on the quality.

Finally pH seems to have strong correlation with both fixed.acidity and total.fixed.acids which is meaningful as pH is a measure of fixed.acidity and fixed.acidity is subset of total.fixed.acids.it also has a weak correlation with alcohol.

### Were there any interesting or surprising interactions between features?

From googling for pH variable I Knew that it is almost the backbone of wine quality but surprisingly I found almost no relationship between quality and pH it is extremely weak.

## Reflection

This dataset contains 1599 observations of 15 variables including quality varible that is my interesting feature. I began exploring all the variables individually.

After that I created a new categorical variable ‘quality_rating’ which categorizes the quality in a meaningful term rathar than the quality numbers.I have also collected all fixed acids variables (fixed.acidity and citric acids) into one variable total.fixed.acids.

I explored the quality variable across all the other variables to understand the impact of the variables on the quality.

I am able to specify that the main features affecting the quality are alcohol and acids.there is also other features that have a low impact like sulphates, density and pH.

I would be interested in creating a linear model and testing its accuracy


