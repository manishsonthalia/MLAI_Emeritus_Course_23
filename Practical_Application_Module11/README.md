# Manish-Sonthalia-Practical-Application-Assignment-11.1

# Objective:   
### To examine the used car sales data and develop a model that can predict the used car prices and determine the impact of various independent features on the used car prices.  The will use the analysis to provide specific recommendations to a used car dealership.

# Data Understanding:
### The dataset contained 18 column. 4 Numeric and the rest are categorical:
### Numeric Data:
- **id**: an external record identifier (426880 values)
- **Price**: The price of the car (in USD) (15655 values)
- **year**: The year of the car's model (114 values)
- **odometer**: The number of miles the car has been driven (104870 values)

### Non-numeric Data:
- **Region**: The U.S. Census region where the car was sold (404 values)
- **Price**: The price of the car (in USD) (15655 values)
- **manufacturer**: The manufacturer of the car (42 values)
- **model**: The model of the car (29649 values)
- **condition**: The condition of the car (good, excellent, like, fair, new)
- **cylinders**: The number of cylinders in the car (3 cylinders, 4 cylinders, 5 cylinders, 6 cylinders, 8 cylinders , 10 cylinders, 12 cylinders, other)
- **fuel**: The type of fuel the car uses (gas, diesel, hybrid, electric, other)
- **title_status**: The status of the car's title (clean, rebuilt, salvage, lien, missing, parts)
- **transmission**: The type of transmission the car has (automatic, manual, other)
- **VIN**: The car's vehicle identification number (118246)
- **drive**: The type of drive the car has (4wd, fwd, rwd)
- **size**: The size of the car (full-size, mid-size, compact, sub-compact)
- **type**: The type of car (sedan, SUV, pickup, truck, coupe, hatchback, wagon, van, convertible, mini-van, offroad, bus, other)
- **paint_color**: The color of the car (white, black, silver, blue, red, grey, green, custom, brown, yelhigh, orange, purple)
- **state**: The state where the car was sold (51 states)

### I found many missing values specifically the following features:
	
	Feature		%Missing Data
	size            	72%
	cylinders       	42%
	condition       	41%
	VIN             	38%
	drive           	31%
	paint_color     	31%
	type            	22%
	
### After removing outlier data and imputing the missing values, I was able to retain **66%** of data for the modeling.


# Summary of the Findings

## Modeling observations:  

1. <mark style="background-color: lightyellow">The Linear Regression model performs well in the $15K and $90K price range</mark>
2. Simple Regression Modeling was able to produce a good model with score: **0.795** and Test MAPE: **0.0279**

3. Below $15K the model tend t over-predict the prices

4. Above $90K the model tend t under-predict the prices

5. Manufacturing brands and car types have the most impact on the price
6. States have very little impact on the price
7. Type, Condition, fuel and title status all have impacts but less than manufactured.
8. Size and transmission have very little impact on pricing


## Examined the price categories and see if there is a relationship between the price and the other features.

### I created three price categories based on the price quantiles: 
* _Low Price_ : Less than $17K
* _Med Price_: Between $17K and $29K
* _High Price_:More than $29K 


_Low Price_ 
* Tend to have Odometer between 90 to 170K
* Tend to have built between 2006 to 2013
* Mostly sedan, SUV, and truck built between 2000 to 2010 with odometer between 100,000 to 200,000 miles and manufactured by Ford, Chevrolet, Toyota, Honda, and Nissan
*  Best Selling Models:  Ford F-150, Ford Escape, Toyota Camery, Honda Accord, Nissan Ultima, ... 


_Med Price_ 
* Tend to have Odometer between 40 to 100K
* Tend to have built between 2014 to 2017
* Mostly trucks, sedans, SUVs built between 2014 to 2017 with odometer less than 70K miles and manufactured by Ford, Chevrolet, ram, gmc, and Toyota
* Best Selling Models: Ford F-150, Chevrolet Siverado, Jeep Wrangler, Toyota Tacoma, Jeep Gran Cherokee


_High Price_ 
* Tend to have Odometer less than 70K
* Tend to have built between 2015 to 2019
* Mostly trucks, SUVs built between 2015 to 2019 with odometer between 40 to 100K miles and manufactured by Ford, Chevrolet, Toyota, Jeep, and Ram.
* Best Selling Models: Ford F-150, Chevrolet Siverado (all models), Ford F-250, Ford F-350


## Next steps and recommendations:

We can use the developed model to predict the used car prices and determine the impact of various independent features on the used car prices.  Based on my analysis I can provide the following recommendations to a used car dealership:

1.  We developed a robust Linear Regression model that can accurately predict the car prices between $15K to $90K price range
2.  Certain car brands can fetch higher prices (Ferrari, Tesla, Persche, Lexuss, ...) vs brands that fetch lower process (fiat, mercury, saturn, mitsubishi, ...)
3.  Trucks and SUVs are more popular in the mid to high price categories.  Sedans are more popular in the low price category
4.  Trucks from Ford and Chevrolet are sold the most and should be a big part of your inventory
5.  In general, cars in high price categories generate much higher sales volumes
6.  Further clean up of the missing or mistyped Type and Model data could provide a larger dataset and allows predictions against specific model
7.  Provide recommendation on the top 10 models for each price category after the type and model cleanups 
