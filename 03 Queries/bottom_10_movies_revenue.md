```sql
SELECT title AS movie_title, SUM(P.amount) AS revenue		
FROM film F				
INNER JOIN inventory I ON F.film_id = I.film_id				
INNER JOIN rental R ON I.inventory_id = R.inventory_id				
INNER JOIN payment P ON R.rental_id = P.rental_id				
GROUP BY title				
ORDER BY revenue ASC				
LIMIT 10;			
```
