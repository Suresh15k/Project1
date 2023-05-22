Question 1: which mode of visitors ( ChannelGrouping ) generated more revenue 

SQL Queries:
select sum (revenue),"channelGrouping"  from analytics
group by "channelGrouping"
order by sum (revenue) desc


Answer: refferal, Direct & organic search created more revenue 




Question 2: which type of transcations happend most 

SQL Queries:
select count ("totalTransactionRevenue"), type from allsessions

group by type

Answer: Most of the transcations happend through Page 



Question 3: 

SQL Queries:

Answer:



Question 4: 

SQL Queries:

Answer:



Question 5: 

SQL Queries:

Answer:
