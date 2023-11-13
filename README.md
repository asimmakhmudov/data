# Practice 2 Solutions

1. **Query 1: Display the last name and salary of hr.employees earning more than $12,000.**
    ```sql
    SELECT last_name, salary
    FROM hr.employees
    WHERE salary > 12000;
    ```

2. **Query 2: Display the employee last name and department number for employee number 176.**
    ```sql
    SELECT last_name, department_id
    FROM hr.employees
    WHERE employee_id = 176;
    ```

3. **Query 3: Display the last name and salary for all hr.employees whose salary is not in the range of $5,000 and $12,000.**
    ```sql
    SELECT last_name, salary
    FROM hr.employees
    WHERE salary NOT BETWEEN 5000 AND 12000;
    ```

4. **Query 4: Display the employee last name, job ID, and start date of hr.employees hired between February 20, 1998, and May 1, 1998. Order the query in ascending order by start date.**
    ```sql
    SELECT last_name, job_id, hire_date
    FROM hr.employees
    WHERE hire_date BETWEEN '1998-02-20' AND '1998-05-01'
    ORDER BY hire_date;
    ```

5. **Query 5: Display the last name and department number of all hr.employees in departments 20 and 50 in alphabetical order by name.**
    ```sql
    SELECT last_name, department_id
    FROM hr.employees
    WHERE department_id IN (20, 50)
    ORDER BY last_name ASC;
    ```

6. **Query 6: Display the last name and salary of hr.employees who earn between $5,000 and $12,000 and are in department 20 or 50.**
    ```sql
    SELECT last_name AS "Employee", salary AS "Monthly Salary"
    FROM hr.employees
    WHERE salary BETWEEN 5000 AND 12000
    AND department_id IN (20, 50);
    ```

7. **Query 7: Display the last name and hire date of every employee who was hired in 1994.**
    ```sql
    SELECT last_name, hire_date
    FROM hr.employees
    WHERE hire_date LIKE '%1994';
    ```

8. **Query 8: Display the last name and job title of all hr.employees who do not have a manager.**
    ```sql
    SELECT last_name, job_id
    FROM hr.employees
    WHERE manager_id IS NULL;
    ```

9. **Query 9: Display the last name, salary, and commission for all hr.employees who earn commissions.**
    ```sql
    SELECT last_name, salary, commission_pct
    FROM hr.employees
    WHERE commission_pct IS NOT NULL
    ORDER BY salary DESC, commission_pct DESC;
    ```

10. **Query 10: Display the last names of hr.employees where the third letter of the name is 'a'.**
    ```sql
    SELECT last_name
    FROM hr.employees
    WHERE last_name LIKE '__a%';
    ```

11. **Query 11: Display the last name of hr.employees who have 'a' and 'e' in their last name.**
    ```sql
    SELECT last_name
    FROM hr.employees
    WHERE last_name LIKE '%a%' AND last_name LIKE '%e%';
    ```

12. **Extra Query 1: Display the last name, job, and salary for hr.employees with specific job titles and salaries.**
    ```sql
    SELECT last_name, job_id, salary
    FROM hr.employees
    WHERE job_id IN ('SA_REP', 'ST_CLERK')
    AND salary NOT IN (2500, 3500, 7000);
    ```

13. **Extra Query 2: Display the last name, salary, and commission for hr.employees with a 20% commission.**
    ```sql
    SELECT last_name AS "Employee", salary AS "Monthly Salary", commission_pct
    FROM hr.employees
    WHERE commission_pct = 0.20;
    ```


# Practice 3 Solutions

1. **Query 1: Display the current date. Label the column Date.**
    ```sql
    SELECT sysdate "Date"
    FROM dual;
    ```

2. **Query 2: For each employee, display the employee number, last_name, salary, and salary increased by 15% and expressed as a whole number. Label the column New Salary.**
    ```sql
    SELECT employee_id, last_name, salary, ROUND(salary * 1.15, 0) "New Salary"
    FROM hr.employees;
    ```

3. **Query 3: Run your query from lab3_2.sql.**
    ```sql
    SELECT employee_id, last_name, salary, ROUND(salary * 1.15, 0) "New Salary"
    FROM hr.employees;
    ```

4. **Query 4: Modify your query lab3_2.sql to add a column that subtracts the old salary from the new salary. Label the column Increase. Save the contents of the file as lab3_4.sql. Run the revised query.**
    ```sql
    SELECT employee_id, last_name, salary, ROUND(salary * 1.15, 0) "New Salary", ROUND(salary * 1.15, 0) - salary "Increase"
    FROM hr.employees;
    ```

