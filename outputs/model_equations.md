# Part 3: Regression-Based Business Insights & Model Interpretation

## Model Equations

### 1. Simple Regression Equations

1. **Model 1: Marketing Spend**  
$$\text{Projected Monthly Sales} = \text{₹}560,777.35 + \text{₹}2.13 \times (\text{Marketing Spend})$$

2. **Model 2: Footfall**  
$$\text{Projected Monthly Sales} = \text{₹}446,410.58 + \text{₹}35.68 \times (\text{Footfall})$$
________
### 2. Multiple Regression Equation

$$\begin{aligned}
\text{Projected Monthly Sales} = &\ \text{₹}62,219.72 \\
&+ \text{₹}1.21 \times (\text{Marketing Spend}) \\
&+ \text{₹}27.33 \times (\text{Footfall}) \\
&- \text{₹}41,094.40 \times (\text{Average Discount \%}) \\
&+ \text{₹}3,510.84 \times (\text{Staff Count}) \\
&+ \text{₹}3,062.39 \times (\text{Inventory Availability \%}) \\
&- \text{₹}3,439.40 \times (\text{Competitor Distance KM}) \\
&+ \text{₹}15,135.31 \times (\text{Holiday Flag}) \\
&+ \text{₹}12,622.24 \times (\text{Customer Rating}) \\
&- \text{₹}21,114.07 \times (\text{Is East}) \\
&+ \text{₹}4,188.53 \times (\text{Is West}) \\
&- \text{₹}11,161.03 \times (\text{Is North}) \\
&+ \text{₹}44,722.36 \times (\text{Is Airport}) \\
&+ \text{₹}20,263.95 \times (\text{Is High Street}) \\
&+ \text{₹}32,837.45 \times (\text{Is Mall})
\end{aligned}$$
________
### 3. Explanation of Each Coefficient
1. **Intercept (Rs. 62,219.72, Insignificant):** The theoretical base sales for a Residential store in the South region if all continuous operational spend/metrics are dropped to zero.  

2. **Marketing Spend (Rs. 1.21, Highly Significant):** each additional Rs. 1 spent on marketing generates Rs. 1.21 in revenue.  

3. **Footfall (+ Rs. 27.33, Highly Significant):** For every 1 additional customer visiting the stores, monthly revenue increases by Rs. 27.33.  

4. **avg_discount_pct (- Rs. 41,094.40, Statistically Weak):** Increasing the discount percentage decreases revenue. However, with a high P-value (0.2259), this metric is statistically weak and should not be used as a primary metric.  

5. **Staff Count (+ Rs. 3,510.84, Highly Significant):** Adding 1 more staff member to the stores generates an additional Rs. 3,510.84 in monthly sales.  

6. **Inventory Availability % (+ Rs. 3,062.39, Highly Significant):** For every 1% increase in product availability, monthly revenue increases by Rs. 3,062.39.  

7. **Competitor Distance KM (- Rs. 3,439.40, Highly Significant):** For every 1 km a competitor moves closer (reducing distance), store sales reduce by Rs. 3,439.40.  

8. **Holiday Flag (+ Rs. 15,135.31, Significant):** Stores operating during holiday months increases revenue of Rs. 15,135.31.  

9. **Customer Rating (+ Rs. 12,622.24, Highly Significant):** Increasing a store's average review score by 1 full star increases sales by Rs. 12,622.24.  

10. **Is East (- Rs.21,114.07, Highly Significant):** Stores in the East region underperform compared to the baseline South region by Rs. 21,114.07 per month.  

11. **Is West (+ Rs. 4,188.53, Statistically Weak) & Is North (- Rs. 11,161.03, Statistically Weak):** Both have high P-values (> 0.05), meaning their sales are not different from the South region. Any variations observed are due to random noise.  

12. **Is Airport (+ Rs. 44,722.36), Is Mall (+ Rs. 32,837.45), Is High Street (+ Rs.20,263.95, Highly Significant):** All three significantly outperform standard Residential locations, with Airport terminals being the highest grossing environment.  
_______
### 4. Explanation of Dummy Variables
To include qualitative text attributes (such as Region and Store Type) in a mathematical model, these fields were converted into binary Dummy Variables.

To prevent data redundancy and avoid the "Dummy Variable Trap", one category from each group was omitted to become the reference baseline.  

_______
### 5. Reference Category Used
**Reference Categories Selected:**
- Regional Baseline: South
- Store Type Baseline: Residential  

This represents a Residential store type located in the South region during a non-holiday month. The model's Intercept (Rs. 62,219.72) is where all other variables are zero. The South-Residential baseline is part of this intercept and all regional and store-type coefficients measure whether a location performs better or worse relative to this South-Residential baseline.
______
### 6. Final Model Selected
**Multiple Linear Regression Model**

### 7. Reason for selecting the final model
- The simple marketing spend model explains only 16.72% of sales, and the footfall model explains 73.63%. The multiple regression model captures 85.71% of all monthly sales variation. This makes it safer and more accurate for decision making.  
- The Standard Error drops from Rs. 94,846 to Rs. 40,124. Using the multiple regression model reduces errors by over half. This reduces risk.  
