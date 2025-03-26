# log_20250326

Q.  from 123, 12 to 00123, 00012
A. Java -> String.format("%05d", num);
   Python -> f"{num:05d}" 
   
Q.  customer table
 customer_id, customer_name

 order table
 id, order_detail, customer_id
 
10+ orders customer?

A. 
SELECT
    customer.customer_id,    
    customer.customer_name,    
    COUNT(orders.id) AS order_count
FROM
    Customer customer
JOIN
    Orders orders ON customer.customer_id = orders.customer_id
WHERE
    orders.customer_id > 10
GROUP BY
    Customer.customer_id, Customer.customer_name;

    
