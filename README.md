## Project: Usage Behavior and Customer Segmentation Analysis – ConnectaTel

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/macarenahulsken/connectatel-data-analysis/blob/main/Project_ConnectaTel.ipynb)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com)

Business Objective:
The primary goal is to identify usage patterns, detect anomalies (outliers), and understand which customer segments exhibit distinct needs. These insights will be used to optimize the commercial offering and enhance the overall user experience (UX).

**Executive Summary**

⚠️ Data Quality & Integrity Issues

The initial phase revealed inconsistencies that required rigorous cleaning to prevent statistical bias:

Data Standardization: All features were cast to their appropriate data types for precise computation.
Geographic Inconsistencies: The city column contained 11.7% missing values (469 records) and "?" placeholders. These were standardized to nulls for accurate reporting.
Sentinel Values: The age column contained "-999" placeholders, which were corrected using Median Imputation to preserve the distribution. Missing Data Mechanism (MAR): A diagnostic check confirmed that nulls in duration (55.2%) and length (44.7%) are Missing At Random (MAR). They correlate directly with the service type: "text" records naturally have null duration, while "call" records have null text length.
Outlier Management: We applied Winsorization to the call_minutes column. This statistical capping ensures that average consumption metrics are not inflated by extreme, atypical user behavior.
🔍 Demographic Insights (Age & Location) ConnectaTel’s user profile shows a distinct distribution:

Primary Demographics: The core user base is aged 30–50, with a dominant presence in major hubs like Bogotá (the highest frequency city).
Plan Adoption: The Basic Plan is the market leader across all age brackets, accounting for 2,595 out of 4,000 analyzed users.
📊 Usage Segmentation & Behavior We identified two clear consumption profiles based on service interaction:

Messaging-Centric (Text): This is the high-frequency service with 22,092 records, significantly outperforming voice calls in volume.
Voice-Centric (Call): While lower in frequency, voice usage shows higher variability in duration, requiring closer monitoring.
Power Users (Outliers): Significant extreme usage was detected, including single calls lasting up to 120 minutes and messages exceeding 1,490 characters.
➡️ Strategic Implications

Business Value: While Premium users drive higher margins, the Basic plan holds the massive volume of data. This represents a major Upselling opportunity for users consistently exceeding their plan limits.
Operational Risk: Extreme usage patterns (2-hour calls) suggest a niche group using residential lines for commercial or professional purposes, which could impact network stability and profit margins for "unlimited" tiers.
💡 Strategic Recommendations

Tier Optimization: Introduce a "Basic Plus" intermediate plan. A plan focused on higher SMS limits could capture the large segment currently stuck between Basic and Premium.
Retention Strategy: Investigate the 11.7% of users with unknown locations. This "blind spot" may hide regional coverage issues that lead to Churn (customer cancellation).
Real-Time Usage Alerts: Implement automated alerts for high-usage outliers. If a Basic user hits an extreme threshold, trigger an immediate promotional offer to migrate them to a higher-tier plan.

Technologies & Tools: 
Python, Pandas, Seaborn, Matplotlib.pyplot, Numpy
