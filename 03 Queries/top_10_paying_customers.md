```sql
SELECT first_name, last_name, country, city, SUM(P.amount) AS total_amount_paid			
FROM customer C					
INNER JOIN address A ON C.address_id = A.address_id					
INNER JOIN city CI ON A.city_id = CI.city_id					
INNER JOIN country CO ON CI.country_id = CO.country_id					
INNER JOIN payment P ON C.customer_id = P.customer_id					
GROUP BY first_name, last_name, country, city					
ORDER BY total_amount_paid DESC					
LIMIT 10;					
```
