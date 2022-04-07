# Big Data-mining

Practice examples using Hadoop streaming and python with the lineorder table

SELECT lo_quantity, AVG(lo_revenue)
	FROM (SELECT lo_revenue, MAX(lo_quantity) as lo_quantity,
                                 MAX(lo_discount) as lo_discount
              FROM lineorder
              WHERE lo_orderpriority LIKE '%URGENT'
              GROUP BY lo_revenue)              
	WHERE lo_discount BETWEEN 4 AND 9
	GROUP BY lo_quantity;

