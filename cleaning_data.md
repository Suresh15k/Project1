What issues will you address by cleaning the data?
By cleaning the data i can form a primary keys and start to make a relational database.  Its useful to analyse and work on getting insights after cleaning the data. 


Queries:
Below, provide the SQL queries you used to clean your data.

# deleting duplicate visitor ID from allsessions to make it as an primary key 
select distinct "fullVisitorId", 
"channelGrouping",
time, 
country,
city,
"totalTransactionRevenue",
transactions,
"timeOnSite",
pageviews,
"sessionQualityDim",
date,
"visitId",
"type",
"productRefundAmount",
"productQuantity"
"productPrice", "productRevenue"
"productSKU", "v2ProductName", "v2ProductCategory", 
"productVariant", "currencyCode", "itemQuantity", "itemRevenue", 
"transactionRevenue", "transactionId", "pageTitle", "searchKeyword",
"pagePathLevel1","eCommerceAction_type","eCommerceAction_step","eCommerceAction_option" 
from allsessions AS als




