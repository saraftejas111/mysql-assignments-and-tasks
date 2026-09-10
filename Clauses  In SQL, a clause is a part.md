**Clauses** : In SQL, a clause is a part of a SQL statement that defines the conditions of the query.



SELECT : use to select the columns for retrieval opts



FROM : Indicates the table or tables from which to retrieve data.



WHERE : Filters the rows returned based on a specified condition.



ORDER BY Clause: Sorts the result set based on specified columns and in a specified order



**Aggregations** **:** inbuilt functions use to perform some actions and return the single value result  



SELECT \* FROM employees;

SELECT names as naam , salary as paisa FROM employees;



SELECT \* FROM employees WHERE salary<5000;

SELECT \* FROM employees where names like'%a%';



SELECT \* FROM employees ORDER BY salary desc;



SELECT COUNT(\*) as emp , role , sum(salary) 

FROM employees GROUP BY role;



SELECT COUNT(\*) as emp , role , sum(salary) 

FROM employees GROUP BY role HAVING sum(salary) > 5000 ;



SELECT \* FROM employees LIMIT 3;



\-- Aggregations : 



SELECT SUM(salary) as total\_salary FROM employees ; 

SELECT AVG(salary) FROM employees ; 

SELECT COUNT(id) total\_employees FROM employees;

SELECT MAX(salary) FROM employees;  -- 2131231

SELECT MIN(salary) FROM employees; 



SELECT MAX(salary) FROM employees WHERE salary < (SELECT MAX(salary) FROM employees); 





\-- tell me name and salary of the higesht paid employees 



SELECT names , salary FROM employees WHERE salary = (SELECT MAX(salary) FROM employees) ;



\-- tell me name and salary of the 2nd higesht paid employees 



SELECT names , salary FROM employees WHERE salary = 

(SELECT MAX(salary) FROM employees WHERE salary < (SELECT MAX(salary) FROM employees));



\-- tell me the name and role of the employees who is having max salary in hr dept ; 



SELECT names , role FROM employees WHERE salary = 

( SELECT MAX(salary) FROM employees WHERE role='hr');

