# Customer-Churn-Analysis-Dashboard
Customer Churn Analysis using Tableau.
**1. INTRODUCTION :**
1.1	Project Name : ‘CUSTOMER CHURN ANALYSIS’

1.2	 Team Composition:  ‘Solo Project’
	‘The Lone Analyst’ - Akshay Gidde (732392024)

1.3 Project Overview:
- The project focuses on analysing customer churn within a Telecommunications company based in California during Q2 2022. The dataset comprises information on 7,043 customers, with each record representing a unique customer. It includes demographic data, location details, tenure, subscription services, and the customer's status for the quarter (joined, stayed, or churned), among other information.
- Our objective is to identify potential reasons for customer churn utilizing visualization techniques. We aim to create a comprehensive dashboard containing essential charts and graphs that highlight these potential factors.

1.4 Software Used :
	‘Tableau : Desktop’

DATA SOURCE : https://www.kaggle.com/datasets/shilongzhuang/telecom-customer-churn-by-maven-analytics : Kaggle website.


**2. OBJECTIVES:**
- Our main goals are to understand how telecom customers behave in California and to solve any business challenges we find.
- To tackle this, we want to figure out why customers are leaving the company, making it easier to understand what's driving their decisions.
- We also plan to create a dashboard with visuals that make it simple for everyone to understand the important data.
Problem Statement:
- Our big question is why customers are leaving our telecom company. We need to understand what's causing them to go elsewhere.
Project Outcomes:
- At the end of our project, we hope to have ideas to stop customers from leaving. We'll also sort customers based on why they leave, so we can give them the right kind of help.
Lastly, we'll put together a report that's easy to understand and tells a clear story about what we found.
3. ANALYSIS :
	Analysis As per CRISP – DM model is as follows :

**3.1 BUSINESS UNDERSTANDING :**
- In line with the CRISP-DM model, our initial focus is on understanding the business context surrounding the telecommunications company in question.
- We begin with the assumption that this telecom company operates similarly to others, providing standard phone and internet services to its customers. Additionally, the company offers various supplementary services aimed at enhancing customer experience, such as different types of internet connections, streaming options, cloud storage, online backup, security features, premium tech support, and unlimited data. Within its phone services, the company also offers multi-line phone service.
- Our understanding of the business is based on the data provided by Kaggle and additional information available on their website.

**3.2 DATA UNDERSTANDING :**
- Our understanding of the data is that it has been curated and provided by the data engineer through the ETL (Extract, Transform, Load) pipeline. The dataset is specifically tailored for customer churn analysis and contains essential information regarding customer attributes, behaviours, and interactions with the company's services.
- We assume that the dataset encompasses all the necessary variables required to conduct a comprehensive churn analysis, enabling us to delve deep into understanding customer behaviour and factors contributing to churn.

**Understanding Each Column in data :**
	As data with context becomes information we studied in DIKW pyramid
Columns :
1.	Customer ID : A unique ID that identifies each customer
2.	Gender : The customer's gender: Male, Female
3.	Age : The customer's current age, in years, at the time the fiscal quarter ended (Q2 2022)
4.	Married : Indicates if the customer is married: Yes, No
5.	Number of Dependents : Indicates the number of dependents that live with the customer (dependents could be children, parents, grandparents, etc.)
6.	City : The city of the customer's primary residence in California
7.	Zip Code : The zip code of the customer's primary residence
8.	Latitude : The latitude of the customer's primary residence
9.	Longitude : The longitude of the customer's primary residence
10.	Number of Referrals : Indicates the number of times the customer has referred a friend or family member to this company to date
11.	Tenure in Months : Indicates the total amount of months that the customer has been with the company by the end of the quarter specified above
12.	Offer : Identifies the last marketing offer that the customer accepted:
	   None, Offer A, Offer B, Offer C, Offer D, Offer E
13.	Phone Service : Indicates if the customer subscribes to home phone service with the company: Yes, No
14.	Multiple Lines : Indicates if the customer subscribes to multiple telephone lines with the company: Yes, No (if the customer is not subscribed to home phone service, this will be No)
15.	Internet Service : Indicates if the customer subscribes to Internet service with the company: Yes, No (this is basic service and all other internet related services are depended on this if customer haven’t taken this service then by default services which are dependent on internet service will be null means ‘No’ )

	BELOW SERVICES ARE DEPENDENT ON INTERNET AND IF CUSTOMER NOT SUBSCRIBED TO INTERNATE SERVICE THEN THOSE WILL BE NULL OR ‘No’

