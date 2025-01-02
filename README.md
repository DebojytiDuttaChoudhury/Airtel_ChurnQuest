# Customer Churn Analysis in Telecommunications

## Project Overview
This project focuses on analyzing customer churn within the telecommunications industry to uncover key factors contributing to churn and to propose actionable strategies for improving customer retention. By categorizing and analyzing customer behavior, service usage, and demographic data, this analysis aims to provide insights to mitigate churn effectively.

---

## Dataset Description
The dataset contains the following key columns:

- **Account Length**: Duration of the customer account in days.
- **Area Code**: The customer’s area code (408, 415, 510).
- **International Plan**: Whether the customer has an international plan (`yes/no`).
- **Voice Mail Plan**: Whether the customer has a voicemail plan (`yes/no`).
- **Number of Customer Service Calls**: Number of times the customer contacted customer service.
- **Call Usage and Charges**:
  - Day, Evening, Night, and International minutes, calls, and charges.
- **Churn Indicator**: Whether the customer churned (`yes/no`).

---

## Support Columns
To enhance analysis, the following calculated fields were created:

### 1. `norm_churn`
- **Formula**: `=IF(T2="no", "Not Churn", "Churn")`
- **Purpose**: Converts the churn status into a binary category for easier segmentation.

### 2. `num_churn`
- **Formula**: `=IF(T2="yes", 1, 0)`
- **Purpose**: Converts churn status into a numeric format for aggregation and statistical analysis.

### 3. `segmentation_number_customer_service_calls`
- **Formula**: `=IF(S2<=2, "Low (0-2)", IF(S2<=5, "Moderate (3-5)", "High (6+)"))`
- **Purpose**: Groups customers based on the number of customer service calls to analyze their correlation with churn.

### 4. `categorize_account_length`
- **Formula**: `=IF(B2<=12, "New (0-12 months)", IF(B2<=36, "Medium (13-36 months)", "Long (37+ months)"))`
- **Purpose**: Segments customers by account tenure to identify churn patterns over time.

### 5. `total_intl_calls_charge_categories`
- **Formula**: `=IF(R2<=1.8, "Low (≤0-1.8)", IF(R2<=3.6, "Medium (1.8-3.6)", "High (>3.6)"))`
- **Purpose**: Categorizes customers by international call charges to understand pricing sensitivity.

### 6. `vmail_messages_categories`
- **Formula**: `=IF(F2<=5, "Low Usage (0-5)", IF(F2<=15, "Moderate Usage (6-15)", "High Usage (>15)"))`
- **Purpose**: Groups customers by voicemail usage to explore its impact on churn.

---

## Key Findings
1. **Customer Tenure**:
   - Churned customers have slightly longer account lengths (102.14 days) compared to non-churned (99.92 days).

2. **International Plans**:
   - Customers with international plans have a significantly higher churn rate (42%) compared to those without (11%).

3. **Customer Service Calls**:
   - High call volume (6+ calls) has a 64% churn rate, whereas low call volume (0–2 calls) has an 11% churn rate.

4. **Call Usage and Charges**:
   - Churned customers incur higher day charges ($35.53 vs. $29.84) despite similar usage patterns.
   - Evening and international call charges are slightly higher for churned customers.

5. **Area Code and Churn**:
   - Customers from area code 415 have the highest churn rate (13.6%), followed by 510 (15%).

6. **Voice Mail Plans**:
   - Customers with voicemail plans have a lower churn rate (7%) compared to those without (16%).

---

## Recommendations
Based on the insights derived, the following actions are proposed to reduce churn:

1. **Enhance Customer Support**:
   - Improve issue resolution efficiency for high-service-call customers.
   - Implement proactive customer service for moderate-risk segments.

2. **Tailored Pricing Plans**:
   - Offer personalized pricing for international plan subscribers.
   - Reassess high call charges to address customer dissatisfaction.

3. **Retention Programs**:
   - Introduce loyalty programs for customers with long account tenures.
   - Offer incentives for customers in high-churn regions.

4. **Communication Improvements**:
   - Provide detailed billing transparency to address concerns about charges.
   - Educate customers on the benefits of voicemail plans.

---

## Tools and Technologies
- **Spreadsheet Software**: For calculations and support column creation.
- **Data Visualization**: Tableau, Power BI for creating interactive dashboards.
- **Programming**: Python and SQL for data cleaning and exploratory data analysis.

---

## Future Work
- Perform a predictive analysis using machine learning models to identify at-risk customers.
- Explore additional features like customer demographics and competitors' impacts.
- Implement A/B testing for pricing and service modifications.

---

## Conclusion
This analysis highlights the critical factors influencing customer churn in the telecommunications industry. The actionable insights provided will help reduce churn and enhance customer satisfaction. Future efforts will focus on predictive modeling and implementing recommended strategies.

---

## Author
This project was developed by Debojyti Dutta Choudhury.  
Feel free to connect: [LinkedIn Profile](https://www.linkedin.com/in/debojyti-dutta-choudhury)

---

## License
This project is open-source and available under the [MIT License](LICENSE).
