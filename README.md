# Sales Insights Data Analytics Project.

## Understanding Business Problem.

* A Hardware Company which supplies computer hardware and peropherals is facing issues with tracking their sales and getting insights (Complete Picture) from the of market Computer Hardware which is growing dramatically.

## Stakeholders Expectations.

* After examinings the overall scope of the work, business objectives and information, the stakeholders are seeking a simple, understandable insights, specifically a dashboard which supports the latest insights from sales revenue and so on, so that they can take actual data driven descision based on this dashboard and so they can increase the sales of the company.

## Dataset.

* Looking at mysql database that is owned by the company, this database has all sales transactions, customers, products and markets information, using sql queries to do data analysis using the below statments:

`SELECT COUNT(*) FROM sales.transactions;`

  ![image](https://user-images.githubusercontent.com/62806731/206025036-04c8d6e6-a7e1-44bd-966c-f49f3d61f874.png) 
  
`SELECT * FROM sales.customers LIMIT 5;`
 
 ![image](https://user-images.githubusercontent.com/62806731/206120157-7678249e-95dd-4211-91be-8c9cff93014a.png)
 
`SELECT COUNT(*) FROM sales.customers;`

![image](https://user-images.githubusercontent.com/62806731/206120518-b9f3618f-3d6e-4d0d-bfc1-37c0d22aa3a7.png)

`SELECT * FROM sales.transactions WHERE market_code = 'Mark004';`

![image](https://user-images.githubusercontent.com/62806731/206288933-b831407f-f52c-45a4-a271-28f1e0d8d210.png)



