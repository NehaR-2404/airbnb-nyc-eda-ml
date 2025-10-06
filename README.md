# Airbnb Data Analysis & Price Prediction

## Project Overview
This project explores the **New York City Airbnb dataset** to understand factors affecting listing prices and predicts listing prices using a basic machine learning model.  

The main objectives are:  
1. Perform **data cleaning** and preprocessing.  
2. Conduct **exploratory data analysis (EDA)** to discover patterns and insights.  
3. Build a **baseline predictive model** using Linear Regression.  
4. Interpret results and insights to demonstrate practical data science skills.

---

## Dataset
- The cleaned dataset used in this project is available in `data/airbnb_nyc_cleaned.csv`.
- Original dataset can be downloaded from [Kaggle Airbnb NYC dataset](https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data).
- Key columns include: 
   - `price`
   - `room_type`
   - `neighbourhood_group`
   - `minimum_nights`
   - `number_of_reviews`
   - `reviews_per_month`
   - `calculated_host_listings_count`
   - `availability_365`

---

## Data Cleaning & Preprocessing
- Handled missing values in `name`, `host_name`, and `reviews_per_month`.  
- Converted `last_review` to datetime format.  
- Removed outliers:
  - Listings with `price > 3000` or `price = 0`.  
  - Listings with `minimum_nights > 365`.  

---

## Exploratory Data Analysis (EDA)

### Univariate Analysis
- **Price:** Most listings are between $50–$300; a few extreme outliers.  
- **Minimum Nights:** Most listings require ≤5 nights; extreme cases removed.  
- **Number of Reviews & Reviews per Month:** Skewed distribution; many listings have low reviews.  
- **Availability:** Highly variable across listings.  

### Bivariate Analysis
- **Price vs Neighbourhood Group:** Manhattan has the highest average price, followed by Brooklyn.  
- **Price vs Room Type:** Entire home/apartments are more expensive than private or shared rooms.  
- **Correlation Analysis:**  
  - Price and number of reviews: weak negative correlation.  
  - Availability and reviews per month: weak positive correlation.  

---

## Machine Learning: Predicting Airbnb Prices

### Step 1: Define Target & Features
- **Target:** `price`  
- **Features:** `neighbourhood_group`, `room_type`, `minimum_nights`, `number_of_reviews`, `reviews_per_month`, `calculated_host_listings_count`, `availability_365`  
- Categorical features encoded using **Label Encoding**.

### Step 2: Train-Test Split
- 80% of data for training, 20% for testing.  

### Step 3: Baseline Linear Regression Model
- **RMSE:** 150.43 → average prediction error ~$150  
- **R² Score:** 0.14 → 14% of price variation explained  
- **Insight:** Linear Regression gives a baseline; more complex models could improve predictions.

---

## Detailed Analysis
For the **full exploratory data analysis (univariate & bivariate), visualizations, and machine learning workflow**, please refer to the Jupyter Notebook:

`Newyork Airbnb Analysis.ipynb`

A concise summary of key insights is also available in `INSIGHTS.md`.

---

## Key Insights
- Manhattan and Brooklyn have the highest priced listings.  
- Entire homes/apartments command significantly higher prices.  
- Most hosts have 1–2 listings; a few hosts manage hundreds of properties.  
- Reviews and availability have weak correlation with price, suggesting other factors influence pricing.  

---

## Challenges
- Handling highly skewed data.   
- Encoding categorical variables for ML models.  
- Interpreting baseline model performance.  

---

## Learnings
- End-to-end data cleaning and preprocessing.  
- Generating actionable insights through visualization.  
- Building and evaluating a baseline ML model.  
- Documenting insights professionally for portfolio presentation.

---

## Tools & Libraries Used
- Python (pandas, numpy, matplotlib, seaborn)  
- Scikit-learn (Linear Regression, preprocessing, train-test split)  
- Jupyter Notebook
