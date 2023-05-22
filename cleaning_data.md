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


Replacing Null Values with Zero 

CLeaning Null to Zero 
update allsessions
set "productPrice" = COALESCE( "productPrice", 0),
"totalTransactionRevenue" = COALESCE( "totalTransactionRevenue", 0),
transactions = COALESCE( transactions, 0),
"timeOnSite" = COALESCE( "timeOnSite", 0),
"productRefundAmount" = COALESCE( "productRefundAmount", 0),
"productQuantity" = COALESCE( "productQuantity", 0),
"productRevenue" = COALESCE( "productRevenue", 0),
"itemQuantity" = COALESCE( "itemQuantity", 0),
"itemRevenue" = COALESCE( "itemRevenue", 0),
"transactionRevenue" = COALESCE( "transactionRevenue", 0)

Second Table 
update analytics 
set "visitNumber" = COALESCE( "visitNumber", 0),
 "units_sold" = COALESCE( "units_sold", 0),
revenue = COALESCE( revenue, 0),
unit_price = COALESCE( unit_price, 0),
bounces = COALESCE( bounces, 0)


