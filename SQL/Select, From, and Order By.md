# Evaluation order
1. from
2. where
3. group by
4. having
5. select   * column alias is not available above select
6. distinct
7. order by
8. limit

## Select
- concatenator operator `||`
- `"column alias"` : `""` for alias with spaces
- all columns operator `*` 
    + not a good pratice due to performance issue
    + only use the asterisk shorthand when examining data
    + instead, explicitly specify the necessary column names 
- `DISTINCT`
    + multiple columns: returns the unique **combinations** of the specified columns
    + single column: returns unique values in the specified column
    +  `DISTINCT ON`: returns the **first row** amonst the unique combinations

## Order by
`ORDER BY sort_expressions [ASC | DESC] [NULLS FIRST | NULLS LAST]`
- order by multiple columns : sorts the rows by the first column, and then sorts the sorted column by the following columns.
- alias : because the `ORDER BY` is evaluated after `SELECT`, the column alias can be used in the `ORDER BY` clause
- default values
    - ASC by default
    - ASC -> NULLS LAST by default
    - DESC -> NULLS FIRST by default
