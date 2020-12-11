## Evaluation order
1. from
2. select
3. order by

## Select
- concatenator operator `||`
- `"column alias"` : `""` for alias with spaces
- all columns operator `*` 
    + not a good pratice due to performance issue
    + only use the asterisk shorthand when examining data
    + instead, explicitly specify the necessary column names 

## Order by
`ORDER BY sort_expressions [ASC | DESC] [NULLS FIRST | NULLS LAST]`
- order by multiple columns : sorts the rows by the first column, and then sorts the sorted column by the following columns.
- alias : because the `ORDER BY` is evaluated after `SELECT`, the column alias can be used in the `ORDER BY` clause
- default values
    - ASC by default
    - ASC -> NULLS LAST by default
    - DESC -> NULLS FIRST by default
