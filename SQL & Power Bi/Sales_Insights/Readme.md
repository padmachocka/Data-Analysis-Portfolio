Steps Followed in this project
Learned about AIMS grid for project planning.

Used MySQL for retrieving the data from the database into Power BI.

Data Cleaning in power query.

Performed ETL process (Extract Transform and Load)

Created measure for needs and used them for creating visuals in PowerBi.

In the currency there were two types of currencies in transactions, performed currency conversion to make all the currency type same

Data Validation

Data Modelling and Visualization.

Major Changes/ Customizations Made
1.Solved the ‘(blank)’ problem for the products section by deleting the original products table and adding the self-modified products table (where I have added the Products ranging from Prod280 to Prod339 with their product type (random type- b/w ‘Own Brand’ and ‘Distribution’).

2.Merged the original modified ‘sales_transaction’ table with the new ‘sales_transaction’ table having profit margin, cost price, etc.

Insights
In this dashboard, we can see company has generated total revenue in 4 years ₹ 985M, total profit margin ₹24.7M, Profit margin% 2.5%, Sales Qty ₹2M. in 2020 company has generated total revenue of ₹ 142M by selling a total of 350K and earned a profit of ₹ 2.1M.

In 4 years Delhi NCR is our largest market in terms of revenue with ₹ 520M and total contribution of 52.8% with total revenue but if you look at the profit margin Delhi NCR is generating only 2.3% profit margin.

If we check the profit margin then here In 2020 Bhubaneshwar comes into the picture which is generating the highest profit margin of 10.48%. Similarly, if we can check the Profit Contribution % by Market then here Mumbai is the largest player with 23.89% of total contribution in total profit.

In 4 years Bengaluru generating the lowest profit margin of -20.8%.if we can check the Profit Contribution % by Market then here also Bengaluru is the Lower with -0.3% of total contribution in total profit.

In our top 5 customers, the Electricalsara Stores is our biggest customer who has generated total ₹ 413 M revenue generated in 4 years.

In our top 5 products,the Prod318 is our highest product has generated total ₹ 69M revenue generated in 4 years.

In product type Distribution has generated the revenue of ₹494M and ownbrand revenue is ₹494M generated in entire 4 years.

Revenue Trend is showing that in June 2020 revenue has been decreased drastically compared to the revenue last year and the profit margin was the least in April 2020.


Data Analysis Using SQL
Show all customer records

SELECT * FROM customers;

Show total number of customers

SELECT count(*) FROM customers;

Show transactions for Chennai market (market code for chennai is Mark001

SELECT * FROM transactions where market_code='Mark001';

Show distrinct product codes that were sold in chennai

SELECT distinct product_code FROM transactions where market_code='Mark001';

Show transactions where currency is US dollars

SELECT * from transactions where currency="USD"

Show transactions in 2020 join by date table

SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

Show total revenue in year 2020,

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

Show total revenue in year 2020, January Month,

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

Show total revenue in year 2020 in Chennai

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";
