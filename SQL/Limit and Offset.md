# Limit and Offset
 - `LIMIT`: limits the number of rows of the result set
 - `OFFSET`: skips the given number of rows before the result set
 - should be used with `ORDER BY`

* syntax
```sql
SELECT columns
  FROM table
 LIMIT n OFFSET m
```

* example
```sql
  select film_id
       , title
    from film
order by film_id
   limit 4 offset 3;
```
<br/><br/>
 
 ## `FETCH`
 `LIMIT` and `FETCH` are identical, but `FETCH` is **SQL standard** while `LIMIT` isn't.

* syntax
```sql
OFFSET n rows
FETCH FIRST n ROWS only
```

* example
 ```SQL
  select film_id
       , title
    from film
order by title
  offset 5 rows
   fetch first 5 row only
 ```

