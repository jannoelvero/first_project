********************
# AirBnB Project
********************
# Project overview:
From Poor Ratings to Exceptional Stays¶
A Data-Driven Analysis of Factors Influencing Airbnb Guest Satisfaction
....

# Installation

1. **Clone the repository**:

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

...


## Business Case - Question

What factors contribute to lower Airbnb guest ratings, and what improvements can hosts implement to increase guest satisfaction and listing performance?

## Dataset

airbnb-listing (Kagglehub) — Data set: "joyshil0599/airbnb-listing-data-for-data-science" (Kagglehub)¶


## Main dataset issues

- Missing values
- Price, Number of reviews and Rating format
- Inconsistent Property info
- Location formatting issues
- Amenities stored as descriptive text
- Uneven Monthly data


## Solutions for the dataset issues

- Issue: offer price had no price or missed values
- Solution: we decided to drop the column.

- Issue: Prices stored as strings, containing symbols (€, commas) or mixed formats.
- Solution: Cleaned and normalized price fields by stripping symbols and converting values to numeric types.

- Issue: Some listings had repited or incomplete property details.
- Solution: Standardized property categories, validated values, and removed listings with duplicates.

- Issue: Locations stored in inconsistent formats (city + neighborhood, mixed languages, special characters).
- Solution: Split location fields into structured components, normalized naming conventions, and removed special characters.

- Issue: Amenities were stored as long, unstructured text strings.
- Solution: split text into lists, standardized amenity names, and created binary indicators for analysis.

- Issue: date did not have a DD/MM/YYYY format, it was more as a stay period that could vary from few days to month.
- Solution: we decided to just take the month into account.


# Business Hypothesis

- # 1. What is the distribution of Airbnb listings based on high, average, and low ratings?
- Findings: The vast majority of Airbnb listings — 76.16% — fall into the high￾rated category. Only 3.31% are classified as low-rated, 
- representing just 20 listings out of the total dataset.

- # 2. Is there a significant difference in price between poorly rated and highly rated Airbnb listings?
- Findings: Highly rated listings command significantly higher prices — an average of 
- $168.93 versus $102.55 for low-rated listings, a difference of nearly $66

- # 3. Which property types are more likely to receive poor guest ratings?
- Findings: Hotel rooms and hotels recorded the highest share of poor ratings at 16.67%, followed by lofts at 15.38%. 
- Apartments had the lowest poor rating rate at just 9.33% — suggesting guests hold hotel-style listings to a higher standard than residential properties.

- # 4. Do amenities significantly influence the price of Airbnb listings?
- Findings: Listings mentioning more amenities tend to have higher prices, and this relationship is statistically significant. 
- However, the correlation is weak amenities alone do not strongly determine Airbnb prices.

- # 5. Does the location of an Airbnb listing significantly influence guest ratings?
- Findings: There is a statistically significant relationship between the number of amenities mentioned and Airbnb ratings 
- but it is negative and weak. More amenities listed does not translate to better guest satisfaction.

- # 6. Does the location of an Airbnb listing significantly influence Airbnb prices?
- The Kruskal-Wallis test confirms a statistically significant difference in Airbnb ratings across locations (H = 74.73, p = 0.0). 
- Where a listing is located meaningfully influences the guest experience and resulting ratings.

- # 7. Does the number of reviews significantly influence Airbnb ratings?
- There is a statistically significant but weak negative relationship between the number of reviews and Airbnb ratings. 
- Listings with more reviews tend to have slightly lower ratings — though the effect is modest.

- # 8. Which month has the highest number of reviews and the highest average Airbnb rating?
- June recorded the highest number of reviews with 66,386 total — reflecting peak travel season demand.

- # 9. What improvements should Airbnb hosts prioritize to transform poorly rated listings into highly rated accommodations?
- Service quality, Smart pricing, Guest expectations and amenity quality.


# Conclusions  

- Ratings Are Generally High
- 76.16% of listings are highly rated; only 3.31% are poorly rated.
- Price Matters, But Isn't Everything
- Highly rated listings cost more, but price alone doesn't explain ratings.
- Property Type & Location Are Key
- Both ratings and prices differ significantly by property type and location.
- Amenities & Reviews Have Limited Impact
- Amenity count and review volume show only weak relationships with ratings.


# Next steps
- Look at the number of beds and include in the analyis 
- Create a dashboard in Tableau


# Jan Noel Vero & Nadiya Al-Shahaibi