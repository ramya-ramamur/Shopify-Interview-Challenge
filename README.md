# Shopify-Interview-Challenge
This is an exercise for the Shopify Interview Challenge. Details as follows.

# Fall 2022 Data Science Intern Challenge 

Please complete the following questions, and provide your thought process/work. You can attach your work in a text file, link, etc. on the application page. Please ensure answers are easily visible for reviewers!


### Question 1: Given some sample data, write a program to answer the following: [click here](https://github.com/ramya-ramamur/Shopify-Interview-Challenge/blob/main/Shopify_Challenge_Question_1/2019%20Winter%20Data%20Science%20Intern%20Challenge%20Data%20Set.xlsx) to access the required data set

On Shopify, we have exactly 100 sneaker shops, and each of these shops sells only one model of shoe. We want to do some analysis of the average order value (AOV). When we look at orders data over a 30 day window, we naively calculate an AOV of $3145.13. Given that we know these shops are selling sneakers, a relatively affordable item, something seems wrong with our analysis. 

Think about what could be going wrong with our calculation. Think about a better way to evaluate this data. 
What metric would you report for this dataset?
What is its value?

#### **Solution:**

Data Exploration and Transformation
1. Data was pulled from an excel file and transferred to a pandas dataframe called "sneaker_shop" The dataset was examined for null values, dulicate data and outliers. 
<img width="670" alt="Screen Shot 2022-05-20 at 4 34 06 PM" src="https://user-images.githubusercontent.com/75961057/169624670-c119c1d4-1c3b-453b-9b36-f11adbd6a67e.png">

3. Unneeded columns "order_id", "user_id", "payment_method", "created_at" was dropped to create a new dataframe that had "shop_id", "order_amount", and "total_items"
4. A metric of Average Order Value was added as a column to the dataframe after  

**Observations:**
1. The original calculation for AOV (given in problem statement) seems to have just taken the mean (3145.13) of the order_amount without taking into account total_items ordered. The standard deviation and max value is also very high indicating there are some outliers. See summary statistics below. 
<img width="646" alt="Screen Shot 2022-05-20 at 4 17 39 PM" src="https://user-images.githubusercontent.com/75961057/169623722-8316abf2-e7cb-4d55-bd76-d0659694b7d0.png">
2. Shop no 42 was the only shop with orders  more than 2000. Orders at the other shops are usually between 1-10 in the 30 day window. However since the  Average value (AOV) per order for shop 42 is 352 which lies in the "a relatively affordable item" spectrum.  There does not seem to be any anomaly.
3. There is one outlier - shop_id 78 with 46 orders with AOV of 25725 that is substantially higher than the other data points.

### Question 2: For this question you’ll need to use SQL. Follow this [link](https://www.w3schools.com/SQL/TRYSQL.ASP?FILENAME=TRYSQL_SELECT_ALL) to access the data set required for the challenge. Please use queries to answer the following questions. Paste your queries along with your final numerical answers below.

#### [SQL Question 1](https://github.com/ramya-ramamur/Shopify-Interview-Challenge/blob/main/SQL/SQL_Question_1.png)
* **How many orders were shipped by Speedy Express in total?**
<img width="1173" alt="SQL_Question_1" src="https://user-images.githubusercontent.com/75961057/169365280-0514d460-6b56-4586-822b-5899a7d3e691.png">

#### [SQL Question 2](https://github.com/ramya-ramamur/Shopify-Interview-Challenge/blob/main/SQL/SQL_Question_2.png)
* **What is the last name of the employee with the most orders?**
<img width="1178" alt="SQL_Question_2" src="https://user-images.githubusercontent.com/75961057/169365400-3221866f-74c1-4358-83aa-3c7b19ac84d3.png">

#### [SQL QUESTION 3](https://github.com/ramya-ramamur/Shopify-Interview-Challenge/blob/main/SQL/SQL_QUESTION_3.png)
* **What product was ordered the most by customers in Germany?**

<img width="592" alt="Screen Shot 2022-05-19 at 11 45 16 AM" src="https://user-images.githubusercontent.com/75961057/169376956-944889f0-1b87-4df4-8788-c7a325421edb.png">

<img width="1178" alt="SQL_Question_3" src="https://user-images.githubusercontent.com/75961057/169377008-c7213d41-98fc-4c7c-a470-1eecbbdfd0c3.png">
