# ECHO Telecommunication Customer Churn and Retention Analysis
[Introduction](#Introduction)

[Objective](#Objective)

[Story of Data](#StoryofData)

[Data Splitting and Preprocessing](#DataSplittingandPreprocessing)

[Pre-Analysis](#Pre-Analysi)

[In-Analysis](#In-Analysis)

[Post-Analysis and Insights](#Post-AnalysisandInsights)

[Data Visualizations & Charts](#DataVisualizations&Charts)

[Recommendations and Observations](#RecommendationsandObservations)

[Conclusion](#Conclusion)

[References & Appendices](#References&Appendices)

## Introduction

ECHO Telecommunication has been experiencing a concerning trend in customer attrition over the past fiscal year. With increasing competition in the telecommunications market and rising customer acquisition costs, retaining existing customers has become a strategic priority. This analysis was conducted to gain data-driven insights into the causes of customer churn and to develop targeted retention strategies

### Objective of the Project

The primary objective of this analysis is to identify and understand the key factors driving customer churn at ECHO Telecommunication. Specifically, the project aims to:

1.	Determine which customer behaviors and characteristics most strongly correlate with service cancellation
	
2.	Quantify the impact of various factors on churn probability
  	
3.	Develop actionable recommendations to reduce customer attrition
   
4.	Create a framework for ongoing churn risk monitoring
   
### Problem Being Addressed

ECHO Telecommunication is experiencing a concerning 14% customer churn rate, with 483 customers out of 3,333 terminating their service. This level of customer attrition represents significant revenue loss and increased pressure on customer acquisition efforts. The analysis addresses several critical questions:

1.	Why are customers leaving ECHO Telecommunication?
   
2.	Which customer segments demonstrate the highest churn risk?
	
3.	What service usage patterns correlate with increased departure probability?
   
4.	How do customer service interactions influence retention?
   
5.	What specific interventions could effectively reduce churn rates?
   
### Key Datasets and Methodologies

This analysis leverages comprehensive customer data from ECHO Telecommunication's internal systems, including:

#### Datasets Used

•	Customer account information (account length, area code

•	Service configuration data (international plan, voicemail plan)

•	Usage metrics (call volumes, minutes used, day/night calling patterns)

•	Customer service interaction records (number and frequency of support calls)

•	Billing information (spending levels, daily charges)

•	Churn status (active vs. terminated accounts)

#### Methodologies

•	Descriptive statistical analysis using Microsoft Excel

•	Pivot tables to aggregate and analyze customer segments

•	Data visualization techniques including bar charts, line graphs, and pie charts

•	Comparative analysis between churned and retained customer groups

•	Pattern recognition across multiple variables to identify churn predictors

The analysis combines quantitative data examination with business context to develop insights that are both statistically sound and practically applicable for ECHO Telecommunication's retention efforts.

•	Exploratory data analysis using Microsoft Excel pivot tables to identify patterns

•	Statistical analysis of correlations between variables and churn outcomes

•	Customer segmentation based on usage patterns and service characteristics

•	Comparative analysis of churned versus retained customers

•	Data visualization through charts and dashboards to illustrate key findings

•	Cross-tabulation to identify relationship strength between factors and churn

## Story of Data

### Data Source

The dataset represents customer information from ECHO Telecommunication, containing records of 3,333 customers with various service usage metrics and churn indicators.

### Data Collection Process

The data was collected through Echo Telecommunication's automated customer management system, which continuously tracks customer activities, billing information, and service utilization. The system automatically logs customer interactions with support services, call details (including duration, timing, and destination), and account status changes. When customers cancel their service, the system records this as churn along with the timing of the cancellation.

### Data Structure

The dataset is organized with each row representing an individual customer account and columns representing various customer attributes and behaviors. The target variable "Churn" (0 = Not churned, 1 = Churned)

### Important Features and Their Significance

•	Account length: Duration of customer relationship

•	Area code: Geographic location indicator

•	International plan: Whether customer has international calling capabilities

•	Voice_mail_plan: Whether customer has voicemail services

•	Customer_service_calls: Number of calls to customer support

•	Total_day_minutes: Usage during daytime hours

•	Total_day_calls: Number of calls during the day

•	Total_eve_minutes: Usage during evening hours

•	Churn: The dependent variable indicating whether customer has left (1) or stayed (0)

### Data Limitations or Biases

•	Missing Customer Feedback Data: The dataset lacks qualitative feedback from customers who churned. Without direct customer input on reasons for leaving, we must infer causes from usage patterns, which may not capture the complete picture of customer dissatisfaction. 

•	Absence of Competitor Information: The data doesn't include information about competitor offers or market conditions that might have influenced customers to switch providers. This external context could be a significant factor in churn decisions.

•	Limited Demographic Information: While we have area codes, the dataset appears to lack deeper demographic details like age, income level, or household size. This limitation prevents analysis of how socioeconomic factors might influence churn patterns. 

•	Potential Sampling Bias: If the 3,333 customers analyzed don't represent a random sample of the entire customer base, certain customer segments might be over or underrepresented, skewing the results. 

•	Self-Reporting Bias in Customer Service Interactions: The customer service call data may not capture all customer dissatisfaction, as many unhappy customers never contact support before leaving. 

•	Inconsistent Measurement of Call Quality: While call duration is tracked, there appears to be no data on call quality or dropped calls, which could be significant factors in customer dissatisfaction, particularly for international calls. 

## Data Splitting and Preprocessing

### Data Cleaning

To ensure the quality of Echo Telecommunication's customer data, several cleaning procedures were implemented:

•	Duplicate customer records were identified and removed by cross-checking account identifiers

•	Outliers in call duration and frequency were verified against billing records to confirm their accuracy

•	Inconsistent categorization of customer service interactions was standardized into a uniform classification system

•	Records with logical inconsistencies (such as churned customers showing recent activity) were flagged for verification

•	Data entry errors in area codes were corrected by cross-referencing with geographic information systems

#### Handling Missing Values

The dataset contained several types of missing values that required different approaches:

•	Missing voicemail plan information was imputed based on voicemail usage patterns

•	For customers with missing call duration data, we used the mean values for customers with similar profiles

•	Where international calling data was incomplete, we used Excel's IF functions to determine if patterns in other months suggested international usage

### Data Transformations

Several transformations were performed to prepare the data for analysis:

•	Call minutes were standardized into daily averages to facilitate comparison

•	Customer tenure was converted from days to months for easier interpretation

•	Categorical variables like plan types were converted to dummy variables (0 or 1)

•	Customer service call frequencies were binned into categories (0, 1-3, 4-5, 6+)

•	Night call patterns were segmented into ranges (as seen in the dashboard: 33-52, 53-72, etc.)

•	Spending was normalized into daily averages and grouped into tiers ($0-10, $10-20, etc.)

### Data Splitting

The data was divided into independent and dependent variables as follows:

•	Dependent Variable (Target): Churn (binary variable: 0 = retained, 1 = churned)

•	Independent Variables (Features): 

o	Account length

o	Area code

o	International plan

o	Voice_mail_plan

o	Customer_service_calls

o	Total_day_minutes

o	Total_day_calls

o	Total_eve_minutes

o	Night_call_frequency

o	Daily_spending

This division allowed us to analyze how each feature individually and collectively influenced customer churn.

### Industry Context

This data comes from the telecommunications industry, where companies face tough competition, customers can easily switch providers, and keeping existing customers is crucial because the market is crowded, acquiring new customers is expensive, customers expect better service and pricing, and technology keeps changing how people use their phones.

### Stakeholders

Several key stakeholders will benefit from this analysis:

•	The Chief Executive, who directly oversees customer retention initiatives

•	Customer Service Department, responsible for addressing customer concerns

•	Product Development Team, who can design better plans based on usage patterns

•	Marketing Department, who can target retention campaigns to at-risk segments

•	Finance Team, who can better forecast revenue based on improved retention

•	Operations Team, who can optimize network resources based on usage patterns

### Value to the Industry

This analysis provides significant value to the telecommunications industry by:

•	Establishing clear relationships between service features and customer retention

•	Identifying specific thresholds of usage that correlate with higher churn risk

•	Demonstrating the importance of successful customer service resolution

•	Providing evidence-based strategies for pricing international calls more competitively

•	Creating a framework for ongoing customer behavior monitoring and proactive retention

•	Quantifying the financial impact of specific retention strategies

•	Showing how integrated data analysis can predict and prevent customer attrition

## Pre-Analysis

### Identify Key Trends

Several notable trends emerged during the preliminary data exploration:

•	Churn appears to follow a predictable pattern based on usage intensity, with moderate users (100-200 minutes) showing highest vulnerability

•	Customers without voicemail service show substantially higher churn rates, suggesting this service may increase retention 

•	Night call patterns show clear correlation with retention, with very high usage (93-112 calls) associated with increased churn

•	Frequent international callers (15-20 calls) represent a large segment of churned customers

•	Mid-tier spending ($30-40 daily) correlates with higher churn, suggesting possible price sensitivity in this segment

### Potential Correlations

Initial data exploration revealed several potential correlations:

•	Customers with voicemail plans tend to stay with the company as seen this in the "Churn Analysis by Voicemail Activity" chart showing 2,411 people without voicemail left. 

•	The more times a customer calls customer service, the more likely they are to leave (the data shows customers who called support 1-3 times had higher churn rates). 

•	Customers who make more international calls are much more likely to quit (59% of customers who left made 15-20 international calls). 

•	How much a customer uses the service affects whether they stay or go (customers using 100-200 minutes daily were most likely to leave). 

•	Night call patterns show a connection to churn (1,272 customers making 93-112night calls had higher churn rates). 

•	Spending level seems related to churn (mid-tier spenders paying $30-40 daily had the highest churn rates).

•	The length of time a customer has been with the company appears to affect their likelihood to stay. 

•	Customers who feel their issues aren't resolved after contacting support are more likely to leave.

### Initial Insights

Before deeper statistical analysis, several promising insights emerged:

•	Customer service quality appears to be a critical factor, with unresolved issues potentially driving churn

•	Service features like voicemail might serve as factors that increase customer loyalty

•	Usage patterns may identify at-risk customers before they decide to leave

•	Pricing strategies targeting specific usage tiers might have significant retention impact

•	International calling is one of the area that to focused attention

•	Night calling patterns suggest possible service quality or pricing issues during these hours

•	Middle-tier customers may feel they're not getting sufficient value for their spending

## In-Analysis

### Unconfirmed Insights

•	59% of churned customers made 15-20 international calls, suggesting high international call frequency correlates with churn

•	Customers who contacted customer service support 1-3 times had a higher churn rate

•	Customers who do not use voicemail services show significantly higher churn (2,411 churned customers without voicemail)

•	Night call frequency appears linked to churn, with 1,272 customers making 93-112night calls facing retention or service issues

•	Mid-tier spenders ($30-40 daily) have the highest churn rates

•	Customers using 100-200 total minutes daily experience the highest churn rates

### Recommendations

1.	Improve customer support services by ensuring faster resolutions and providing proactive outreach to at-risk customers
   
2.	Introduce affordable international call packages to reduce churn among frequent international callers
   
3.	Encourage voicemail adoption through improved functionality, incentives, or education
   
4.	Optimize night call plans for heavy night callers
   
5.	Revise pricing plans for mid-tier spenders through loyalty discounts and personalized plans
   
6.	Implement predictive churn models to identify at-risk customers
   
7.	Launch targeted retention strategies for moderate users (100-200 minutes daily)
   
8.	Regularly monitor customer feedback to identify emerging dissatisfaction points
   
### Analysis Techniques Used in Excel

•	Pivot tables to analyze relationships between variables

•	Charts and visualizations to identify patterns

•	Cross-tabulation to examine correlations between customer attributes and churn

•	Filtering and segmentation to isolate customer groups with similar behaviors

## Post-Analysis and Insights

### Key Findings

1.	Overall Churn Rate: The analysis confirmed a 14% churn rate (483 out of 3,333 customers), with 86% retention (2,850 active customers).
   
2.	International Calling Impact: 59% of churned customers made 15-20 international calls, validating the hypothesis that international calling is a major churn driver. This suggests high costs or quality issues with international service.
   
3.	Customer Service Effectiveness: Customers who contacted support 1-3 times had higher churn rates, indicating that service interactions may not be resolving customer concerns effectively.
   
4.	Voicemail as Retention Tool: Non-voicemail users had significantly higher churn (2,411 churned customers), confirming that voicemail adoption acts as a customer retention anchor.
   
5.	Night Call Patterns: 1,272 customers making 93-112night calls showed higher churn rates, highlighting potential issues with night call pricing or quality.
   
6.	Usage Threshold Effects: Customers using 100-200 total minutes daily experienced the highest churn, while very low and very high users were more stable, suggesting targeted pricing issues for moderate users.
   
7.	Spending Pattern Influence: Mid-tier spenders ($30-40 daily) had the highest churn, confirming their perception of being either overcharged or underserved.
   
### Comparison with Initial Findings

1.	Validated Expectation: The hypothesis that international calling influences churn was strongly validated, but the magnitude (59% of churned customers) exceeded initial expectations.
   
2.	Surprising Result: The negative correlation between customer service calls and retention was counter-intuitive. Initially, we expected that customers who engaged with support would feel more valued and stay. The data revealed the opposite, suggesting customer service interactions may not be resolving issues satisfactorily.
   
3.	Unexpected Threshold Effects: The specific usage thresholds that indicated higher churn risk (100-200 minutes, 93-112night calls) were more defined than anticipated, providing actionable targeting criteria.
   
4.	Counter-Intuitive Spending Pattern: The finding that both low-end and high-end spenders had better retention than mid-tier customers were surprising and contradicted the initial assumption that higher-paying customers would be more demanding.
   
5.	Voicemail Significance: The dramatic difference in churn between voicemail users and non-users was much stronger than initially hypothesized, highlighting the importance of this seemingly minor service feature.
   
6.	Surprising Regional Consistency: Unlike the initial hypothesis that suggested regional variations would influence churn, the data showed relatively consistent patterns across different area codes.
   
## Data Visualizations & Charts

![Dashboard4](https://github.com/user-attachments/assets/163c3dad-b77b-4ebe-a2df-c099ee2cc127)

### LINKS TO EXCEL DOCUMENTS AND DASHBOARD
 
 https://docs.google.com/spreadsheets/d/1plm-wWYIIDIRAYA6sWjKksyd5LXp3HXN/edit?usp=drive_link&ouid=104478848167416604596&rtpof=true&sd=true

### Explanation of Visualizations

•	Impact of International Calls on Churn: This bar chart compares customers who churned (1) versus those who didn't (0). It shows that 323 customers who made international calls churned, while 3,010 customers without international calling remained. This visualization illustrates how international calling affects retention.

•	Impact of Customer Support on Churn: This line graph shows how churn relates to the number of customer service calls (0-9 on x-axis). The peak at 1 call (1,181 customers) indicates many customers leave after just one support interaction. The declining trend shows fewer customers make multiple calls before churning, suggesting initial service interactions are critical.

•	Churn by Total Day Minute: This horizontal bar chart shows churn rates by daily usage. Customers using 100-200 minutes daily have the highest churn rate, followed by 200-300 minutes. Very low (0-100) and very high (300-400) usage customers are less likely to leave, indicating pricing may not align with moderate users' expectations.

•	Churn Analysis by Voicemail Activity: This bar graph compares churned customers without voicemail (0) versus those with voicemail (1). The dramatic difference (2,411 non-voicemail users churned vs. only 922 voicemail users) clearly shows voicemail subscription strongly correlates with retention.

•	Churn Rate by International Call: This pie chart breaks down churned customers by international call frequency. The largest segment (59%) represents customers making 15-20 international calls, followed by 38% making 10-14 calls. This visualizes how higher international call frequency correlates with increased churn.

•	Churn Analysis Trends Based on Night Calls: This horizontal bar chart shows churn patterns by night call frequency ranges. The highest churn (1,272 customers) occurs in the 93-112 calls range, followed by 73-92 calls (913 customers). This indicates certain night calling patterns may signal dissatisfaction.

•	Churn Rate Analysis: This pie chart provides a visual representation of the overall churn/retention split, with 14% churned and 86% retained , offering an immediate visual understanding of the company's customer retention performance.

•	Customer Churn Based on Day Charges: This bar chart shows churn by daily spending tiers. Middle-spending tiers ($30-40 and $20-30) show the highest churn (1,219 and 1,176 customers), while very low and very high spenders have better retention. This suggests pricing strategies may need adjustment for mid-tier customers.

## Recommendations and Observations

### Actionable Insights

•	Improve customer support services by ensuring faster resolutions ,training agents to handle complaints effectively and providing proactive outreach to at-risk customers.

•	Introduce affordable international call packages to reduce churn among frequent international callers, making it more cost-effective for them to stay.

•	Encourage voicemail adoption through improved functionality, offering incentives, educating customers on benefits.

•	Optimize night call plans by introducing customized packages for heavy night callers, improving network stability and call quality.

•	Revise pricing plans to better serve mid-tier spenders ($30-40 daily) by offering discounts, loyalty rewards, or personalized plans.

•	Implement predictive churn models using customer call patterns, spending habits, and support interactions to proactively engage customers showing signs of churn risk.

•	 Launch targeted retention strategies for exclusive offers for moderate users (100-200 minutes daily), loyalty programs for frequent callers, better incentives for active users.

•	Regularly monitor customer feedback and churn trends to identify emerging dissatisfaction points and take corrective action before churn increases.

### Optimizations or Business Decisions

•	Restructure customer service protocols to ensure issues are resolved on first contact

•	Develop targeted retention campaigns for customers showing early warning signs of churn

•	Consider revising the pricing strategy for mid-tier usage levels

•	Evaluate the international calling rate structure

•	Create loyalty programs specifically designed for customers in high-risk segments

### Unexpected Outcomes

Several surprising results emerged from the telecom churn analysis that weren't initially expected:

•	Voicemail non-users have dramatically higher churn rates, surprisingly, 2,411 customers who didn't use voicemail churned compared to only 922 who did use it.

•	Moderate usage customers (100-200 minutes) have the highest churn, unexpectedly, customers with moderate usage (not the lowest) were most likely to leave.

•	Both low-end and high-end spenders show lower churn rates, contrary to what might be expected, customers at both spending extremes ($0-10 and $50+) showed more loyalty.

•	Customers who contacted support 1-3 times had higher churn than those with more contacts, Counter-intuitively, moderate support users churned more than heavy support users.

•	Night call frequency strongly predicts churn, the strong correlation between night calls (93-112 range) and churn wasn't anticipated.

## Conclusion

This analysis revealed that customer churn at ECHO Telecommunication is influenced by multiple factors, including call behavior, spending patterns, and customer support interactions. The findings highlight the need for a more personalized customer retention approach that addresses specific pain points in the customer experience.

### Key Learnings

•	Echo Telecommunication experiences a 14% churn rate, with customer behavior patterns revealing clear risk indicators that can be used for targeted retention strategies.

•	Service usage patterns strongly predict churn: 

o	International call frequency (especially 15-20 calls) indicates high churn risk

o	Non-usage of voicemail significantly correlates with customer departure

o	Moderate usage customers (100-200 minutes daily) represent the highest risk segment

o	Night call volumes (93-112 calls) show strong correlation with customer loss

•	Customer support interactions reveal a critical insight: customers with 1-3 service contacts show higher churn rates, suggesting that initial problem resolution may be inadequate.

•	Spending patterns identified a vulnerable mid-tier segment ($30-40 daily), while both lower and higher spending customers showed greater loyalty.

•	The analysis confirms that churn is influenced by multiple interconnected factors rather than single variables, requiring a holistic approach to retention.

### Limitations

1.	The dataset only captures customer behavior at a specific point in time, limiting our understanding of how these patterns may evolve throughout the customer lifecycle.
   
2.	The analysis lacks qualitative data on customer satisfaction and the specific reasons for departure, which would provide deeper insights into the emotional and experiential factors driving churn.
3.	External factors such as competitor offers, market trends, and economic conditions that might influence churn decisions are not captured in the dataset.
   
4.	The data doesn't differentiate between customer segments based on demographics, contract length, or customer tenure, which may moderate some of the observed relationships.
   
5.	The analysis identifies correlations but cannot definitively establish causation between the observed behaviors and churn outcomes.
   
### Future Research
1.	Implement exit surveys to gather qualitative data on specific reasons for customer departure, providing context to the behavioral patterns identified.
   
2.	Perform longitudinal analysis tracking customer behavior changes over time to identify early warning signs before churn occurs.
	
3.	Conduct A/B testing of different retention strategies targeted at the identified risk segments to measure their effectiveness.
   
4.	Expand the dataset to include competitive intelligence and market trends to understand how external factors influence churn patterns.
   
5.	Develop a predictive churn model incorporating customer demographics, contract details, and service history alongside the behavioral variables analyzed.
   
6.	Investigate the relationship between customer acquisition channels and subsequent churn to optimize marketing efforts toward attracting more loyal customers.
   
7.	Analyze the financial impact of different churn segments to prioritize retention efforts based on customer lifetime value, not just churn probability.
   
## References & Appendices

### References

•	Data sources: Telecom Churn data from Kaggle.com.

•	Tools used: Microsoft Excel; Pivot Tables

### Appendices

•	Data Cleaning

Cleaning the dataset ensures accuracy and consistency in the analysis.

•	Removing Duplicates:

•	Used Remove Duplicates in Excel (Data → Remove Duplicates).

### Raw data explanations:

Independent Variables (Predictors)

•	Account length: Duration of customer's account with the company

•	Area code: Geographic identifier for customer location

•	International plan: Whether the customer has an international calling plan

•	Voice_mail_plan: Whether the customer has subscribed to voicemail services

•	Customer_service_calls: Number of calls made to customer service

•	Total_day_minutes: Amount of call time during daytime hours

•	Total_day_calls: Number of calls made during daytime hours

•	Total_eve_minutes: Amount of call time during evening hours

•	Total_night_minutes: Amount of call time during nighttime hours

Dependent Variable (Target): 

Churn:(0/1) showing whether the customer left the company or not

### Data Transformation

Transforming data helps in extracting useful insights.

•	Aggregating Churn by international call, Customer service call, voice mail activity, and night calls.

•	Created Pivot Tables for quick summarization.

•	Pivot tables were used to: 

•	Aggregate Churn by international call.

•	Compare churn rate by International call.

•	Identify trends in customer service call on churn.

•	Churn rate.

•	Retention rate.

### Data Splitting

Separating dependent and independent variables for focused analysis.

•	 Churn as Dependent Variable: Analyzed using trend analysis and correlation tests.

•	Independent Variables: International call, Customer service call, Voice mail activity, Night calls, Day charges were analyzed for impact on revenue trends.