16.	Internet Type : Indicates the customer's type of internet connection: DSL, Fibre Optic, Cable (if the customer is not subscribed to internet service, this will be None.
17.	Avg Monthly GB Download : Indicates the customer's average download volume in gigabytes, calculated to the end of the quarter specified above (if the customer is not subscribed to internet service, this will be 0)
18.	Online Security : Indicates if the customer subscribes to an additional online security service provided by the company: Yes, No (if the customer is not subscribed to internet service, this will be No)
19.	Online Backup : Indicates if the customer subscribes to an additional online backup service provided by the company: Yes, No (if the customer is not subscribed to internet service, this will be No)
20.	Device Protection Plan : Indicates if the customer subscribes to an additional device protection plan for their Internet equipment provided by the company: Yes, No (if the customer is not subscribed to internet service, this will be No)
21.	Premium Tech Support : Indicates if the customer subscribes to an additional technical support plan from the company with reduced wait times: Yes, No (if the customer is not subscribed to internet service, this will be No)
22.	Streaming TV : Indicates if the customer uses their Internet service to stream television programming  from a third party provider at no additional fee: Yes, No (if the customer is not subscribed to internet service, this will be No)
23.	Streaming Movies : Indicates if the customer uses their Internet service to stream movies from a third party provider at no additional fee: Yes, No (if the customer is not subscribed to internet service, this will be No)
24.	Streaming Music : Indicates if the customer uses their Internet service to stream music from a third party provider at no additional fee: Yes, No (if the customer is not subscribed to internet service, this will be No)
25.	Unlimited Data : Indicates if the customer has paid an additional monthly fee to have unlimited data downloads/uploads: Yes, No (if the customer is not subscribed to internet service, this will be No)
27.	Contract : Indicates the customer's current contract type: Month-to-Month, One &  Two Year
28.	Paperless Billing : Indicates if the customer has chosen paperless billing: Yes, No
29.	Payment Method : Customer pays their bill: Bank Withdrawal, Credit Card, Mailed Check
30.	Monthly Charge : Indicates the customer's current total monthly charge for all their services from the company
31.	Avg Monthly Long Distance Charges : Indicates the customer's average long distance charges, calculated to the end of the quarter specified above (if the customer is not subscribed to home phone service, this will be 0)
32.	Total Charges : Indicates the customer's total charges, calculated to the end of the quarter specified above
33.	Total Refunds : Indicates the customer's total refunds, calculated to the end of the quarter specified above
34.	Total Extra Data Charges : Indicates the customer's total charges for extra data downloads above those specified in their plan, by the end of the quarter specified above
35.	Indicates the customer's total charges for long distance above those specified in their plan, by the end of the quarter specified above
36.	Total Revenue : 
(Total Charges - Total Refunds + Total Extra Data Charges + Total Long Distance Charges)
Indicates the company's total revenue from this customer, calculated to the end of the quarter specified above 
36.	Churn Category : A high-level category for the customer's reason for churning, which is asked when they leave the company: Attitude, Competitor, Dissatisfaction, Other, Price (directly related to Churn Reason)
37.	Churn Reason : A customer's specific reason for leaving the company, which is asked when they leave the company (directly related
38.	Customer Status : Indicates the status of the customer at the end of the quarter: Churned, Stayed, or Joined

THIS DATASET BRODLY CONTAINS THE DATA OF CUSTOMER’S DEMOGRAPHIC,GEOGRAPHIC, PAYMENT RECORDS, CHURN FEEDBACK, SERVICES USAGE ETC

**3. 3 DATA PROCESSING :**
- We will conduct the entire analysis and create the dashboard using Tableau, a platform renowned for its extensive graphing capabilities and dynamic visualizations, facilitating better understanding of the data.
- Within the dataset, the "Customer Status" column serves as a crucial indicator of churn status.
- However, it also includes a new value, "Joined," denoting newly acquired customers. Since our primary focus is on churn analysis and identifying potential churn factors, we will exclude the 314 rows where the status is labelled as "Joined."
- Additionally, due to insufficient understanding of the "Average Monthly Long Distance Charges" column, we have decided to conceal this column within the Tableau dataset.



**HANDLING NULL VALUES :**
-	Churn Category Column: The "Churn Category" column contains null values, indicating that customers left without providing a reason. To address this, we filled these null values with "No reason" and created a new calculated field to capture this information.
-	Internet Services Dependencies: Columns dependent on basic internet services are affected by null values. For instance, if a customer doesn't have internet service, then other related services would also be absent. To handle this, we filled these null values with "No" by creating a new calculated field.
Internet Dependent columns : 
	[ Internet Type, Average Monthly GB Download, Online Security, Online Backup, Device Protection Plan, Premium Tech Support, Streaming TV, Streaming Movies, Streaming Music, Unlimited Data ]
	Null data in this column is due to customer is not subscribed to the basic internet service then by default it is ‘No’. So, we have filled it with No wherever it is null.

-	Churn Rate Calculation: We created a new calculated field called "Churn Rate," representing the percentage of total customers who churned. This metric aids in further analysis of churn patterns.
-	Customer Count: We utilized the "Customer ID" column to calculate the total customer count, providing essential context for our analysis.
-	Age Grouping: To simplify analysis based on age, we created five age bins to group customers by age range.


