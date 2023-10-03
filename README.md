# Quick-Notes-SQL

<h1>2nd Highest salary</h1>

```
SELECT MAX(salary) as second_highest_salary
FROM employees
WHERE salary != (SELECT MAX(salary) FROM employees)
```

<h1>Nth Highest salary</h1>

```
SELECT e1.salary as Nth_highest_salary
FROM employees e1
WHERE n-1 = (SELECT COUNT(DISTINCT e2.salary) FROM employees e2 WHERE e1.salary<e2.salary)    
```
