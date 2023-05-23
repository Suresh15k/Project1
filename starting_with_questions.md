Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
select sum ("transactionRevenue"), country, city from allsessions
group by country, city 
order by sum ("transactionRevenue")


Answer: Country is US and the city is sunnyvale




**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:
select avg ("productQuantity"), country, city from allsessions
group by country, city 
order by avg ("productQuantity")



Answer: the average number of products orderd is Mostly 1 for USA and its 10 for spain. 




**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:
select allsessions."v2ProductCategory", 
allsessions.city, allsessions.country, analytics.units_sold from allsessions 
join analytics ON analytics."visitId" = allsessions."visitId"
where analytics.units_sold >= 1
order by city, country


Answer: if not same, City and country have similar product catogeries orderd.  





**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:
with CTE as (select allsessions.city, 
 allsessions."productSKU", 
 Sum (analytics."units_sold") as units_sold
 from allsessions 
inner join analytics on allsessions."visitId" = analytics."visitId" 
group by allsessions.city, allsessions."productSKU"
),
max_product_country_CTE as (
select city, max (units_sold) as max_units_sold
from CTE 
group by city)

select * from CTE
inner join max_product_country_CTE as mpce on mpce.city = CTE.city and 
mpce.max_units_sold = CTE.units_sold
where units_sold > 0
order by CTE.city


Answer: I was getting the details of maximum sold PRODUCTSKU in each city 





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:
select city, country, "itemRevenue", "productRevenue", "transactionRevenue"  from allsessions
order by  "transactionRevenue" desc


Answer: most of the sales has happend in US country and perticularly sunnyvale city. 







