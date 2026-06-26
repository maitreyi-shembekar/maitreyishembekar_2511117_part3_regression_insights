# Part 3: Regression-Based Business Insights & Model Interpretation

## Final Recommendation

### 1. Factors Most Strongly Associated with Monthly Sales
Based on the multiple linear regression model ($R^2$ = 0.8571), the variables most strongly associated with monthly sales are:

1. **Footfall (Customer Traffic):** This is the strongest individual predictor in the model (Simple $R^2$ = 73.63%, Multiple Coefficient = + Rs. 27.33, $P \approx 0$).

2. **Premium Stores:** Store types makes a huge difference. Compared directly to suburban Residential locations, **Airport** format make + Rs. 44,722.36, **Mall** formats make + Rs. 32,837.45, and **High Street** formats make + Rs. 20,263.95.

3. **Customer satisfaction:** Customer satisfaction and resource availability also impact massively. Increasing a store's **Customer Rating** by 1 star adds + Rs. 12,622.24, maximizing **Inventory Availability %** yields + Rs. 3,062.39 per 1% increase, and adding a **Staff Member** brings in + Rs. 3,510.84 monthly.

_________
### 2. Variables to Focus On?
1. We should focus on Shelf Stocking and Logistics. Maximizing inventory availability is a priority. Because each 1% increase generates Rs. 3,062.39 across 320 stores, ensuring shelves are filled is an immediate priority.

2. We should focus on optimizing the staff. The model shows that adding a staff member yields a revenue of Rs. 3,510.84 per month (P = 0.0027). If the cost of hiring is below this threshold, increasing floor coverage is financially justified.

3. We should favor Airport and Mall locations over suburban Residential storefronts due to their revenue premiums.
_________
### 3. Variables not to be Over-interpreted?
- `avg_discount_pct`: The model shows a massive negative value to discounting (- Rs. 41,094.40), but its high P-value (0.2259) means this relationship is statistically weak and unreliable. This indicates that discounting do not have a uniform or predictable impact on revenue.

- **Geographic Performance Shifts (is_west & is_north):** While the East region significantly underperforms (- Rs. 21,114.07, P = 0.0016), the West (P = 0.5389) and North (P = 0.1340) show no statistical difference from the South baseline. Regional performance across the West, North, and South is virtually uniform, so localized problems should not be attributed to broad regional factors.
_________
### 4. Business Action
- Implement a policy to ensure inventory availability across all stores never drops below a certain point.

- Instead of pouring funds strictly into marketing (which yields a modest but statistically significant return of Rs. 1.21 for every Rs. 1 spent), shift budget toward core in-store operations.

- For underperforming stores, increase inventory depth, add 1 floor staff member, and target localized reputation fixes to lift review ratings by at least 0.5 stars.
_________
### 5. Risks and Limitations
- While our model captures 85.71% of variance, the remaining 14.29% contains unmeasured elements like hyper-local marketing campaigns, localized economic shocks, regional disposable income shifts, and specific landlord constraints.

- Linear regression models assume straight-line growth indefinitely. In reality, adding 50 staff members or reaching 200% inventory depth will not continuously grow sales. The model cannot identify where saturation or diminishing returns hit.
_________
### 6. Association vs. Causation in Regression Analysis
Linear regression models evaluate statistical association, meaning they track how two metrics move together mathematically.

However, mathematical models cannot prove why or which variable caused the movement.

For example, a high customer rating is associated with higher sales. But it might be that high sales volume gives a store the excess capital to build a beautiful store, which then causes high customer ratings (reverse causation). Alternatively, an unmeasured third factor such as, excellent local store management, could be causing high staff retention, high customer reviews, and high sales volume. Two variables may appear linked only because a third, unmeasured factor drives them both.
_________