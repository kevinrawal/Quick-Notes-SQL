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
<h1>Questions</h1>
<h4>Write a SQL query to find the names of employees who have not been assigned to any project.</h4>
<img width="338" alt="image" src="https://github.com/kevinrawal/Quick-Notes-SQL/assets/84058124/6e20b60d-6acb-4faf-a45a-fa2f5a7b09d5">
<img width="297" alt="image" src="https://github.com/kevinrawal/Quick-Notes-SQL/assets/84058124/326ce6bd-0437-4ca2-b7cb-3362d9b37242">
<br>

```
SELECT t1.employee_id from employee e1
left join projects t2 on t1.employee_id = t2.employee_id
where t2.employee_id IS NULL
```
