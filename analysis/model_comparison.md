# Part 3: Regression-Based Business Insights & Model Interpretation

## Regression Models Analysis and Comparison

### Simple Linear Regression

#### Simple Regression 1: Monthly Sales vs Marketing Spend
1. **Regression Equation**  
$$\text{Monthly Sales} = 560,777.35 + 2.13 \times (\text{marketing\_spend})$$

2. **R-Squared**  
$0.1672$ ($16.72\%$)  

3. **Coefficient**  
$2.1296$  

4. **p-value**  
$2.48 \times 10^{-14}$ (very close to 0; very less than $\alpha$ = 0.05) 

5. **Business Interpretation**  
If the company spend Rs. 0 on marketing, the sales are expected to be Rs. 560,777.35. For every Rs. 1 spent on marketing, the sales increase by Rs. 2.13.  

6. **Variable Usefulness**  
The p-value is very less than $\alpha$ = 0.05 threshold, meaning marketing spend has a statistically significant positive relationship with sales. However, since R-squared is only 16.72%, that leaves over 83% of the variance in sales unexplained. Hence, it is limited useful.  
___________
#### Simple Regression 2: Monthly Sales vs Footfall
1. **Regression Equation**  
$$\text{Monthly Sales} = 446,410.58 + 35.68 \times (\text{footfall})$$

2. **R-Squared**  
$0.7363$ ($73.63\%$)  

3. **Coefficient**  
$35.6780$  

4. **p-value**  
$4.75 \times 10^{-94}$ (very close to 0; very less than $\alpha$ = 0.05)  

5. **Business Interpretation**  
If a store has 0 footfall, the baseline monthly sales are expected to be Rs. 446,410.58. For every one person visiting the store, the monthly sales increase Rs. 35.68.  

6. **Variable Usefulness**  
The p-value is almost 0, meaning footfall has a highly significant positive relationship. With an R-squared of 73.63%, footfall is a strong predictor of sales performance.
__________
### Multiple Linear Regression
1. **R-Squared**  
$0.8571$ ($85.71\%$)

2. **Table**  
This table shows the Coefficients, p-values, Direction of Relationship and their Business Interpretations of all the variables.  

| Variable | Coefficient | P-value | Relationship Direction | Business Meaning & Significance |  
| :---: | :---: | :---: | :---: | :---: |  
| Intercept | $62,219.72$ | $0.1716$ | N/A | The baseline sales value when all continuous X variables are 0, evaluated for a Residential store in the South region. |  
| `marketing_spend` | $1.21$ | $9.99 \times 10^{-22}$ | Positive (+) | Highly Significant. For every additional Rs. 1 spent on marketing, monthly sales increase by Rs. 1.21, holding other factors constant. |  
| `footfall` | $27.33$ | $6.55 \times 10^{-27}$ | Positive (+) | Highly Significant. Each additional store visitor drives Rs. 27.33 in monthly sales. |  
| `staff_count` | $3,510.84$ | $0.0027$ | Positive (+) | Highly Significant. Adding one extra staff member to a store is associated with a Rs. 3,510.84 increase in monthly sales.  |  
| `inventory_availability_pct` | $3,062.39$ | $5.06 \times 10^{-12}$ | Positive (+) | Highly Significant. For every 1% increase in product availability, sales increase by Rs. 3,062.39. |  
| `competitor_distance_km` | $-3,439.40$ | $7.05 \times 10^{-10}$ | Negative (-) | Highly Significant. For every 1 km closer a competitor moves (distance decreases), sales drop by Rs. 3,439.40.   |  
| `customer_rating` | $12,622.24$ | $0.0048$ | Positive (+) | Highly Significant. A 1-point increase in average customer rating correlates to a Rs. 12,622.24 increase in monthly sales. |  
| `is_east` | $-21,114.07$ | $0.0016$ | Negative (-) | Highly Significant. Stores in the East region underperform by Rs. 21,114.07 compared directly to the South region baseline.  |  
| `is_airport` | $44,722.36$ | $5.61 \times 10^{-7}$ | Positive (+) | Highly Significant. Airport stores out-perform standard Residential locations by Rs. 44,722.36 per month.  |  
| `is_high_street` | $20,263.95$ | $0.0003$ | Positive (+) | Highly Significant. High Street stores see a Rs. 20,263.95 premium over Residential locations. |  
| `is_mall` | $32,837.45$ | $1.88 \times 10^{-7}$ | Positive (+) | Highly Significant. Mall stores see a Rs. 32,837.45 premium over Residential locations. |  
-------

3. **Statistically Weak and Difficult to Interpret Variables** 
    - `avg_discount_pct` (P = 0.2259): This variable has a negative coefficient, implying discounts actually hurt total sales. However, because its P-value is greater than 0.05, it is statistically weak and unreliable. Changing discounts does not have an effect on sales.  
    - `is_west` (P = 0.5389) & `is_north` (P = 0.1340): Both regional dummy variables have high P-values. This means their sales are not statistically different from our baseline region South.  

-----------------------
### Model Comparison Table

| Model Name | Simple Regression (marketing_spend) | Simple Regression (footfall) | Multiple Regression |  
| :---: | :---: | :---: | :---: |  
| Variables Used | Dependent Variable (Y): `monthly_sales`; Independent Variable (X): `marketing_spend` | Dependent Variable (Y): `monthly_sales`; Independent Variable (X): `footfall` | Dependent Variable (Y): `monthly_sales`; Independent Variables (X): `marketing_spend`, `footfall`, `avg_discount_pct`, `staff_count`, `inventory_availability_pct`, `competitor_distance_km`, `holiday_flag`, `customer_rating`, `is_east`, `is_west`, `is_north`, `is_airport`, `is_high_street`, `is_mall` (14 variables) |  
| R Squared | 16.72% | 73.63% | 85.71% |  
| Significant Variables | p-value = $2.48 \times 10^{-14}$; Highly significant | p-value = $4.75 \times 10^{-94}$; Highly significant | `marketing_spend`, `footfall`, `avg_discount_pct`, `staff_count`, `inventory_availability_pct`, `competitor_distance_km`, and `customer_rating`, `is_airport`, `is_mall`, `is_high_street`, `is_east` all significantly impact sales. |  
| Business Usefulness | Low usefulness. Even though marketing has a positive return, the rest 83% of the sales is unexplained. This cannot be used for strategic financial planning. | Moderate usefulness. It shows that customer traffic contributes a lot to the sales. But it still isn't enough to make decisions. | Highly useful. This model shows how all the variables contribute to the sales. this is very helpful for many decisions other than just sales, like optimizing resourse allocation. |  
| Limitations | Other variables are omitted, hence results are over simplified. | Other variables are omitted, hence results are over simplified. | The model only assumes a linear statistical relationship. It cannot measure other qualitative factors.  |  
________

