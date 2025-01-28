# NYC Yellow Taxi Trip Data: Hypothesis Testing & Regression Analysis  

This repository contains a comprehensive analysis of the NYC Yellow Taxi Trip data, focusing on hypothesis testing and regression analysis to explore how factors such as trip distance, payment preferences, and other variables influence fare amount. The study investigates whether payment methods significantly affect fare pricing and offers data-driven insights to help taxi drivers optimize their revenue.

## Data Collection  

The dataset used in this analysis is sourced from the NYC Taxi & Limousine Commission (TLC) and includes detailed records of yellow taxi trips. Key features include:  

- **Pickup and Dropoff Dates/Times**: Timestamps indicating trip start and end times.  
- **Passenger Count**: Number of passengers per trip.  
- **Trip Distance**: Distance traveled during the trip.  
- **Payment Type**: Method of payment used (Cash or Card).  
- **Fare Amount**: Total fare for the trip.  

## Data Preprocessing  

Before analysis, the data underwent several preprocessing steps:  

1. **Data Cleaning**: Removed duplicate, missing or inconsistent values.  
2. **Feature Engineering**: Created new variables, such as trip duration (from pickup and dropoff times).  
3. **Data Transformation**: Converted categorical variables into numerical formats for analysis.
4. **Feature Selection**: Extracted important columns using correlation matrix and heatmap.
5. **Outlier Treatment**: Removed negative and extreme values from columns like trip distance, total amount & trip duration using inter-quartile range.

## Descriptive Analysis  

Statistical analysis was conducted to summarize key aspects of the data, focusing on **payment type, trip distance, trip duration, and fare amount**:  

- Customers paying with cards tend to have a slightly higher average trip distance and fare amount compared to those paying with cash.  
- Customers prefer to use cards for higher fare amounts and longer trips.
- Card payments account for 65.9% of all transactions, while cash payments make up 34.1%, indicating a strong preference for credit card usage due to convenience, security, or incentives.

### Passenger Count Analysis  

- Single-passenger rides dominate both card and cash payments:  
  - **48% of all card transactions** involve single-passenger rides.  
  - **24% of all cash transactions** involve single-passenger rides.  
- The percentage of transactions decreases as the passenger count increases, suggesting that larger groups may prefer alternative transportation methods.  
- These insights emphasize the need to consider both payment method and passenger count when analyzing customer behavior.  

## Hypothesis Testing  

### Hypothesis: Payment Method vs. Fare Amount (using a random sample of 100K records from the overall population)

- **Null Hypothesis (H₀)**: There is no difference in average fare between customers who use credit cards and customers who use cash.  
- **Alternative Hypothesis (H₁)**: There is a significant difference in average fare between customers who use credit cards and customers who use cash.  

#### Results:  

- **T-statistic**: 129.6  
- **P-value**: < 0.01 

Since the P-value is less than 0.01, we **reject the null hypothesis**, confirming a statistically significant difference in fare amounts between the two payment methods.  

## Regression Analysis  

A **multiple linear regression model** was implemented to explore the relationship between **passenger count, trip distance, trip duration**  and **fare amount**. 

#### Model Performance Metrics:  
- **Mean Squared Error (MSE)**: `0.6821`  
- **R-squared (R²)**: `0.9651`  

The **high R² value (0.9651)** suggests that the model explains approximately **96.5% of the variance** in fare amount based on passenger count, trip distance, and trip duration, indicating a strong relationship between these variables. 
The **low MSE (0.6821)** further supports the model’s accuracy in predicting fare amounts.  

These results confirm, and reinforce the importance of time/duration based pricing in taxi services.

## Key Insights  

- Customers using credit cards tend to have higher fare amounts and longer trip distances compared to cash payers. 
- Card payments dominate the payment method preference, making up 65.9% of all transactions.
- The difference in fare amount between payment methods is statistically significant, suggesting that encouraging card payments may lead to increased revenue for taxi drivers.
- Single-passenger rides make up the largest proportion of transactions, highlighting an opportunity to tailor services based on passenger behavior. 

## Recommendations  

To maximize revenue and enhance customer satisfaction, the following strategies are recommended:  

1. **Encourage Credit Card Payments**  
   - Capitalize on the higher fare amounts associated with credit card transactions.  
   - Promote card payments through driver incentives.  

2. **Offer Incentives for Card Transactions**  
   - Implement discounts or reward programs for card users to further increase adoption.  

3. **Enhance Payment Convenience & Security**  
   - Ensure seamless and secure credit card payment options to improve the passenger experience.  
   - Provide multiple digital payment options to accommodate customer preferences.  

4. **Optimize Services for Single-Passenger Rides**  
   - Since single-passenger rides dominate transactions, consider tailored promotions for solo riders.  

By implementing these data-driven strategies, taxi services can **increase revenue while improving the overall customer experience**.  

## Dependencies  

The analysis was conducted using Python, with the following key libraries:  

- `pandas`
- `numpy` 
- `matplotlib`
- `seaborn`
- `scipy`
- `statsmodels` 

## References
- [NYC Yellow Taxi Trip Dataset](https://www.kaggle.com/datasets/elemento/nyc-yellow-taxi-trip-data)
