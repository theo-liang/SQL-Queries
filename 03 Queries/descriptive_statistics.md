```sql
SELECT	
	MIN(release_year) AS oldest_release_year,
	MAX(release_year) AS newest_release_year,
	MIN(rental_duration) AS min_rental_duration,
	MAX(rental_duration) AS max_rental_duration,
	AVG(rental_duration) AS avg_rental_duration,
	MIN(rental_rate) AS min_rental_rate,
	MAX(rental_rate) AS max_rental_rate,
	AVG(rental_rate) AS avg_rental_rate,
	MIN(length) AS min_length,
	MAX(length) AS max_length,
	AVG(length) AS avg_length,
	MIN(replacement_cost) AS min_replacement_cost,
	MAX(replacement_cost) AS max_replacement_cost,
	AVG(replacement_cost) AS avg_replacement_cost,
	MIN(last_update) AS oldest_update,
	MAX(last_update) AS latest_update,
	MODE() WITHIN GROUP (ORDER BY title) AS modal_title,
	MODE() WITHIN GROUP (ORDER BY release_year) AS modal_release_year,
	MODE() WITHIN GROUP (ORDER BY language_id) AS modal_language,
	MODE() WITHIN GROUP (ORDER BY rating) AS modal_rating,
	MODE() WITHIN GROUP (ORDER BY special_features) AS modal_special_features,
	MODE() WITHIN GROUP (ORDER BY fulltext) AS modal_fulltext
FROM film;	
```
