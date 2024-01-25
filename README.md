# LRD_Predictor
Predicting the Price of Vintage Land Rover Defenders using a custom scraped dataset
# Problem
Although there is a market ineffiency between EU and US of vintage Land Rover Defenders, the process of finidng the right model to arbitrage is laborious and prone to human error. 

# Goal
Accurately predict the price of Defenders aged 25 or older in the US Market. Apply that model to LRD listings in the EU. If the difference of predicted price and listed price is greater than 10% the listing is flagged. These listings will then be asessed by me for potential imports.

# Scraping Data
All data is scraped from classic.com which archives many previous listings. The dataset is scraped from the following criteria: Left hand drive, > 25 years old (makes them eligible for importation), sold in the US within the last 5 years. The dataset consists of 488 sold vehicles.

Raw Features: Price, Exterior Color, Model Type, Engine Variant, Age (Current year - manufactured year), Originality (Built-in to the website ie.Restored-modified, Restored-original, Highly Original, Highly Modified)

# Cleaning Data
Visualized correlation of price vs features, identified and handled outliers, analyzed groupings (popular values/ranges for each feature)
Fixed bug with final mileage, standardized model names and engine variant, grouped exterior colors.

Created age originality score (original --> modified == 0.5 --> 2 : score*age = originality score). This is a little tricky because in some cases originality increases price, and if done right modifying the truck can increase value.

TRY: Figure out possible features

# Building Model
Using very simple Random Forest Regressor as baseline, still a lot to play around with to achieve accurate results.

TRY: Feature analysis, Cross validation, different models, simplify features, add features,
# Problem
1) The buyers are relatively price insensitive in the US due to the fact that these cars are collectibles/beach cars for the majority. This makes it hard to find a solid relationship between features and price as it is mostly derived from other factors such as overall health of economy.

2) Lack of data. Struglling w/ overfitting in part because there aren't enough examples. The more I simplify features, the more I lose from the real world applicability.