5. **Query 5: Write a query that displays the employee’s last names with the first letter capitalized and all other letters lowercase and the length of the name for all hr.employees whose name starts with J, A, or M. Sort the results by the hr.employees’ last names.**
    ```sql
    SELECT INITCAP(last_name) "Name", LENGTH(last_name) "Length"
    FROM hr.employees
    WHERE last_name LIKE 'J%' OR last_name LIKE 'M%' OR last_name LIKE 'A%'
    ORDER BY last_name;
    ```

6. **Query 6: For each employee, display the employee’s last name, and calculate the number of months between today and the date the employee was hired. Label the column MONTHS_WORKED. Order your results by the number of months employed.**
    ```sql
    SELECT last_name, ROUND(MONTHS_BETWEEN(SYSDATE, hire_date)) MONTHS_WORKED
    FROM hr.employees
    ORDER BY MONTHS_BETWEEN(SYSDATE, hire_date);
    ```

7. **Query 7: Write a query that produces the following for each employee: `<employee last name> earns <salary> monthly but wants <3 times salary>`. Label the column Dream Salaries.**
    ```sql
    SELECT last_name || ' earns ' || TO_CHAR(salary, 'fm$99,999.00') || ' monthly but wants ' || TO_CHAR(salary * 3, 'fm$99,999.00') || '.' "Dream Salaries"
    FROM hr.employees;
    ```

8. **Query 8: Create a query to display the last name and salary for all hr.employees. Format the salary to be 15 characters long, left-padded with $. Label the column SALARY.**
    ```sql
    SELECT last_name, LPAD(salary, 15, '$') SALARY
    FROM hr.employees;
    ```

9. **Query 9: Display each employee’s last name, hire date, and salary review date, which is the first Monday after six months of service. Label the column REVIEW. Format the dates to appear in the format similar to “Monday, the Thirty-First of July, 2000.”**
    ```sql
    SELECT last_name, hire_date, TO_CHAR(NEXT_DAY(ADD_MONTHS(hire_date, 6),'MONDAY'), 'fmDay, "the" Ddspth "of" Month, YYYY') REVIEW
    FROM hr.employees;
    ```

10. **Query 10: Display the last name, hire date, and day of the week on which the employee started. Label the column DAY. Order the results by the day of the week starting with Monday.**
    ```sql
    SELECT last_name, hire_date, TO_CHAR(hire_date, 'DAY') DAY
    FROM hr.employees
    ORDER BY TO_CHAR(hire_date - 1, 'd');
    ```

11. **Query 11: Create a query that displays the hr.employees’ last names and commission amounts. If an employee does not earn commission, put “ No Commission.” Label the column COMM.**
    ```sql
    SELECT last_name, NVL(TO_CHAR(commission_pct), 'No Commission') COMM
    FROM hr.employees;
    ```

12. **Query 12: Create a query that displays the hr.employees’ last names and indicates the amounts of their annual salaries with asterisks. Each asterisk signifies a thousand dollars. Sort the data in descending order of salary. Label the column hr.EMPLOYEES_AND_THEIR_SALARIES.**
    ```sql
    SELECT rpad(last_name, 8) || ' ' || rpad(' ', salary/1000+1, '\*') hr.EMPLOYEES_AND_THEIR_SALARIES
    FROM hr.employees
    ORDER BY salary DESC;
    ```

13. **Query 13: Using the DECODE function, write a query that displays the grade of all hr.employees based on the value of the column JOB_ID, as per the provided data.**
    ```sql
    SELECT job_id, DECODE (job_id, 'ST_CLERK', 'E', 'SA_REP', 'D', 'IT_PROG', 'C', 'ST_MAN', 'B', 'AD_PRES', 'A', '0') GRADE
    FROM hr.employees;
    ```

14. **Query 14: Rewrite the statement in the preceding question using the CASE syntax.**
    ```sql
    SELECT job_id, CASE job_id WHEN 'ST_CLERK' THEN 'E' WHEN 'SA_REP' THEN 'D' WHEN 'IT_PROG' THEN 'C' WHEN 'ST_MAN' THEN 'B' WHEN 'AD_PRES' THEN 'A' ELSE '0' END GRADE
    FROM hr.employees;
    ```


# Practice 4 Solutions

1. **Query 1: Write a query to display the last name, department number, and department name for all hr.employees.**
    ```sql
    SELECT e.last_name, e.department_id, d.department_name
    FROM hr.employees e, departments d
    WHERE e.department_id = d.department_id;
    ```

2. **Query 2: Create a unique listing of all jobs that are in department 30. Include the location of department 90 in the output.**
    ```sql
    SELECT DISTINCT job_id, location_id
    FROM hr.employees, departments
    WHERE hr.employees.department_id = departments.department_id
    AND hr.employees.department_id = 80;
    ```

