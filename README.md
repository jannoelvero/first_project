# Project overview
This project analyzes Airbnb property listings to identify factors associated with property prices and guest ratings, with particular attention to poorly rated listings.

The main business problem is:

What factors contribute to lower Airbnb guest ratings, and what improvements can hosts prioritize to improve poorly rated listings?

The project follows an integrated Python and SQL data analytics workflow.

Python and Pandas are used for data loading, cleaning, transformation, feature engineering, exploratory data analysis, statistical testing, and visualization.

MySQL is used to store the cleaned dataset and perform structured SQL queries, aggregations, filtering, grouping, and analytical operations.

The overall project workflow is:

Raw Airbnb Data
        ↓
Load Data with Python
        ↓
Data Validation
        ↓
Missing Value Analysis
        ↓
Duplicate Detection
        ↓
Data Cleaning
        ↓
Feature Engineering
        ↓
Clean Dataset
        ↓
Python EDA             MySQL Database
        ↓                     ↓
Statistical Tests       SQL Analysis
        ↓                     ↓
        └───────┬─────────────┘
                ↓
          Visualizations
                ↓
           Key Findings
                ↓
         Recommendations

The project uses Python and SQL together rather than treating them as separate analytical processes.

Python is primarily used for data preparation, statistical analysis, and visualization, while SQL is used for structured storage and querying of the cleaned data.
# Installation

1. **Clone the repository**:
2. git clone https://github.com/jannoelvero/first_project.git

```bash
git clone https://github.com/YourUsername/repository_name.git
```

2. **Install UV**

If you're a MacOS/Linux user type:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

If you're a Windows user open an Anaconda Powershell Prompt and type :

