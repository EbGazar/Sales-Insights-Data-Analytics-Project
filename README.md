# Sales Insights Data Analytics Project.

## Understanding Business Problem.

* A Hardware Company which supplies computer hardware and peropherals is facing issues with tracking their sales and getting insights (Complete Picture) from the of market Computer Hardware which is growing dramatically.

## Stakeholders Expectations.

* After examinings the overall scope of the work, business objectives and information, the stakeholders are seeking a simple, understandable insights, specifically a dashboard which supports the latest insights from sales revenue and so on, so that they can take actual data driven descision based on this dashboard and so they can increase the sales of the company.

## Dataset.

* Looking at mysql database that is owned by the company, this database has all sales transactions, customers, products and markets information, using sql queries to do data analysis using the below statments:

`SELECT COUNT(*) FROM sales.transactions;`

![image](https://user-images.githubusercontent.com/62806731/206692756-d8b0f717-c4fc-4ff9-8809-b2087f58f07b.png)
  
`SELECT * FROM sales.customers LIMIT 5;`
 
![image](https://user-images.githubusercontent.com/62806731/206692840-23163a53-e468-42ec-9e2d-4528060e888a.png)
 
`SELECT COUNT(*) FROM sales.customers;`

![image](https://user-images.githubusercontent.com/62806731/206692926-ffe8b444-74e3-466b-b3e1-fa3c01b7ef33.png)

`SELECT * FROM sales.transactions WHERE market_code = 'Mark004';`

![image](https://user-images.githubusercontent.com/62806731/206693013-b2e2b644-e1b9-4791-80e7-fde53d4b46a1.png)

`SELECT distinct product_code FROM sales.transactions WHERE market_code = 'Mark001';`

![image](https://user-images.githubusercontent.com/62806731/206693101-d5e545c6-8671-41ed-aef4-0891a4295789.png)