3. **Query 3: Write a query to display the employee last name, department name, location ID, and city of all hr.employees who earn a commission.**
    ```sql
    SELECT e.last_name, d.department_name, d.location_id, l.city
    FROM hr.employees e, departments d, locations l
    WHERE e.department_id = d.department_id
    AND d.location_id = l.location_id
    AND e.commission_pct IS NOT NULL;
    ```

4. **Query 4: Display the employee last name and department name for all hr.employees who have an _a_ (lowercase) in their last names.**
    ```sql
    SELECT last_name, department_name
    FROM hr.employees, departments
    WHERE hr.employees.department_id = departments.department_id
    AND last_name LIKE '%a%';
    ```

5. **Query 5: Write a query to display the last name, job, department number, and department name for all hr.employees who work in Toronto.**
    ```sql
    SELECT e.last_name, e.job_id, e.department_id, d.department_name
    FROM hr.employees e JOIN departments d
    ON (e.department_id = d.department_id)
    JOIN locations l
    ON (d.location_id = l.location_id)
    WHERE LOWER(l.city) = 'toronto';
    ```

6. **Query 6: Display the employee last name and employee number along with their manager’s last name and manager number.**
    ```sql
    SELECT w.last_name "Employee", w.employee_id "EMP#", m.last_name "Manager", m.employee_id "Mgr#"
    FROM hr.employees w JOIN hr.employees m
    ON (w.manager_id = m.employee_id);
    ```

7. **Query 7: Modify the query to display all hr.employees including King, who has no manager.**
    ```sql
    SELECT w.last_name "Employee", w.employee_id "EMP#", m.last_name "Manager", m.employee_id "Mgr#"
    FROM hr.employees w
    LEFT OUTER JOIN hr.employees m
    ON (w.manager_id = m.employee_id);
    ```

8. **Query 8: Create a query to display employee last names, department numbers, and all the hr.employees who work in the same department as a given employee.**
    ```sql
    SELECT e.department_id department, e.last_name employee, c.last_name colleague
    FROM hr.employees e JOIN hr.employees c
    ON (e.department_id = c.department_id)
    WHERE e.employee_id <> c.employee_id
    ORDER BY e.department_id, e.last_name, c.last_name;
    ```

9. **Query 9: Show the structure of the JOB_GRADES table and create a query to display the name, job, department name, salary, and grade for all hr.employees.**
    ```sql
    -- Show structure of JOB_GRADES table
    DESC JOB_GRADES

    -- Query to display employee information
    SELECT e.last_name, e.job_id, d.department_name, e.salary, j.grade_level
    FROM hr.employees e, departments d, job_grades j
    WHERE e.department_id = d.department_id
    AND e.salary BETWEEN j.lowest_sal AND j.highest_sal;
    ```

10. **Query 10: Create a query to display the name and hire date of any employee hired after employee Davies.**
    ```sql
    SELECT e.last_name, e.hire_date
    FROM hr.employees e, hr.employees davies
    WHERE davies.last_name = 'Davies'
    AND davies.hire_date < e.hire_date;
    ```

11. **Query 11: Display the names and hire dates for all hr.employees who were hired before their managers, along with their manager’s names and hire dates.**
    ```sql
    SELECT w.last_name, w.hire_date, m.last_name, m.hire_date
    FROM hr.employees w, hr.employees m
    WHERE w.manager_id = m.employee_id
    AND w.hire_date < m.hire_date;
    ```


# Practice 5 Solutions

1. **Statement 1: Group functions work across many rows to produce one result.**
    - True

2. **Statement 2: Group functions include nulls in calculations.**
    - False. Group functions ignore null values. If you want to include null values, use the NVL function.

3. **Statement 3: The WHERE clause restricts rows prior to inclusion in a group calculation.**
    - True

4. **Query 4: Display the highest, lowest, sum, and average salary of all hr.employees.**
    ```sql
    SELECT ROUND(MAX(salary), 0) "Maximum",
    ROUND(MIN(salary), 0) "Minimum",
    ROUND(SUM(salary), 0) "Sum",
    ROUND(AVG(salary), 0) "Average"
    FROM hr.employees;
    ```

5. **Query 5: Modify the query to display the minimum, maximum, sum, and average salary for each job type.**
    ```sql
    SELECT job_id, ROUND(MAX(salary), 0) "Maximum",
    ROUND(MIN(salary), 0) "Minimum",
    ROUND(SUM(salary), 0) "Sum",
    ROUND(AVG(salary), 0) "Average"
    FROM hr.employees
    GROUP BY job_id;
    ```

6. **Query 6: Write a query to display the number of people with the same job.**
    ```sql
    SELECT job_id, COUNT(*)
    FROM hr.employees
    GROUP BY job_id;
    ```

