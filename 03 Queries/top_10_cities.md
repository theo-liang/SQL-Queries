```sql
SELECT		
	D.country,	
	C.city,	
	COUNT(customer_id) AS customer_count	
FROM customer A		
INNER JOIN address B ON A.address_id = B.address_id		
INNER JOIN city C ON B.city_id = C.city_id		
INNER JOIN country D ON C.country_id = D.country_id		
WHERE D.country IN		
	(	
		SELECT country
		FROM customer A
		INNER JOIN address B ON A.address_id = B.address_id
		INNER JOIN city C ON B.city_id = C.city_id
		INNER JOIN country D ON C.country_id = D.country_id
		GROUP BY country
		ORDER BY COUNT(customer_id) DESC
		LIMIT 10
	)	
GROUP BY country, city		
ORDER BY customer_count DESC		
LIMIT 10;
```		
