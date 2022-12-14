# Sales Insights Data Analytics Project.

Using the data analytics life cycle, going step by step for solving the business problem, these steps are:

1 - `Understanding Business Problem.`                                                                                                                           
2 - `Data Collecing.`                                                                                                                              
3 - `Data Processing and Preperation.`                                                                                                                                 
4 - `Data Preperation, Cleaning and ETL.`                                                                                                                              
5 - `Building and Sharing Dashboard.`                                                                                                                               
6 - `Stakeholders Feedback and Analysis Profit.`                                                                                                                     

### 1 - Understanding Business Problem.

A Hardware Company in India which supplies computer hardware and peropherals is facing issues with tracking their sales and getting insights (Complete Picture) from the of market Computer Hardware which is growing dramatically.

* ####  Stakeholders Expectations and Business Objectives.

   * After examinings the overall scope of the work, business objectives and information, the stakeholders are seeking a simple, understandable insights, specifically a dashboard which supports the latest insights from sales revenue and so on, so that they can take actual data driven descision based on this dashboard and so they can increase the sales of the company.

### 2 - Data Collecting.

The data required for the analsis is available at [MySQL](https://www.mysql.com/) database server that is owned by the company, this database has all sales transactions, customers, products and markets information, the initial appropriate method for the analysis is using SQL queries.

### 3 - Data Processing and Understanding.

For the data understanding part, using sql to determine data availability and explore data and it's characteristics, for this part we will strat using SQL Queries Statements:

```sql
SELECT COUNT(*) FROM sales.transactions;
```

![image](https://user-images.githubusercontent.com/62806731/206692756-d8b0f717-c4fc-4ff9-8809-b2087f58f07b.png)
  
```sql
SELECT * FROM sales.customers LIMIT 5;
```
 
![image](https://user-images.githubusercontent.com/62806731/206692840-23163a53-e468-42ec-9e2d-4528060e888a.png)
 
```sql
SELECT COUNT(*) FROM sales.customers;
```

![image](https://user-images.githubusercontent.com/62806731/206692926-ffe8b444-74e3-466b-b3e1-fa3c01b7ef33.png)

```sql
SELECT * FROM sales.transactions WHERE market_code = 'Mark004';
```

![image](https://user-images.githubusercontent.com/62806731/206693013-b2e2b644-e1b9-4791-80e7-fde53d4b46a1.png)

```sql
SELECT distinct product_code FROM sales.transactions WHERE market_code = 'Mark001';
```

![image](https://user-images.githubusercontent.com/62806731/206693101-d5e545c6-8671-41ed-aef4-0891a4295789.png)

```sql
SELECT * FROM sales.transactions where currency = 'USD';
```

![image](https://user-images.githubusercontent.com/62806731/206694006-3b33e0c6-90f7-4355-b529-6fc936abf7c9.png)



<details>
  
  <summary> <b> Click for more SQL Data Analysis Queries Statements! </b> </summary>
  
   <br/>
  
```sql
SELECT sales.transactions.*, sales.date.* FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date = sales.date.date where sales.date.year = 2020;
```

![image](https://user-images.githubusercontent.com/62806731/206700222-69497ba3-dbaf-4a28-a510-ee73c34ee5e2.png)

```sql
SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r";
```

![image](https://user-images.githubusercontent.com/62806731/206704761-e2a6740d-3c50-4ad0-8667-1ee00848b631.png)

```sql
SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date = sales.date.date WHERE sales.date.year = 2020 AND sales.date.month_name = 'January' and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");
```

![image](https://user-images.githubusercontent.com/62806731/206710339-4ddf3a3c-31bc-4e9b-af6c-1c4b89223253.png)

```sql 
SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date = sales.date.date WHERE sales.date.year = 2020 AND sales.date.month_name = 'January' and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r") AND sales.transactions.market_code = 'Mark001';
```

![image](https://user-images.githubusercontent.com/62806731/206710697-0c7a25dc-98ec-4438-a0c0-fb22c257cc3b.png)

</details>

## 4 - Data Preperation, Cleaning and ETL.

Start by plugging SQL Databse to MS Power BI, this process is also known as data munging or data wrangling, As appear from the SQL Queries the data is messy and contains some inconsistent values as `sales_amount` contains values in both `USD` and `INR` and these values need to be transformed to get the right results from the analysis.

- `Data Model and Star Schema as shown in Power BI`:

  ![image](https://user-images.githubusercontent.com/62806731/207005022-2eb030e1-d27e-4968-b274-ed687d8b8672.png)

  Start The ETL and Data Cleaning Process using `Power Query` to `connect`, `prepare` and `transform` our data, and the result of using Power Query will be the following:

   * Filtering the markets that only located in India.
   * Filtering all the `sales_amount` less than `1`.
   * Normalizing `sales_amount` values to `INR`.
   * Removing all duplicates records.

## 5 - Exploratory Analysis and Modeling (Building Dashboard):

* using [Power BI](https://powerbi.microsoft.com/en-au/), I created the following Dashboard:

![Screenshot 2022-12-21 174332](https://user-images.githubusercontent.com/62806731/208946051-b9c225ff-d00a-4b48-8513-a7655c5feb8e.png)