7. **Query 7: Determine the number of managers without listing them.**
    ```sql
    SELECT COUNT(DISTINCT manager_id) "Number of Managers"
    FROM hr.employees;
    ```

8. **Query 8: Write a query that displays the difference between the highest and lowest salaries.**
    ```sql
    SELECT MAX(salary) - MIN(salary) DIFFERENCE
    FROM hr.employees;
    ```

9. **Query 9: Display the manager number and the salary of the lowest paid employee for that manager.**
    ```sql
    SELECT manager_id, MIN(salary)
    FROM hr.employees
    WHERE manager_id IS NOT NULL
    GROUP BY manager_id
    HAVING MIN(salary) > 6000
    ORDER BY MIN(salary) DESC;
    ```

10. **Query 10: Write a query to display each department’s name, location, number of hr.employees, and the average salary for all hr.employees in that department.**
    ```sql
    SELECT d.department_name "Name", d.location_id "Location",
    COUNT(*) "Number of People",
    ROUND(AVG(salary), 2) "Salary"
    FROM hr.employees e, departments d
    WHERE e.department_id = d.department_id
    GROUP BY d.department_name, d.location_id;
    ```

11. **Query 11: Create a query to display the total number of hr.employees and the number of hr.employees hired in 1995, 1996, 1997, and 1998.**
    ```sql
    SELECT COUNT(*) total,
    SUM(DECODE(TO_CHAR(hire_date, 'YYYY'), 1995, 1, 0)) "1995",
    SUM(DECODE(TO_CHAR(hire_date, 'YYYY'), 1996, 1, 0)) "1996",
    SUM(DECODE(TO_CHAR(hire_date, 'YYYY'), 1997, 1, 0)) "1997",
    SUM(DECODE(TO_CHAR(hire_date, 'YYYY'), 1998, 1, 0)) "1998"
    FROM hr.employees;
    ```

12. **Query 12: Create a matrix query to display the job, the salary for that job based on department number, and the total salary for that job, for departments 20, 50, 80, and 90.**
    ```sql
    SELECT job_id "Job",
    SUM(DECODE(department_id, 20, salary)) "Dept 20",
    SUM(DECODE(department_id, 50, salary)) "Dept 50",
    SUM(DECODE(department_id, 80, salary)) "Dept 80",
    SUM(DECODE(department_id, 90, salary)) "Dept 90",
    SUM(salary) "Total"
    FROM hr.employees
    GROUP BY job_id;
    ```

# Practice 6 Solutions

1. **Query 1: Write a query to display the last name and hire date of any employee in the same department as Zlotkey. Exclude Zlotkey.**
    ```sql
    SELECT last_name, hire_date
    FROM hr.employees
    WHERE department_id = (SELECT department_id
                          FROM hr.employees
                          WHERE last_name = 'Zlotkey')
    AND last_name <> 'Zlotkey';
    ```

2. **Query 2: Create a query to display the employee numbers and last names of all hr.employees who earn more than the average salary. Sort the results in descending order of salary.**
    ```sql
    SELECT employee_id, last_name
    FROM hr.employees
    WHERE salary > (SELECT AVG(salary)
                    FROM hr.employees);
    ```

3. **Query 3: Write a query that displays the employee numbers and last names of all hr.employees who work in a department with any employee whose last name contains a 'u'.**
    ```sql
    SELECT employee_id, last_name
    FROM hr.employees
    WHERE department_id IN (SELECT department_id
                            FROM hr.employees
                            WHERE last_name like '%u%');
    ```

4. **Query 4: Display the last name, department number, and job ID of all hr.employees whose department location ID is 1700.**
    ```sql
    SELECT last_name, department_id, job_id
    FROM hr.employees
    WHERE department_id IN (SELECT department_id
                          FROM departments
                          WHERE location_id = 1700);
    ```

5. **Query 5: Display the last name and salary of every employee who reports to King.**
    ```sql
    SELECT last_name, salary
    FROM hr.employees
    WHERE manager_id = (SELECT employee_id
                      FROM hr.employees
                      WHERE last_name = 'King');
    ```

6. **Query 6: Display the department number, last name, and job ID for every employee in the Executive department.**
    ```sql
    SELECT department_id, last_name, job_id
    FROM hr.employees
    WHERE department_id IN (SELECT department_id
                          FROM departments
                          WHERE department_name = 'Executive');
    ```

7. **Query 7: Modify the query to display the employee numbers, last names, and salaries of all hr.employees who earn more than the average salary and who work in a department with any employee with a 'u' in their name.**
    ```sql
    SELECT employee_id, last_name, salary
    FROM hr.employees
    WHERE department_id IN (SELECT department_id
                            FROM hr.employees
                            WHERE last_name like '%u%')
    AND salary > (SELECT AVG(salary)
                  FROM hr.employees);
    ```