```bash
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

3. **Create an environment**

```bash
uv venv 
```

3. **Activate the environment**

If you're a MacOS/Linux user type (if you're using a bash shell):

```bash
source ./venv/bin/activate
```

If you're a MacOS/Linux user type (if you're using a csh/tcsh shell):

```bash
source ./venv/bin/activate.csh
```

If you're a Windows user type:

```bash
.\venv\Scripts\activate
```

4. **Install dependencies**:

```bash
uv pip install -r requirements.txt
```
The project uses:

Python
Pandas
NumPy
MySQL
SQL
SQLAlchemy
PyMySQL
SciPy
Matplotlib
Seaborn
Jupyter Notebook

MySQL Setup

The cleaned dataset is also stored in MySQL.

The project database is:

airbnb_project

The main SQL table is:

airbnb_listings

Python connects to MySQL using SQLAlchemy and PyMySQL.
# Questions 
...
The project investigates the following research questions.

RQ1

What is the distribution of Airbnb listings based on high, average, and low ratings?

RQ2

Is there a significant difference in price between poorly rated and highly rated Airbnb listings?

RQ3

Which property types are more likely to receive poor guest ratings?

RQ4

Do amenities significantly influence the price of Airbnb listings?

RQ5

Do amenities significantly influence Airbnb ratings?

RQ6

Does the location of an Airbnb listing significantly influence guest ratings?

RQ7

Does the location of an Airbnb listing significantly influence Airbnb prices?

RQ8

Does the number of reviews significantly influence Airbnb ratings?

RQ9

Which month has the highest number of reviews and the highest average Airbnb rating?

RQ10

What improvements should Airbnb hosts prioritize to transform poorly rated listings into highly rated accommodations?
# Dataset 
...
The project uses Airbnb property listing data containing information about property characteristics, listing descriptions, location, price, guest ratings, reviews, and amenities.

Following the cleaning and feature engineering process, the final dataset contains:

604 Airbnb listings

24 variables

The cleaned dataset is exported as:

airbnb_cleaned.csv

The final variables are:

Property Name
Listing Description
Property Type
City
Country
Month
Price(in dollar)
Rating
Number of Reviews
Rating Rank
Price Rank
WiFi
Pool
Sauna
Hot Tub
Fireplace
Wood Stove
Parking
Kitchen
Beach
Waterfront
Sea View
Mountain View
Amenity Count

The cleaned dataset is also transferred from Python into MySQL for SQL based analysis.

Database: airbnb_project

Table: airbnb_listings
## Main dataset issues

- ...
- ...
- ...
The original Airbnb data required cleaning and transformation before reliable analysis could be performed.

The main issues identified were:

Missing values in selected variables, particularly ratings.
Duplicate listing records.
Price information that was not initially suitable for numeric analysis.
Rating information that required cleaning and standardization.
Review information that required extraction and conversion.
Property and location information stored in formats that required restructuring.
Date information that needed to be converted into month.
Property names containing unusual or invalid special character patterns.
Amenities embedded within listing descriptions rather than stored as separate analytical variables.
Differences in structure across the source datasets that required standardization before combining the data.
## Solutions for the dataset issues
...
Python and Pandas were used for the main data preparation process.

Data loading

The original datasets were loaded into Pandas DataFrames for inspection and cleaning.

The initial inspection included:

Dataset dimensions
Column names
Data types
Missing values
Duplicate records
Unique values
Descriptive statistics
Missing values

Missing values were identified using Pandas.

Ratings with missing values were handled during the cleaning process to ensure that the final dataset could be used consistently for analysis.

Duplicate records

Duplicate records were identified, inspected, and removed.

A final duplicate check was performed after cleaning.

Property information

Property information was cleaned and standardized.

Property names containing invalid or inappropriate special character patterns were identified and removed where necessary.

Location

Location information was restructured into:

City
Country

This allowed geographic comparisons to be performed during the exploratory and statistical analyses.

Month

Date information was transformed into a standardized:

Month

variable for monthly analysis.

Price

The price variable was cleaned and converted into numeric format.

The final variable used for analysis is:

Price(in dollar)

This allows calculations such as:

Average price
Median price
Minimum price
Maximum price
Price comparison
Price ranking
Rating

Rating information was cleaned and converted into a numeric variable.

Listings were subsequently classified into rating categories for analysis.

The categories used were:

Low Rating
Rating below 4.5

Average Rating
Rating from 4.5 to below 4.8

High Rating
Rating of 4.8 or above
Reviews

The number of reviews was extracted and stored as:

Number of Reviews

This variable was used to investigate the relationship between review volume and guest rating.

Feature engineering

Additional variables were created to support the analysis.

These included:

Rating Rank
Price Rank
Amenity Count

Individual amenity indicators were also extracted from listing descriptions:

WiFi
Pool
Sauna
Hot Tub
Fireplace
Wood Stove
Parking
Kitchen
Beach
Waterfront
Sea View
Mountain View

Each amenity variable identifies whether the amenity was detected in the listing information.

Amenity Count represents the number of identified amenities associated with each listing.

Clean dataset

After cleaning, validation, duplicate removal, and feature engineering, the final dataset contained:

604 listings
24 variables

The dataset was exported as:

airbnb_cleaned.csv
MySQL integration

The cleaned Pandas DataFrame was transferred into MySQL using SQLAlchemy and PyMySQL.

The MySQL database is:

airbnb_project

The table is:

airbnb_listings

SQL was then used for:

Filtering
Grouping
Aggregation
Property comparisons
Location comparisons
Rating analysis
Price analysis
Review analysis
Amenity analysis
Exploratory Data Analysis

Exploratory data analysis was conducted using Python and SQL.

The analysis examined:

Dataset structure
Rating distribution
Price distribution
Property types
Countries and cities
Guest ratings
Number of reviews
Amenities
Monthly patterns
Relationships between analytical variables

SQL was used for structured aggregation and filtering, while Python was used for statistical analysis and visualization.

Statistical Analysis

Because several research questions ask whether relationships or differences are statistically significant, inferential statistical methods were used in addition to descriptive analysis.

Mann Whitney U Test

The Mann Whitney U test was used to compare prices between poorly rated and highly rated Airbnb listings.

Spearman Correlation

Spearman correlation was used to examine relationships between:

Amenity Count and Price
Amenity Count and Rating
Number of Reviews and Rating
Kruskal Wallis Test

The Kruskal Wallis test was used to evaluate differences in:

Ratings across locations
Prices across locations

These nonparametric methods were appropriate for examining relationships and group differences without relying on normal distribution assumptions.

# Conclussions
...
RQ1: Rating Distribution

The majority of properties in the dataset are highly rated.

The rating distribution is:

Rating Category	Listings	Percentage
High	460	76.16%
Average	124	20.53%
Low	20	3.31%

Only 20 listings are classified as poorly rated.

This means the low rating group represents a relatively small proportion of the dataset and comparisons involving this group should be interpreted with appropriate caution.

RQ2: Price and Rating

Highly rated listings were more expensive than poorly rated listings.

Poorly rated listings had an average price of:

$102.55

Highly rated listings had an average price of:

$168.93

The median prices were:

Poorly Rated: $79

Highly Rated: $131

The Mann Whitney U test produced:

U Statistic: 2939.5

P Value: 0.0063

The result is statistically significant at the 0.05 significance level.

Therefore, the analysis indicates a significant difference in price between poorly rated and highly rated listings in this dataset.

RQ3: Property Type and Poor Ratings

Hotels and hotel rooms showed the highest proportion of poorly rated listings at:

16.67%

Lofts followed at:

15.38%

Apartments had a lower proportion of poorly rated listings at:

9.33%

However, apartments accounted for the largest absolute number of poorly rated properties, with seven listings.

Property types represented by very small numbers of listings should be interpreted cautiously.

RQ4: Amenities and Price

The relationship between amenity count and Airbnb price was examined using Spearman correlation.

The result was:

Spearman Correlation: 0.101

P Value: 0.013

The relationship is statistically significant but weak.

Listings with no identified amenities mentioned had an average price of approximately:

$144.04

Listings with three identified amenities had an average price of approximately:

$224.75

The results suggest that listings mentioning more amenities tend to have somewhat higher prices, but amenity count alone is not a strong predictor of price.

RQ5: Amenities and Rating

The relationship between amenity count and Airbnb rating produced:

Spearman Correlation: negative 0.115

P Value: 0.0045

The relationship is statistically significant but very weak.

The negative correlation indicates that simply mentioning or providing more amenities does not necessarily result in higher guest ratings.

Guest satisfaction therefore appears to depend on factors beyond the number of amenities.

RQ6: Location and Rating

Guest ratings differed significantly across geographic locations.

The Kruskal Wallis test produced:

H Statistic: 74.730

P Value: below 0.001

North Carolina recorded an average rating of approximately:

4.963

The United Kingdom recorded approximately:

4.927

Germany recorded approximately:

4.925

Other locations, including Malaysia, Vietnam, and Spain, recorded lower average ratings within the analyzed data.

The results indicate that location is significantly associated with guest ratings.

However, this relationship should not be interpreted as evidence that location directly causes higher or lower ratings.

RQ7: Location and Price

Airbnb prices also differed significantly across locations.

The Kruskal Wallis test produced:

H Statistic: 175.778

P Value: below 0.001

California recorded the highest average price at approximately:

$371.91

Texas followed at approximately:

$264.60

North Carolina recorded approximately:

$235.83

Lower average prices included:

Malaysia: $56.70

Vietnam: $66.62

Germany: $79.38

The results demonstrate that geographic market differences are important when analyzing Airbnb pricing.

RQ8: Number of Reviews and Rating

The relationship between number of reviews and rating produced:

Spearman Correlation: negative 0.184

P Value: below 0.001

The relationship is statistically significant but weak.

Listings with more reviews tend to have slightly lower ratings.

However, this does not demonstrate that receiving more reviews causes ratings to decline.

RQ9: Month, Reviews, and Rating

June had the highest aggregated review count in the dataset:

66,386 reviews

May recorded the highest average rating:

4.98

However, May contains only one listing.

The dataset is also heavily concentrated in June, which contains:

401 of the 604 listings

January and May contain only one listing each, while December contains only two.

Therefore, monthly comparisons must be interpreted cautiously.

An additional limitation is that Number of Reviews represents the review count associated with a listing and does not necessarily represent reviews written during that specific month.

The monthly analysis therefore describes the characteristics of listings associated with each month rather than definitive monthly guest review activity.

RQ10: Improving Poorly Rated Listings

The combined results indicate that Airbnb hosts should focus on the overall guest experience rather than relying primarily on increasing the number of amenities.

Amenities showed only weak relationships with both price and rating.

Location showed significant relationships with price and guest rating, while certain property types showed greater exposure to poor ratings.

The findings suggest that hosts should prioritize:

Property cleanliness and condition

Service quality and consistency

Accurate property descriptions

Appropriate pricing relative to the local market

Guest expectation management

Monitoring recurring guest complaints

Quality and functionality of amenities

Responsiveness to guest feedback

The findings indicate associations within this dataset and should not be interpreted as proof of causal relationships.
# Next steps
...
Several improvements could strengthen future analysis.

Expand the dataset

A larger dataset would provide more observations for poorly rated listings and reduce the imbalance between low, average, and highly rated properties.

Improve geographic representation

The dataset contains uneven numbers of listings across locations.

Future analysis should use more balanced geographic samples.

Collect review level data

Future datasets should include individual review dates rather than relying only on the total number of reviews associated with each property.

This would allow more reliable analysis of:

Seasonality
Monthly review activity
Changes in guest satisfaction over time
Analyze individual amenities

Future analysis could investigate whether specific amenities have stronger relationships with price or rating than total amenity count.

For example:

WiFi
Pool
Parking
Kitchen
Waterfront
Sea View
Mountain View
Add additional property variables

Future datasets could include:

Number of bedrooms
Number of bathrooms
Guest capacity
Property size
Host experience
Host response rate
Neighborhood
Cleaning quality
Cancellation policy
Length of stay

These variables may help explain price and rating differences more effectively.

Conduct multivariable analysis

Future work could use regression models to analyze several predictors simultaneously.

This could help determine the relative importance of:

Location
Property Type
Price
Amenities
Number of Reviews

while controlling for other variables.

Conduct post hoc analysis

The Kruskal Wallis tests show that significant differences exist across locations but do not identify every specific pair of locations that differs.

Post hoc statistical testing could be used to investigate these differences further.

Predict poorly rated listings

A future extension could develop a predictive model to identify listings at greater risk of receiving poor ratings.

This could help hosts identify potential problems before guest satisfaction declines.
ß