**3.4 DATA VISUALISATION**

•	KPI’s :
We've created several key performance indicators (KPIs), including the total number of customers, total churned customers, and the gender ratio.

**CHART EXPLANATION :**

•	Percentage of Churn Reasons: 
	This chart illustrates the percentage breakdown of each churn reason out of the total churn cases, providing insights into the primary drivers of customer attrition.

•	Contract & Payment Method Affecting Churn: 
	This visualization displays the churn rate based on customer tenure, offering insights into how contract and payment method choices impact customer churn over time.

•	Internet Type vs Churn Rate: 
	This chart showcases the churn rate across different types of internet services, highlighting which internet types experience higher churn rates.

•	Churn by Age: 
	Here, we observe how churn rates vary across different age groups, helping us understand the relationship between age and churn behaviour.

•	Churn By Dependents: 
	This visualization examines how churn rates change as the number of dependents increases. We filtered out dependencies greater than three to prevent heavy skewing of percentages due to limited data.

•	Last Offer vs Churn Rate: 
	This chart reveals the percentage of customers who churned among those who accepted the last offer, providing insights into the effectiveness of different offers in retaining customers.

•	Churn Rate vs Contract : 
	This chart illustrates the churn rate across three categories of subscription contracts. It provides insight into how different contract types correlate with customer churn, allowing for a comparison of churn rates among these contract categories.


**CLICKABLE BUTTONS / FILTERS :** 

•	Churn Categories: 
	This filter consists of five buttons/categories representing different churn reasons. Each category provides information on the number of customers churned within that specific reason. It enables us to sort the entire dashboard based on the selected category, allowing for focused analysis.

•	Customer by Reasons: 
	This filter contains three categories based on the contract type of the customers with the company. It allows us to sort the entire dashboard according to the selected contract type, facilitating targeted analysis.

Additionally, every element of each graph on the dashboard is interactive, serving as a filter itself. This interactivity empowers users to sort and interpret data at the most granular level and in a manner that best suits their needs.


**4 . ANALYTICS**
- In this section, we delve into insights gleaned from our analysis, which will inform our recommendations.

**4.1 INSIGHTS / INTERPRETATIONS**
1.	Overall Churn Rate : The overall customer churn stands at 1869, constituting a churn rate of 26.54%.
2.	Gender Impact : Both male and female customers contribute equally to churn rates.
3.	Contract and Payment Method Influence : Customers on month-to-month contracts who opt for bank withdrawal payment methods exhibit a higher churn rate of approximately 53%, particularly after 19 months of service.
4.	Internet Service Type : Fibre optic internet service subscribers demonstrate a churn rate of 41%.
5.	Churn Categories : "Competition" and "Attitude" emerge as the top two churn categories.
6.	Dominant Churn Categories : "Competition" and "Attitude" collectively account for approximately 60% of total churn reasons, underscoring their significant impact.
7.	Offer E Impact : Among customers who accepted offers before churning, approximately 53% of those who opted for "offer E" ultimately left.
8.	Dependency Impact : Customers without dependencies exhibit a higher churn rate of around 33%. However, even a single dependency significantly reduces the churn rate to 7% and continues to decrease further. Note: Dependencies over 3 were filtered due to low row count in that category.
9.	Month-to-Month Contracts : Month-to-month contracts contribute to approximately 15% of total churn, indicating higher churn propensity in this contract type.

 These insights offer valuable information for formulating recommendations aimed at reducing churn and improving customer retention strategies.


**4.2 RECOMMENDATION**
1.	Comparing the churn rate of 26.54% with the industry average of around 30%, efforts should be made to maintain healthy customer relationships and gradually improve churn rates over time.
2.	No gender-specific churn patterns were observed, as both male and female numbers are the same.
3.	For customers on month-to-month contracts who pay via bank withdrawal and exhibit a high churn rate of 53% after 19 months of service: Scope of improvement in 'bank withdrawal' payment can be done and customers can be promoted to auto credit card transactions to reduce churn. Additionally, special offers can be extended to customers nearing the 19-month mark to encourage retention.
4.	With 41% of customers who have opted for Fibre Optics Internet leaving, there may be issues with the service or internet speed quality that need to be addressed.
5.	Improving support personnel's view and attitude towards customers during consultations is crucial, as it contributes to around 17% of total churn.
6.	Monitor competitors' actions closely and make necessary organizational changes to enhance the overall competitive experience for customers.
7.	Investigate the effectiveness of 'Offer E', as approximately 53% of customers who accepted this offer ultimately churned. Consider adding incentives or bonuses to Offer E to incentivize customer retention after acceptance.
8.	Launch family offers, coupons, or community features to encourage customers to onboard family members. Increasing dependencies within accounts can significantly reduce churn rates, as observed in solo versus dependent accounts.

