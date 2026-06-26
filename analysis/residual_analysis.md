# Part 3: Regression-Based Business Insights & Model Interpretation

## Residual Analysis

**Final Selected Model : Multiple Linear Regression**

### 1. Calculating Predicted Sales
The Predicted Sales is calculated using regression coefficients derived in the multiple linear regression summary output.

$$\begin{aligned}
\text{Predicted Sales} = &\ \text{₹}62,219.72 \\
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
_______
### 2. Calculating Residuals
A residual is the error margin.  
**Residuals ($e$):** Calculated using the standard formula:
  $$\text{Residual} = \text{Actual Sales} - \text{Predicted Sales}$$
________
### 3. Top 5 Records with Largest Positive Residuals
| Observation | Predicted Sales | Residuals |  
| :---: | :---: | :---: |  
| 230 | Rs. 759,989.64 | + Rs. 110,947.76 |  
| 112 | Rs. 610,473.89 | + Rs. 103,137.27 |  
| 291 | Rs. 721,410.73 | + Rs. 91,905.98 |  
| 202 | Rs. 701,506.22 | + Rs. 86,209.29 |  
| 104 | Rs. 540,333.61 | + Rs. 85,180.43 |  
-----
**Business Meaning:**  
These stores are high-performing. These locations likely have some variables that offer localized advantages that cannot be calculated. For example, a highly exceptional store management, localized viral marketing, a temporary pop-up event nearby, or lack of regional competition. 

________
### 4. Bottom 5 records with Largest Negative Residuals
| Observation | Predicted Sales | Residuals |  
| :---: | :---: | :---: |  
| 90 | Rs. 764,154.66 | - Rs. 136,982.76 |  
| 67 | Rs. 805,203.31 | - Rs. 119,824.23 |  
| 45 | Rs. 709,877.64 | - Rs. 114,410.04 |  
| 26 | Rs. 912,416.86 | - Rs. 111,964.92 |  
| 237 | Rs. 807,986.95 | - Rs. 86,907.60 |  
----
**Business Meaning:** These locations are underperforming spots. This underperformance might be caused by localized road construction blocking store access, bad local store leadership, severe landlord issues, or aggressive unmeasured hyper-local pricing matching from a competitor.
________
### 5. Under-Predicting vs. Over-Predicting Trends

Multiple regression model handles categorical variables as fixed additions, it assumes every single airport or mall store functions uniformly.

* **Under-Predicting:** For places like Airport terminals or Malls, The model tends to under-predict when they hit peak traffic seasons because their sales grow exponentially rather than linearly.
* **Over-Predicting Under-Performing Regions:** The model calculated the East region as a whole (Rs. 21,114.07). However, for an exceptionally well-run store in the East, the model will drastically under-predict its capability.