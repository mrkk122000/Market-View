#  Project : Market-view of Data Analysis

The problem was that all thses thing happening is verbal and these was mo proof with facts that how his business is affected and which made him frustraed as he can see that overall sales is declining but when he can ask regional manager, he is not getting complete picture of this bussiness and when he and this AtliQ hardware is big business. so to see insights clearly. and he will get proper insights anbd can take data driven decision to increase sales of hos company.
All he wants is a simple data visualization tool which he can access on daily basis. By using such tools and technology one can make data driven decisiions which helps to increase the sales of the company. So, In this projects we will help a company make its own sales related dashboard using power BI.
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

Show total revenue in year 2020, Janua0ry Month,

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

Show total revenue in year 2020 in Chennai

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";

Data Analysis Using Power BI
Formula to create norm_amount column
= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*86 else [sales_amount], type any)
