# Quick-Notes-SQL
<h1> Some Imp Questions</h1>
<h3>Inner Join Vs Natural Join Vs Cross Join</h3>

<li>In inner join we have to specifie colums and condition on which we want to join (same value)</li>
<li>In natural join we don't need to specify column or conditon it merge same colum with same value in both the table</li>
<li>In Cross join every Row of 1st table is merge with every Row of 2nd table</li>
<a href="https://www.geeksforgeeks.org/difference-between-natural-join-and-inner-join-in-sql/">GFG Article On inner vs Natural join</a>
<br>
<a href="https://www.geeksforgeeks.org/difference-between-natural-join-and-cross-join-in-sql/">GFG Article On Natural Vs Cross Join</a>
<br>

<h3>JOINS in SQL</h3>
<img width="334" alt="image" src="https://github.com/kevinrawal/Quick-Notes-SQL/assets/84058124/7ad9131e-fd04-40fb-9594-297360984b1a">
<li>FUll join is combination of left and right join</li>
<li>In cross join there is no null never, but in full join we can have NULL values as well, <a href="https://www.tutorialspoint.com/sql/sql-full-joins.htm">FULL JOIN article</a></li>
<li>FULL join and Natural Join is Different</li>
<br>

<h3>What is the difference between the SQL statements DELETE, TRUNCATE and DROP?</h3>
<li>DELETE: DML Commnad, we can delete specifice row, Can be rollback</li>
<li>TRUNCATE: DDL Command, We can delete every Row in one go, Can't rollback</li>
<li>Drop: DDL commmand, We can Drop(delete) whole structure,schema in one go, can't rollback</li>
<a href="https://www.geeksforgeeks.org/difference-between-delete-drop-and-truncate/"> GFG Article </a>
<br>

<h3>Aggregate and Scalar functions</h3>
<li>Both the function return single value</li>
<li>Aggregate function: used to perform operation on values of column</li>
<li>Scalar function: used to perform on user input</li>
<a href="https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/"> LINK TO READ </a>

<h3>INDEXING</h3>
<h4><a href="https://www.youtube.com/watch?v=E--yzX05_k8">Video to watch - 1</a></h4>
<h4><a href="https://www.youtube.com/watch?v=P24LAhp-ap8">Video to watch - 2</a></h4>
<h4><a href="https://www.youtube.com/watch?v=s_S_MpLoDEM">Video to watch - 3</a></h4>
<h4><a href="https://www.youtube.com/watch?v=E--yzX05_k8">Video to watch</a></h4>

<img width="386" alt="image" src="https://github.com/kevinrawal/Quick-Notes-SQL/assets/84058124/a17868d7-5607-4f84-a53c-491b8522c5db">
<li>Primary Index: Unique value + Ordered Value</li>
<li>Cluster Index: Non-Unique Value(Multiple) + Ordered value</li>
<li>Secondary Index: (non-unique or unique) value + unordered value</li>

<h4><a href="https://www.youtube.com/watch?v=4E-MGnjMhRw">Primary Index</a></h4>
<h4><a href="https://www.youtube.com/watch?v=UpJ9ICmzaAM">Clustered Index</a></h4>
<h4><a href="https://www.youtube.com/watch?v=Ua08uVgsk4k">Secondary Index</a></h4>
<br>

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
<h3>Write a SQL query to find the names of employees who have not been assigned to any project.</h3>
<img width="338" alt="image" src="https://github.com/kevinrawal/Quick-Notes-SQL/assets/84058124/6e20b60d-6acb-4faf-a45a-fa2f5a7b09d5">
<img width="297" alt="image" src="https://github.com/kevinrawal/Quick-Notes-SQL/assets/84058124/326ce6bd-0437-4ca2-b7cb-3362d9b37242">
<br>

```
SELECT t1.employee_id from employee e1
left join projects t2 on t1.employee_id = t2.employee_id
where t2.employee_id IS NULL
```
