# Customer Churn Analysis Using SQL, Python and Tableau

![Cropped - Customer Churn Dashboard](https://user-images.githubusercontent.com/24312721/224085369-e520eb0f-3e8e-4168-9993-53af01f0ea90.png)

<p align="center">
<em> Customer Churn Dashboard (Tableau) - See link to Dashboard at the bottom of this page </em> 
  </p>
  
<br>
 
## Introduction 
Dollar Bank Customer Churn Analysis using SQL + Python + Tableau:  An end-to-end project that involved exploratory analysis with SQL, a deep-dive EDA using Python, and building an interactive dashboard with Tableau to present meaningful business insights for the bank. 

Dollar Bank was concerned that more and more customers were leaving its credit card services. They asked for a seasoned Data Analyst to analyze the problem for them in order to understand the main reasons for customers leaving the services. They also needed me to come up with recommendations for how the bank can mitigate further customer churns. Eventually, the bank wanted to proactively implement these recommendations in order to keep their customers happy.

## Data Description

In this task, a few datasets are provided:

### 1. BankChurners.csv
This file contains basic information about each client (**10 columns**):

- **CLIENTNUM** – Client number. Unique identifier for the customer holding the account.  
- **Attrition_Flag** – Internal event (customer activity) variable – if the client had churned (attrited) or not (existing).  
- **Dependent_Count** – Demographic variable – Number of dependents.  
- **Card_Category** – Product Variable – Type of Card (Blue, Silver, Gold, Platinum).  
- **Months_on_book** – Period of relationship with bank.  
- **Months_Inactive_12_mon** – No. of months inactive in the last 12 months.  
- **Contacts_Count_12_mon** – No. of contacts in the last 12 months.  
- **Credit_Limit** – Credit limit on the credit card.  
- **Avg_Open_To_Buy** – Open to buy credit line (average of last 12 months).  
- **Avg_Utilization_Ratio** – Average card utilization ratio.  

---

### 2. basic_client_info.csv
This file contains some basic client info per each client (**6 columns**):

- **CLIENTNUM** – Client number. Unique identifier for the customer holding the account.  
- **Customer_Age** – Demographic variable – Customer's age in years.  
- **Gender** – Demographic variable – M = Male, F = Female.  
- **Education_Level** – Demographic variable – Educational qualification of the account holder (e.g., high school, college graduate, etc.).  
- **Marital_Status** – Demographic variable – Married, Single, Divorced, Unknown.  
- **Income_Category** – Demographic variable – Annual income category of the account holder (`<40K, 40K–60K, 60K–80K, 80K–120K, >120K, Unknown`).  

---

### 3. enriched_churn_data.csv
This file contains enriched data about each client (**7 columns**):

- **CLIENTNUM** – Client number. Unique identifier for the customer holding the account.  
- **Total_Relationship_Count** – Total number of products held by the customer.  
- **Total_Revolving_Bal** – Total revolving balance on the credit card.  
- **Total_Amt_Chng_Q4_Q1** – Change in transaction amount (Q4 over Q1).  
- **Total_Trans_Amt** – Total transaction amount (last 12 months).  
- **Total_Trans_Ct** – Total transaction count (last 12 months).  
- **Total_Ct_Chng_Q4_Q1** – Change in transaction count (Q4 over Q1).

---

<br>

## Methodology
SQL queries were used to explore and understand the data, and joining all 3 datasets was critical in answering research questions to generate valuable insights for the business. 

Python deep-dive analysis took this a step further by drilling down into the data to understand the different variables, their datatypes, summary statistics, checking for outliers, and assessing both data quality and tidiness issues that required data cleaning. Performing a distribution analysis for each variable identified unique values and variables that showed potential in providing useful business insights. A cross-correlation analysis helped to check for the relationship between variables and identify variables of interests that can help solve the business problem at hand; which is the ultimate question for the bank - "Why are customers churning?" 



---

<br>


## Insights

<br>

![KPIs Only - Customer Churn Dashboard](https://user-images.githubusercontent.com/24312721/230170655-11755678-2998-4c2e-9a9c-72555ed84a82.png)

**Overall Churn Rate:** The overall churn rate is 16\%, which indicates that around one in six customers were churning. This is a key metric for the bank to continuously monitor in its effort to mitigate churn and increase customer retention.

**Transaction Amounts:** The dashboard also shows the average transaction amount for all customers is \$4,404, which suggests that the bank's customer base includes customers with a range of spending levels. However, the average transaction amount for churned customers is \$3,095, which is significantly lower than the average for all customers. This may indicate that customers who spend less money on transactions are more likely to churn, perhaps because they are not as invested in the bank's services or do not find them as useful. The bank may want to consider strategies for encouraging customers to increase their transaction amounts in order to improve retention rates. For example, they could offer rewards programs or incentives for customers who maintain high transaction volumes or balances. Alternatively, they could explore ways to improve their services or product offerings to make them more attractive to customers with lower transaction amounts.

<br>

<br>


![Customer Churn Demographics](https://user-images.githubusercontent.com/24312721/230170768-b0b97eb6-208a-4f3b-ad44-c6b97fc0a4f7.png)

**Customer Demographics:** Overall, the average customer age is 46 yrs, and there are more female customers than male customers, with the majority of customers in the 41-50 age range. The churn summary indicates that female clients also aged between 41-50 have the highest churn rate, with 4.4\% of the 2461 female clients in this age group having churned, compared to 3.3\% of the 2191 male clients in the same age group. Overall, the churn rate is higher for females at 9.2\% across all age groups, compared to 6.9\% for males across all age groups. 

According to the analysis, established customers (those who have been with the bank for 25 to 36 months) have the highest churn rate at 5\% for females and 3.6\% for males. The second-highest churn rate is seen in long-term customers (those with the bank for 37-48 months), with rates of 2.8\% for females and 2.3\% for males. 

The analysis also shows that the largest number of churned customers were female blue credit card holders earning less than \\$40k, with a total count of 559. The second highest count, at 215, were male blue credit card holders earning between \$80k -\$120k. However, a majority of customers across all income categories owned blue credit cards. Both male and female customers who churned were established and long-term customers of the bank. Male blue cardholders had churn counts ranging from 97 to 215 across income categories of \$40k -\$120k+, with all churned male blue cardholders being established and long-term customers of the bank.

This information can be used to tailor marketing and communication efforts to specific demographic groups to mitigate customer churn and increase customer retention.

<br>

<br>


![Visualizing customer spending behaviours](https://user-images.githubusercontent.com/24312721/230170857-a811bbf2-0776-4e12-b8df-ebf46363f200.png)


**Customer Behavior:** Visualizing customer spending behaviors and connection to churn reveals that customers with higher number of transactions and higher transaction amounts are less likely to churn. Additionally, the scatter plot shows that customers who churned made less than 100 transactions and typically spent less than 5K before churning, regardless of income category. This suggests that offering incentives for customers to maintain high levels of activity and transaction amounts may be an effective retention strategy.

<br>

<br>


![Paretor Analysis of Customers](https://user-images.githubusercontent.com/24312721/230170946-475b706b-8f35-4b7e-8598-fce1ca3032f6.png)


**Short-Term vs Long-Term Focus:**
Vital few - The Pareto analysis reveals that around 20\% of the total churned customers are responsible for approximately 80\% of the total churn. This means that a small subset of customers is responsible for the majority of customer churn.
Customer segments: The dashboard identifies two customer segments that constitute the vital few: female graduates who are married or single, and male graduates who are single. This suggests that Dollar Bank may need to pay special attention to these customer segments to reduce churn.

---

<br>


## Recommendations
The analysis highlights the need for the bank to focus on retaining its established and long-term customers in all income categories, especially female blue cardholders earning less than \$40k.
By focusing on the vital few customer segments, Dollar Bank can reduce the overall churn rate to less than 7\%, which is a generally acceptable churn rate level for most banks and credit card companies. The vital few of around 20\% can be increased to 30\% of the total churned customers to capture more customers segments and further reduce churn.

Targeted marketing ad campaigns should be used to effectively reach the customer segments contributing the most to churn. Examples of such campaigns include: 
 
- Providing financial education and resources to both male and female graduates, such as webinars, podcasts, or blog posts, to help them manage their finances more effectively, improve their financial literacy, and pay back student loans and other expenses without running into debt.
- Partnering with brands that appeal to the target audience (e.g partnering with fitness brands and offering discounts on gym memberships or workout gears to male and female graduates who are married or single)
- Creating a loyalty program specifically for established and long-term customers, which could include perks such as waived fees, free financial planning sessions, or personalized investment advice.
- Providing personalized investment advice and retirement planning services to established and long-term customers, which could help them maximize their savings and achieve their long-term financial goals.
- Offering credit counseling services to blue credit card holders who earn less than \\$40k per year, which could help them improve their credit scores and reduce their financial stress.
- Rewards and incentives e.g sign-up bonuses, discounted interest rates on loans or cash back rewards on purchases, to increase credit card usage and attract new customers to the bank

