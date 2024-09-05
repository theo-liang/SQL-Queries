```sql
SELECT name, COUNT(R.inventory_id) AS film_inventory, SUM(amount) AS revenue			
FROM payment P					
INNER JOIN rental R ON P.rental_id = R.rental_id					
INNER JOIN inventory I ON R.inventory_id = I.inventory_id					
INNER JOIN film F ON I.film_id = F.film_id					
INNER JOIN film_category FC ON F.film_id = FC.film_id					
INNER JOIN category C ON FC.category_id = C.category_id					
GROUP BY name					
ORDER BY revenue ASC					
LIMIT 10;
```
