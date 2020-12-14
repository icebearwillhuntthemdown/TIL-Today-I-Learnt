# Joins
- inner join
- left & right join
- full outer join (full join)
- cross join
- natural join
- self-join
<br/><br/>

## Inner join: 교집합
```sql
    select a
         , a_column
         , b
         , b_column
      from table_a
inner join table_b
        on a_column = b_column
```
- examines each row in the first table(table_a) with the condition in `on` clause 
- creates a new row that contains columns from both tables and adds this new row the result set
<br/><br/>

## Left & Right join
```sql
    select a
         , a_column
         , b
         , b_column
      from table_a
 left join table_b
        on a_column = b_colmn     
```
### how it works
1. when the condition evaluates to true, adds the columns of both tables with their data 
2. when the condition evaluates to false, fills the columns of the right table with null

### result set
- the LEFT JOIN selects all rows from the left table whether or not they have matching rows from the right table.
- the RIGHT JOIN selects all rows from the right table whether or not they have matching rows from the left table.
<br/><br/>

## Full [outer] join: 합집합
If the rows in the joined table do not match, the full outer join sets NULL values for every column of the table that does not have the matching row.
<br/><br/>

## Self join
```sql
select ...columns
from table a
inner join table b on a.id = b.id
```
### How it works
1. specify the same table twice with different table aliases
2. provide the join predicate after the `ON` keyword

### Use cases
1. hierarchical query
2. compare rows within the same table
<br/><br/>

## Cross join
모든 경우의 수
<br/><br/>

## Natural join
```sql
select ...columns
from table_a
natural [inner, left, right] join table_b
```
- implicit join using the common columns 
- doesn't require you to specify the join clause
- 조건절을 안 써도 알아서 두 테이블의 중복 컬럼을 기준으로 조인해줘서 편하다는 장점
- BUT, avoid using this whenever possible because sometimes it may cause an unexpected result.
<br/><br/>

### `ON` clause
- `USING (column_name)`
used when using a single column for join predicate, instead of repeating the column twice.

```sql
select a, b 
from table_a
inner join table_b
on using(order_id) // identical to 'a.order_id = b.order_id'
```


