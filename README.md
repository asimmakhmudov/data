<a name="br1"></a> 

**Practice Solutions**



<a name="br2"></a> 

<a name="br3"></a> 

**Practice 1 Solutions**

1\. Initiate an *i*SQL\*Plus session using the user ID and password provided by the instructor.

2\. *i*SQL\*Plus commands access the database.

**False**

3\. The following SELECT statement executes successfully:

**True**

SELECT last\_name, job\_id, salary AS Sal

FROM   hr.employees;

4\. The following SELECT statement executes successfully:

**True**

SELECT \* 

FROM   job\_grades;

5\. There are four coding errors in this statement. Can you identify them?

SELECT    employee\_id, last\_name

sal x 12  ANNUAL SALARY

FROM      hr.employees;

–

**The** hr.EMPLOYEES **table does not contain a column called** sal**. The column is called**

SALARY**.**

–

–

**The multiplication operator is \*, not x, as shown in line 2.**

**The** ANNUAL SALARY **alias cannot include spaces. The alias should read**

ANNUAL\_SALARY **or be enclosed in double quotation marks.**

–

**A comma is missing after the column,**LAST\_NAME**.**

6\. Show the structure of the DEPARTMENTS table. Select all data from the DEPARTMENTS table.

DESCRIBE departments

SELECT \*

FROM   departments;

7\. Show the structure of the hr.EMPLOYEES table. Create a query to display the last name, job code,

hire date, and employee number for each employee, with employee number appearing first. Save

your SQL statement to a file named lab1\_7.sql.

DESCRIBE hr.employees

SELECT employee\_id, last\_name, job\_id, hire\_date

FROM   hr.employees;

**Introduction to Oracle9*i*: SQL A-3**



<a name="br4"></a> 

**Practice 1 Solutions (continued)**

8\. Run your query in the file lab1\_7.sql.

SELECT employee\_id, last\_name, job\_id, hire\_date

FROM   hr.employees;

9\. Create a query to display unique job codes from the hr.EMPLOYEES table.

SELECT DISTINCT job\_id

FROM   hr.employees;

If you have time, complete the following exercises:

10\. Copy the statement from lab1\_7.sql into the *i*SQL\*Plus Edit window. Name the column

headings Emp #, Employee, Job, and Hire Date, respectively. Run your query again.

SELECT employee\_id "Emp #", last\_name "Employee",

job\_id "Job", hire\_date "Hire Date"

FROM   hr.employees;

11\. Display the last name concatenated with the job ID, separated by a comma and space, and name the

column Employee and Title.

SELECT last\_name||', '||job\_id "Employee and Title"

FROM   hr.employees;

If you want an extra challenge, complete the following exercise:

12\. Create a query to display all the data from the hr.EMPLOYEES table. Separate each column by a

comma. Name the column THE\_OUTPUT.

SELECT employee\_id || ',' || first\_name || ',' || last\_name 

|| ',' || email || ',' || phone\_number || ','|| job\_ id

|| ',' || manager\_id || ',' || hire\_date || ',' || 

salary || ',' || commission\_pct || ',' || department \_id

THE\_OUTPUT

FROM   hr.employees;

**Introduction to Oracle9*i*: SQL A-4**



<a name="br5"></a> 

**Practice 2 Solutions**

1\. Create a query to display the last name and salary of hr.employees earning more than $12,000.

Place your SQL statement in a text file named lab2\_1.sql. Run your query.

SELECT  last\_name, salary

FROM    hr.employees

WHERE   salary > 12000; 

2\. Create a query to display the employee last name and department number for employee number

176\.

SELECT  last\_name, department\_id

FROM    hr.employees

WHERE   employee\_id = 176;

3\. Modify lab2\_1.sql to display the last name and salary for all hr.employees whose salary is not in

the range of $5,000 and $12,000. Place your SQL statement in a text file named lab2\_3.sql.

SELECT  last\_name, salary

FROM    hr.employees

WHERE   salary NOT BETWEEN 5000 AND 12000;

4\. Display the employee last name, job ID, and start date of hr.employees hired between February 20,

1998, and May 1, 1998. Order the query in ascending order by start date.

SELECT   last\_name, job\_id, hire\_date

FROM     hr.employees

WHERE    hire\_date BETWEEN '20-Feb-1998' AND '01-May-1998'

ORDER BY hire\_date;

**Introduction to Oracle9*i*: SQL A-5**



<a name="br6"></a> 

**Practice 2 Solutions (continued)**

5\. Display the last name and department number of all hr.employees in departments 20 and 50 in

alphabetical order by name.

SELECT   last\_name, department\_id

FROM     hr.employees

WHERE    department\_id IN (20, 50)

ORDER BY last\_name;

6\. Modify lab2\_3.sql to list the last name and salary of hr.employees who earn between $5,000 and

$12,000, and are in department 20 or 50. Label the columns Employee and Monthly Salary,

respectively. Resave lab2\_3.sql as lab2\_6.sql. Run the statement in lab2\_6.sql.

SELECT   last\_name "Employee", salary "Monthly Salary"

FROM     hr.employees

WHERE    salary  BETWEEN 5000 AND 12000

AND      department\_id IN (20, 50);

7\. Display the last name and hire date of every employee who was hired in 1994.

SELECT   last\_name, hire\_date

FROM     hr.employees

WHERE    hire\_date LIKE '%94';

8\. Display the last name and job title of all hr.employees who do not have a manager.

SELECT   last\_name, job\_id

FROM     hr.employees

WHERE    manager\_id IS NULL;

9\. Display the last name, salary, and commission for all hr.employees who earn commissions. Sort

data in descending order of salary and commissions.

SELECT   last\_name, salary, commission\_pct

FROM     hr.employees

WHERE    commission\_pct IS NOT NULL

ORDER BY salary DESC, commission\_pct DESC;

**Introduction to Oracle9*i*: SQL A-6**



<a name="br7"></a> 

**Practice 2 Solutions (continued)**

If you have time, complete the following exercises.

10\. Display the last names of all hr.employees where the third letter of the name is an *a.*

SELECT   last\_name

FROM     hr.employees

WHERE    last\_name LIKE '\_\_a%';

11\. Display the last name of all hr.employees who have an *a* and an *e* in their last name.

SELECT   last\_name

FROM     hr.employees

WHERE    last\_name LIKE '%a%'

AND    last\_name LIKE '%e%';

If you want an extra challenge, complete the following exercises:

12\. Display the last name, job, and salary for all hr.employees whose job is sales representative or stock

clerk and whose salary is not equal to $2,500, $3,500, or $7,000.

SELECT   last\_name, job\_id, salary

FROM     hr.employees

WHERE    job\_id IN ('SA\_REP', 'ST\_CLERK')

AND    salary NOT IN (2500, 3500, 7000);

13\. Modify lab2\_6.sql to display the last name, salary, and commission for all hr.employees whose

commission amount is 20%. Resave lab2\_6.sql as lab2\_13.sql. Rerun the statement in

lab2\_13.sql.

.

SELECT   last\_name "Employee", salary "Monthly Salary", 

commission\_pct

FROM     hr.employees

WHERE    commission\_pct = .20;

**Introduction to Oracle9*i*: SQL A-7**



<a name="br8"></a> 

**Practice 3 Solutions**

1\. Write a query to display the current date. Label the column Date.

SELECT   sysdate "Date"

FROM     dual;

2\. For each employee, display the employee number, last\_name, salary, and salary increased by 15%

and expressed as a whole number. Label the column New Salary. Place your SQL statement in a

text file named lab3\_2.sql.

SELECT   employee\_id, last\_name, salary,

ROUND(salary \* 1.15, 0) "New Salary"

FROM     hr.employees;

3\. Run your query in the file lab3\_2.sql.

SELECT  employee\_id, last\_name, salary,

ROUND(salary \* 1.15, 0) "New Salary"

FROM    hr.employees;

4\. Modify your query lab3\_2.sql to add a column that subtracts the old salary from

the new salary. Label the column Increase. Save the contents of the file as lab3\_4.sql. Run

the revised query.

SELECT   employee\_id, last\_name, salary, 

ROUND(salary \* 1.15, 0) "New Salary",

ROUND(salary \* 1.15, 0) - salary "Increase"

FROM     hr.employees;

5\. Write a query that displays the employee’s last names with the first letter capitalized and all other

letters lowercase and the length of the name for all hr.employees whose name starts with *J*, *A*, or *M*.

Give each column an appropriate label. Sort the results by the hr.employees’ last names.

SELECT

INITCAP(last\_name) "Name",

LENGTH(last\_name) "Length"

FROM     hr.employees

WHERE    last\_name LIKE 'J%'

OR       last\_name LIKE 'M%'

OR       last\_name LIKE 'A%'

ORDER BY last\_name;

**Introduction to Oracle9*i*: SQL A-8**



<a name="br9"></a> 

**Practice 3 Solutions (continued)**

6\. For each employee, display the employee’s last name, and calculate the number of months between

today and the date the employee was hired. Label the column MONTHS\_WORKED. Order your results

by the number of months employed. Round the number of months up to the closest whole number.

**Note:** Your results will differ.

SELECT   last\_name, ROUND(MONTHS\_BETWEEN

(SYSDATE, hire\_date)) MONTHS\_WORKED

FROM     hr.employees

ORDER BY MONTHS\_BETWEEN(SYSDATE, hire\_date);

7\. Write a query that produces the following for each employee:

<employee last name> earns <salary> monthly but wants <3 times 

salary>. Label the column Dream Salaries.

SELECT   last\_name || ' earns '

|| TO\_CHAR(salary, 'fm$99,999.00')

|| ' monthly but wants '

|| TO\_CHAR(salary \* 3, 'fm$99,999.00')

|| '.' "Dream Salaries"

FROM     hr.employees;

If you have time, complete the following exercises:

8\. Create a query to display the last name and salary for all hr.employees. Format the salary to be 15

characters long, left-padded with $. Label the column SALARY.

SELECT   last\_name,

LPAD(salary, 15, '$') SALARY

FROM     hr.employees;

9\. Display each employee’s last name, hire date, and salary review date, which is the first Monday after

six months of service. Label the column REVIEW. Format the dates to appear in the format similar to

“Monday, the Thirty-First of July, 2000.”

SELECT   last\_name, hire\_date,

TO\_CHAR(NEXT\_DAY(ADD\_MONTHS(hire\_date,  6),'MONDAY'),

'fmDay, "the" Ddspth "of" Month, YYYY') REVIEW

FROM     hr.employees;

10\. Display the last name, hire date, and day of the week on which the employee started. Label

the column DAY. Order the results by the day of the week starting with Monday.

SELECT   last\_name, hire\_date,

TO\_CHAR(hire\_date, 'DAY') DAY

FROM     hr.employees

ORDER BY TO\_CHAR(hire\_date - 1, 'd');

**Introduction to Oracle9*i*: SQL A-9**



<a name="br10"></a> 

**Practice 3 Solutions (continued)**

If you want an extra challenge, complete the following exercises:

11\. Create a query that displays the hr.employees’ last names and commission amounts. If an employee

does not earn commission, put “ No Commission.” Label the column COMM.

SELECT   last\_name,

NVL(TO\_CHAR(commission\_pct), 'No Commission') COM M

FROM     hr.employees;

12\. Create a query that displays the hr.employees’ last names and indicates the amounts of their annual

salaries with asterisks. Each asterisk signifies a thousand dollars. Sort the data in descending order

of salary. Label the column hr.EMPLOYEES\_AND\_THEIR\_SALARIES.

SELECT

rpad(last\_name, 8)||' '|| rpad(' ', salary/1000+1, '\*')

hr.EMPLOYEES\_AND\_THEIR\_SALARIES

FROM     hr.employees

ORDER BY salary DESC;

13\. Using the DECODE function, write a query that displays the grade of all hr.employees based on the

value of the column JOB\_ID, as per the following data:

JOB

GRADE

AD\_PRES

A

B

C

D

E

0

ST\_MAN

IT\_PROG

SA\_REP

ST\_CLERK

None of the above

SELECT job\_id, decode (job\_id,

'ST\_CLERK',  'E',

'SA\_REP',    'D',

'IT\_PROG',   'C',

'ST\_MAN',    'B',

'AD\_PRES',   'A',

'0')GRADE

FROM hr.employees;

**Introduction to Oracle9*i*: SQL A-10**



<a name="br11"></a> 

**Practice 3 Solutions (continued)**

14\. Rewrite the statement in the preceding question using the CASE syntax.

SELECT job\_id, CASE job\_id

WHEN 'ST\_CLERK' THEN 'E'

WHEN 'SA\_REP'   THEN 'D'

WHEN 'IT\_PROG'  THEN 'C'

WHEN 'ST\_MAN'   THEN 'B'

WHEN 'AD\_PRES'  THEN 'A'

ELSE '0'  END  GRADE

FROM hr.employees;

**Introduction to Oracle9*i*: SQL A-11**



<a name="br12"></a> 

**Practice 4 Solutions**

1\. Write a query to display the last name, department number, and department name for all

hr.employees.

SELECT e.last\_name, e.department\_id, d.department\_name

FROM hr.employees e, departments d

WHERE e.department\_id = d.department\_id;

2\. Create a unique listing of all jobs that are in department 30. Include the location of department 90

in the output.

SELECT DISTINCT job\_id, location\_id

FROM hr.employees, departments

WHERE hr.employees.department\_id = departments.department\_id

AND hr.employees.department\_id = 80;

3\. Write a query to display the employee last name, department name, location ID, and city of all

hr.employees who earn a commission.

SELECT e.last\_name, d.department\_name, d.location\_id, l.c ity

FROM hr.employees e, departments d, locations l

WHERE e.department\_id = d.department\_id

AND

d.location\_id = l.location\_id

AND e.commission\_pct IS NOT NULL;

4\. Display the employee last name and department name for all hr.employees who have an *a* (lowercase)

in their last names. Place your SQL statement in a text file nam ed lab4\_4.sql.

SELECT last\_name, department\_name

FROM hr.employees, departments

WHERE hr.employees.department\_id = departments.department\_id

AND last\_name LIKE '%a%';

**Introduction to Oracle9*i*: SQL A-12**



<a name="br13"></a> 

**Practice 4 Solutions (continued)**

5\. Write a query to display the last name, job, department number, and department name for all

hr.employees who work in Toronto.

SELECT e.last\_name, e.job\_id, e.department\_id, 

d.department\_name

FROM hr.employees e JOIN departments d 

ON (e.department\_id = d.department\_id)

JOIN locations l

ON (d.location\_id = l.location\_id)

WHERE LOWER(l.city) = 'toronto';

6\. Display the employee last name and employee number along with their manager’s last name and

manager number. Label the columns Employee, Emp#, Manager, and Mgr#, respectively.

Place your SQL statement in a text file named lab4\_6.sql.

SELECT w.last\_name "Employee", w.employee\_id "EMP#", 

m.last\_name "Manager", m.employee\_id  "Mgr#"

FROM hr.employees w join hr.employees m

ON (w.manager\_id = m.employee\_id);

**Introduction to Oracle9*i*: SQL A-13**



<a name="br14"></a> 

**Practice 4 Solutions (continued)**

7\. Modify lab4\_6.sql to display all hr.employees including King, who has no manager.

Place your SQL statement in a text file named lab4\_7.sql. Run the query in lab4\_7.sql

SELECT w.last\_name "Employee", w.employee\_id "EMP#", 

m.last\_name "Manager", m.employee\_id  "Mgr#"

FROM hr.employees w 

LEFT OUTER JOIN hr.employees m

ON (w.manager\_id = m.employee\_id);

If you have time, complete the following exercises.

8\. Create a query that displays employee last names, department numbers, and all the

hr.employees who work in the same department as a given employee. Give each column an appropriate

label.

SELECT e.department\_id department, e.last\_name employee,

c.last\_name colleague

FROM   hr.employees e JOIN hr.employees c

ON     (e.department\_id = c.department\_id)

WHERE   e.employee\_id <> c.employee\_id

ORDER BY e.department\_id, e.last\_name, c.last\_name;

9\. Show the structure of the JOB\_GRADES table. Create a query that displays the name, job,

department name, salary, and grade for all hr.employees.

DESC JOB\_GRADES

SELECT e.last\_name, e.job\_id, d.department\_name,

e.salary, j.grade\_level

FROM   hr.employees e, departments d, job\_grades j

WHERE  e.department\_id = d.department\_id

AND    e.salary BETWEEN j.lowest\_sal AND j.highest\_sal;

-- OR

SELECT e.last\_name, e.job\_id, d.department\_name,

e.salary, j.grade\_level

FROM   hr.employees e JOIN departments d

ON     (e.department\_id = d.department\_id)

JOIN   job\_grades j

ON    (e.salary BETWEEN j.lowest\_sal AND j.highest\_sal);

**Introduction to Oracle9*i*: SQL A-14**



<a name="br15"></a> 

**Practice 4 Solutions (continued)**

If you want an extra challenge, complete the following exercises:

10\. Create a query to display the name and hire date of any employee hired after employee Davies.

SELECT e.last\_name, e.hire\_date

FROM   hr.employees e, hr.employees davies

WHERE davies.last\_name = 'Davies'

AND

davies.hire\_date < e.hire\_date

-- OR

SELECT e.last\_name, e.hire\_date

FROM   hr.employees e JOIN hr.employees davies

ON     (davies.last\_name = 'Davies')

WHERE davies.hire\_date < e.hire\_date;

11\. Display the names and hire dates for all hr.employees who were hire d before their managers, along with

their manager’s names and hire dates. Label the columns Employee, Emp

Hired, Manager, and Mgr Hired, respectively.

SELECT w.last\_name, w.hire\_date, m.last\_name, m.hire\_date

FROM   hr.employees w, hr.employees m

WHERE  w.manager\_id = m.employee\_id

AND    w.hire\_date <  m.hire\_date;

-- OR

SELECT w.last\_name, w.hire\_date, m.last\_name, m.hire\_date

FROM   hr.employees w JOIN hr.employees m

ON    (w.manager\_id = m.employee\_id)

WHERE    w.hire\_date <  m.hire\_date;

**Introduction to Oracle9*i*: SQL A-15**



<a name="br16"></a> 

**Practice 5 Solutions**

Determine the validity of the following three statements. Circle either True or False.

1\. Group functions work across many rows to produce one result.

**True**

2\. Group functions include nulls in calculations.

**False. Group functions ignore null values. If you want to include null values, use the NVL**

**function.**

3\. The WHERE clause restricts rows prior to inclusion in a group calculation.

**True**

4\. Display the highest, lowest, sum, and average salary of all hr.employees. Label the columns

Maximum, Minimum, Sum, and Average, respectively. Round your results to the nearest whole

number. Place your SQL statement in a text file named lab5\_6.sql.

SELECT   ROUND(MAX(salary),0) "Maximum",

ROUND(MIN(salary),0)  "Minimum",

ROUND(SUM(salary),0) "Sum",

ROUND(AVG(salary),0)  "Average"

FROM     hr.employees;

5\. Modify the query in lab5\_4.sql to display the minimum, maximum, sum, and average salary for

each job type. Resave lab5\_4.sql to lab5\_5.sql. Run the statement in lab5\_5.sql.

SELECT   job\_id, ROUND(MAX(salary),0) "Maximum",

ROUND(MIN(salary),0)  "Minimum",

ROUND(SUM(salary),0) "Sum",

ROUND(AVG(salary),0)  "Average"

FROM     hr.employees

GROUP BY job\_id;

**Introduction to Oracle9*i*: SQL A-16**



<a name="br17"></a> 

**Practice 5 Solutions (continued)**

6\. Write a query to display the number of people with the same job.

SELECT   job\_id, COUNT(\*)

FROM     hr.employees

GROUP BY job\_id;

7\. Determine the number of managers without listing them. Label the column Number of

Managers. **Hint**: Use the MANAGER\_ID column to determine the number of managers.

SELECT   COUNT(DISTINCT manager\_id) "Number of Managers"

FROM     hr.employees;

8\. Write a query that displays the difference between the highest and lowest salaries. Label the column

DIFFERENCE.

SELECT   MAX(salary) - MIN(salary) DIFFERENCE

FROM     hr.employees;

If you have time, complete the following exercises.

9\. Display the manager number and the salary of the lowest paid employee for that manager.

Exclude anyone whose manager is not known. Exclude any groups where the minimum

salary is less than $6,000. Sort the output in descending order of salary.

SELECT   manager\_id, MIN(salary)

FROM     hr.employees

WHERE    manager\_id IS NOT NULL

GROUP BY manager\_id

HAVING   MIN(salary) > 6000

ORDER BY MIN(salary) DESC;

10\. Write a query to display each department’s name, location, number of hr.employees, and the average

salary for all hr.employees in that department. Label the columns Name, Location, Number of 

People, and Salary, respectively. Round the average salary to two decimal places.

SELECT   d.department\_name "Name", d.location\_id "Location ",

COUNT(\*) "Number of People",

ROUND(AVG(salary),2)  "Salary"

FROM     hr.employees e, departments d

WHERE    e.department\_id = d.department\_id

GROUP BY d.department\_name, d.location\_id;

**Introduction to Oracle9*i*: SQL A-17**



<a name="br18"></a> 

**Practice 5 Solutions (continued)**

If you want an extra challenge, complete the following exercises:

11\. Create a query that will display the total number of hr.employees and, of that total, the number of

hr.employees hired in 1995, 1996, 1997, and 1998. Create appropriate column headings.

SELECT  COUNT(\*) total,

SUM(DECODE(TO\_CHAR(hire\_date,  'YYYY'),1995,1,0))"1 995",

SUM(DECODE(TO\_CHAR(hire\_date,  'YYYY'),1996,1,0))"1 996",

SUM(DECODE(TO\_CHAR(hire\_date,  'YYYY'),1997,1,0))"1 997",

SUM(DECODE(TO\_CHAR(hire\_date,  'YYYY'),1998,1,0))"1 998"

FROM    hr.employees;

12\. Create a matrix query to display the job, the salary for that job based on department number, and the

total salary for that job, for departments 20, 50, 80, and 90, giving each column an appropriate

heading.

SELECT   job\_id "Job",

SUM(DECODE(department\_id , 20, salary)) "Dept 20" ,

SUM(DECODE(department\_id , 50, salary)) "Dept 50" ,

SUM(DECODE(department\_id , 80, salary)) "Dept 80" ,

SUM(DECODE(department\_id , 90, salary)) "Dept 90" ,

SUM(salary) "Total"

FROM     hr.employees

GROUP BY job\_id;

**Introduction to Oracle9*i*: SQL A-18**



<a name="br19"></a> 

**Practice 6 Solutions**

1\. Write a query to display the last name and hire date of any employee in the same

department as Zlotkey. Exclude Zlotkey.

SELECT last\_name, hire\_date

FROM   hr.employees

WHERE  department\_id = (SELECT department\_id

FROM   hr.employees

WHERE  last\_name = 'Zlotkey')

AND    last\_nae <> 'Zlotkey';

2\. Create a query to display the employee numbers and last names of all hr.employees who earn more than

the average salary. Sort the results in descending order of salary.

SELECT employee\_id, last\_name

FROM   hr.employees

WHERE  salary > (SELECT AVG(salary)

FROM   hr.employees);

3\. Write a query that displays the employee numbers and last names of all hr.employees who work in a

department with any employee whose last name contains a *u*. Place your SQL statement in a text

file named lab6\_3.sql. Run your query.

SELECT employee\_id, last\_name

FROM   hr.employees

WHERE  department\_id IN (SELECT department\_id

FROM   hr.employees

WHERE  last\_name like '%u%');

4\. Display the last name, department number, and job ID of all hr.employees whose department location ID

is 1700.

SELECT last\_name, department\_id, job\_id

FROM   hr.employees

WHERE  department\_id IN (SELECT department\_id

FROM   departments

WHERE  location\_id = 1700);

**Introduction to Oracle9*i*: SQL A-19**



<a name="br20"></a> 

**Practice 6 Solutions (continued)**

5\. Display the last name and salary of every employee who reports to King.

SELECT last\_name, salary

FROM   hr.employees

WHERE  manager\_id = (SELECT employee\_id

FROM   hr.employees

WHERE  last\_name = 'King');

6\. Display the department number, last name, and job ID for every employee in the Executive

department.

SELECT department\_id, last\_name, job\_id

FROM   hr.employees

WHERE  department\_id IN (SELECT department\_id

FROM   departments

WHERE  department\_name = 'Executive');

If you have time, complete the following exercises:

7\. Modify the query in lab6\_3.sql to display the employee numbers, last names, and salaries of all

hr.employees who earn more than the average salary and who work in a department with any employee

with a *u* in their name. Resave lab6\_3.sql to lab6\_7.sql. Run the statement in

lab6\_7.sql.

SELECT employee\_id, last\_name, salary

FROM   hr.employees

WHERE  department\_id IN (SELECT department\_id

FROM   hr.employees

WHERE  last\_name like '%u%')

AND    salary > (SELECT AVG(salary)

FROM   hr.employees);

**Introduction to Oracle9*i*: SQL A-20**



<a name="br21"></a> 

**Practice 7 Solutions**

Determine whether the following statements are true or false:

1\. The following statement is correct:

DEFINE & p\_val = 100

**False**

**The correct use of DEFINE is** DEFINE p\_val=100**. The** & **is used within the SQL code.**

2\. The DEFINE command is a SQL command.

**False**

**The** DEFINE **command is an iSQL\*Plus command.**

3\. Write a script file to display the employee last name, job, and hire date for all hr.employees who

started between a given range. Concatenate the name and job together, separated by a space

and comma, and label the column hr.Employees. Use the DEFINE command to provide the two

ranges. Use the format MM/DD/YYYY. Save the script file as lab7\_3.sql.

SET ECHO OFF

SET VERIFY OFF

DEFINE low\_date = 01/01/1998

DEFINE high\_date = 01/01/1999

SELECT  last\_name ||', '|| job\_id hr.EMPLOYEES, hire\_date

FROM    hr.employees

WHERE   hire\_date BETWEEN TO\_DATE('&low\_date',  'MM/DD/YYYY')

AND TO\_DATE('&high\_date', 'MM/DD/YYYY')

/

UNDEFINE low\_date

UNDEFINE high\_date

SET VERIFY ON

SET ECHO ON

**Introduction to Oracle9*i*: SQL A-21**



<a name="br22"></a> 

**Practice 7 Solutions (continued)**

4\. Write a script to display the employee last name, job, and department name for a given location. The

search condition should allow for case-insensitive searches of the department location. Save the

script file as lab7\_4.sql.

SET ECHO OFF

SET VERIFY OFF

COLUMN last\_name HEADING "EMPLOYEE NAME"

COLUMN department\_name HEADING "DEPARTMENT NAME”

SELECT  e.last\_name, e.job\_id, d.department\_name

FROM    hr.employees e, departments d, locations l

WHERE   e.department\_id = d.department\_id

AND     l.location\_id = d.location\_id

AND     l.city = INITCAP('&p\_location')

/

COLUMN last\_name CLEAR

COLUMN department\_name CLEAR

SET VERIFY ON

SET ECHO ON

**Introduction to Oracle9*i*: SQL A-22**



<a name="br23"></a> 

**Practice 7 Solutions (continued)**

5\. Modify the code in lab7\_4.sql to create a report containing the department name, employee last

name, hire date, salary, and each employee’s annual salary for all hr.employees in a given location.

Label the columns DEPARTMENT NAME, EMPLOYEE NAME, START DATE, SALARY, and

ANNUAL SALARY, placing the labels on multiple lines. Resave the script as lab7\_5.sql and

execute the commands in the script.

SET ECHO OFF

SET FEEDBACK OFF

SET VERIFY OFF

BREAK ON department\_name

COLUMN department\_name HEADING "DEPARTMENT|NAME"

COLUMN last\_name HEADING "EMPLOYEE|NAME"

COLUMN hire\_date HEADING "START|DATE"

COLUMN salary HEADING "SALARY" FORMAT $99,990.00

COLUMN asal HEADING "ANNUAL|SALARY" FORMAT $99,990.00

SELECT d.department\_name, e.last\_name, e.hire\_date,

e.salary, e.salary\*12 asal

FROM   departments d, hr.employees e, locations l

WHERE  e.department\_id = d.department\_id 

AND    d.location\_id   = l.location\_id

AND    l.city          = '&p\_location'

ORDER BY d.department\_name

/

COLUMN department\_name CLEAR

COLUMN last\_name CLEAR

COLUMN hire\_date CLEAR

COLUMN salary CLEAR 

COLUMN asal CLEAR

CLEAR BREAK

SET VERIFY ON

SET FEEDBACK ON

SET ECHO ON

**Introduction to Oracle9*i*: SQL A-23**



<a name="br24"></a> 

**Practice 8 Solutions**

Insert data into the MY\_EMPLOYEE table.

1\. Run the statement in the lab8\_1.sql script to build the MY\_EMPLOYEE table that will be used for

the lab.

CREATE TABLE my\_employee

(id  NUMBER(4) CONSTRAINT my\_employee\_id\_nn NOT NULL,

last\_name VARCHAR2(25),

first\_name VARCHAR2(25),

userid  VARCHAR2(8),

salary  NUMBER(9,2));

2\. Describe the structure of the MY\_EMPLOYEE table to identify the column names.

DESCRIBE my\_employee

3\. Add the first row of data to the MY\_EMPLOYEE table from the following sample data. Do not list the

columns in the INSERT clause.

**ID**

1

**LAST\_NAME FIRST\_NAME USERID**

**SALARY**

895

Patel

Ralph

Betty

Ben

rpatel

2

Dancs

Biri

bdancs

bbiri

860

3

1100

750

4

Newman

Ropeburn

Chad

Audrey

cnewman

aropebur

5

1550

INSERT INTO my\_employee

VALUES (1, 'Patel', 'Ralph', 'rpatel', 895);

4\. Populate the MY\_EMPLOYEE table with the second row of sample data from the preceding list. This

time, list the columns explicitly in the INSERT clause.

INSERT INTO my\_employee (id, last\_name, first\_name, 

userid, salary)

VALUES (2, 'Dancs', 'Betty', 'bdancs', 860);

5\. Confirm your addition to the table.

SELECT   \*

FROM     my\_employee;

**Introduction to Oracle9*i*: SQL A-24**



<a name="br25"></a> 

**Practice 8 Solutions (continued)**

6\. Write an insert statement in a text file named loademp.sql to load rows into the

MY\_EMPLOYEE table. Concatenate the first letter of the first name and the first seven characters of

the last name to produce the userid.

SET ECHO OFF

SET VERIFY OFF

INSERT INTO my\_employee

VALUES (&p\_id, '&p\_last\_name', '&p\_first\_name',

lower(substr('&p\_first\_name', 1, 1) ||

substr('&p\_last\_name', 1, 7)), &p\_salary);

SET VERIFY ON

SET ECHO ON

7\. Populate the table with the next two rows of sample data by running the insert statement in the

script that you created.

SET ECHO OFF

SET VERIFY OFF

INSERT INTO my\_employee

VALUES (&p\_id, '&p\_last\_name', '&p\_first\_name',

lower(substr('&p\_first\_name', 1, 1) ||

substr('&p\_last\_name', 1, 7)), &p\_salary);

SET VERIFY ON

SET ECHO ON

8\. Confirm your additions to the table.

SELECT   \*

FROM my\_employee;

9\. Make the data additions permanent.

COMMIT;

**Introduction to Oracle9*i*: SQL A-25**



<a name="br26"></a> 

**Practice 8 Solutions (continued)**

Update and delete data in the MY\_EMPLOYEE table.

10\. Change the last name of employee 3 to Drexler.

UPDATE  my\_employee

SET     last\_name = 'Drexler'

WHERE   id = 3;

11\. Change the salary to 1000 for all hr.employees with a salary less than 900.

UPDATE  my\_employee

SET     salary = 1000

WHERE   salary < 900;

12\. Verify your changes to the table.

SELECT  last\_name, salary

FROM    my\_employee;

13\. Delete Betty Dancs from the MY\_EMPLOYEE table.

DELETE

FROM  my\_employee

WHERE last\_name = 'Dancs';

14\. Confirm your changes to the table.

SELECT  \*

FROM    my\_employee;

15\. Commit all pending changes.

COMMIT;

Control data transaction to the MY\_EMPLOYEE table.

16\. Populate the table with the last row of sample data by modifying the statements in the script that you

created in step 6. Run the statements in the script.

SET ECHO OFF

SET VERIFY OFF

INSERT INTO my\_employee

VALUES (&p\_id, '&p\_last\_name', '&p\_first\_name',

lower(substr('&p\_first\_name', 1, 1) ||

substr('&p\_last\_name', 1, 7)), &p\_salary);

SET VERIFY ON

SET ECHO ON

**Introduction to Oracle9*i*: SQL A-26**



<a name="br27"></a> 

**Practice 8 Solutions (continued)**

17\. Confirm your addition to the table.

SELECT

\*

FROM my\_employee;

18\. Mark an intermediate point in the processing of the transaction.

SAVEPOINT step\_18;

19\. Empty the entire table.

DELETE

FROM  my\_employee;

20\. Confirm that the table is empty.

SELECT \*

FROM   my\_employee;

21\. Discard the most recent DELETE operation without discarding the earlier INSERT operation.

ROLLBACK TO step\_18;

22\. Confirm that the new row is still intact.

SELECT \*

FROM   my\_employee;

23\. Make the data addition permanent.

COMMIT;

**Introduction to Oracle9*i*: SQL A-27**



<a name="br28"></a> 

**Practice 9 Solutions**

1\. Create the DEPT table based on the following table instance chart. Place the syntax in a script called

lab9\_1.sql, then execute the statement in the script to create the table. Confirm that the table is

created.

**Column Name**

**Key Type**

**Nulls/Unique**

**FK Table**

ID

NAME

**FK Column**

**Data type**

Number

VARCHAR2

**Length**

7

25

CREATE TABLE dept

(id NUMBER(7),

name VARCHAR2(25));

DESCRIBE dept

2\. Populate the DEPT table with data from the DEPARTMENTS table. Include only columns that

you need.

INSERT INTO dept

SELECT  department\_id, department\_name

FROM    departments;

3\. Create the EMP table based on the following table instance chart. Place the syntax in a script called

lab9\_3.sql, and then execute the statement in the script to create the table. Confirm that the table is

created.

**Column Name**

**Key Type**

ID

LAST\_NAME

FIRST\_NAME

DEPT\_ID

**Nulls/Unique**

**FK Table**

**FK Column**

**Data type**

Number

VARCHAR2

VARCHAR2

Number

**Length**

7

25

25

7

**Introduction to Oracle9*i*: SQL A-28**



<a name="br29"></a> 

**Practice 9 Solutions (continued)**

CREATE TABLE  emp

(id           NUMBER(7),

last\_name     VARCHAR2(25),

first\_name    VARCHAR2(25),

dept\_id       NUMBER(7));

DESCRIBE emp

4\. Modify the EMP table to allow for longer employee last names. Confirm your modification.

ALTER TABLE emp

MODIFY (last\_name   VARCHAR2(50));

DESCRIBE emp

5\. Confirm that both the DEPT and EMP tables are stored in the data dictionary. (**Hint:**

USER\_TABLES)

SELECT   table\_name

FROM     user\_tables

WHERE    table\_name IN ('DEPT', 'EMP');

6\. Create the hr.EMPLOYEES2 table based on the structure of the hr.EMPLOYEES table. Include only the

EMPLOYEE\_ID, FIRST\_NAME, LAST\_NAME, SALARY, and DEPARTMENT\_ID columns. Name

the columns in your new table ID, FIRST\_NAME, LAST\_NAME, SALARY , and DEPT\_ID,

respectively.

CREATE TABLE hr.employees2 AS

SELECT  employee\_id id, first\_name, last\_name, salary,

department\_id dept\_id

FROM    hr.employees;

7\. Drop the EMP table.

DROP TABLE emp;

8\. Rename the hr.EMPLOYEES2 table to EMP.

RENAME hr.employees2 TO emp;

**Introduction to Oracle9*i*: SQL A-29**



<a name="br30"></a> 

**Practice 9 Solutions (continued)**

9\. Add a comment to the DEPT and EMP table definitions describing the tables. Confirm your additions

in the data dictionary.

COMMENT ON TABLE emp IS 'Employee Information';

COMMENT ON TABLE dept IS 'Department Information';

SELECT  \*

FROM    user\_tab\_comments

WHERE   table\_name = 'DEPT'

OR      table\_name = 'EMP';

10\. Drop the FIRST\_NAME column from the EMP table. Confirm your modification by checking the

description of the table.

ALTER TABLE emp

DROP COLUMN FIRST\_NAME;

DESCRIBE emp

11\. In the EMP table, mark the DEPT\_ID column in the EMP table as UNUSED. Confirm your

modification by checking the description of the table.

ALTER TABLE

emp

SET   UNUSED (dept\_id);

DESCRIBE emp

12\. Drop all the UNUSED columns from the EMP table. Confirm your modification by checking the

description of the table.

ALTER TABLE emp

DROP UNUSED COLUMNS;

DESCRIBE emp

**Introduction to Oracle9*i*: SQL A-30**



<a name="br31"></a> 

**Practice 10 Solutions**

1\. Add a table-level PRIMARY KEY constraint to the EMP table on the ID column. The constraint

should be named at creation. Name the constraint my\_emp\_id\_pk

ALTER TABLE    emp

ADD CONSTRAINT my\_emp\_id\_pk PRIMARY KEY (id);

2\. Create a PRIMARY KEY constraint to the DEPT table using the ID column. The constraint should

be named at creation. Name the constraint my\_deptid\_pk.

ALTER TABLE    dept

ADD CONSTRAINT my\_deptid\_pk PRIMARY KEY(id);

3\. Add a column DEPT\_ID to the EMP table. Add a foreign key reference on the EMP table that

ensures that the employee is not assigned to a nonexistent department. Name the constraint

my\_emp\_dept\_id\_fk.

ALTER TABLE emp

ADD (dept\_id NUMBER(7));

ALTER TABLE emp

ADD CONSTRAINT my\_emp\_dept\_id\_fk

FOREIGN KEY (dept\_id) REFERENCES dept(id);

4\. Confirm that the constraints were added by querying the USER\_CONSTRAINTS view. Note the

types and names of the constraints. Save your statement text in a file called lab10\_4.sql.

SELECT   constraint\_name, constraint\_type

FROM     user\_constraints

WHERE    table\_name IN ('EMP', 'DEPT');

5\. Display the object names and types from the USER\_OBJECTS data dictionary view for the EMP

and DEPT tables. Notice that the new tables and a new index were created.

SELECT   object\_name, object\_type

FROM     user\_objects

WHERE    object\_name LIKE 'EMP%'

OR       object\_name LIKE 'DEPT%';

If you have time, complete the following exercise:

6\. Modify the EMP table. Add a COMMISSION column of NUMBER data type, precision 2, scale 2.

Add a constraint to the commission column that ensures that a commission value is greater than

zero.

ALTER TABLE EMP

ADD commission NUMBER(2,2)

CONSTRAINT my\_emp\_comm\_ck CHECK (commission >= 0;

**Introduction to Oracle9*i*: SQL A-31**



<a name="br32"></a> 

**Practice 11 Solutions**

1\. Create a view called hr.EMPLOYEES\_VU based on the employee numbers, employee names, and

department numbers from the hr.EMPLOYEES table. Change the heading for the employee name to

EMPLOYEE.

CREATE OR REPLACE VIEW hr.employees\_vu AS

SELECT employee\_id, last\_name employee, department\_id

FROM hr.employees;

2\. Display the contents of the hr.EMPLOYEES\_VU view.

SELECT   \*

FROM     hr.employees\_vu;

3\. Select the view name and text from the USER\_VIEWS data dictionary view.

**Note:** Another view already exists. The EMP\_DETAILS\_VIEW was created as part of your schema.

**Note:** To see more contents of a LONG column, use the iSQL\*Plus command SET LONG n, where

n is the value of the number of characters of the LONG column that you want to see.

SET LONG 600

SELECT   view\_name, text

FROM     user\_views;

4\. Using your hr.EMPLOYEES\_VU view, enter a query to display all employee names and department

numbers.

SELECT   employee, department\_id

FROM     hr.employees\_vu;

5\. Create a view named DEPT50 that contains the employee numbers, employee last names, and

department numbers for all hr.employees in department 50. Label the view columns

EMPNO, EMPLOYEE, and DEPTNO. Do not allow an employee to be reassigned to another

department through the view.

CREATE VIEW dept50 AS

SELECT   employee\_id empno, last\_name employee,

department\_id deptno

FROM     hr.employees

WHERE    department\_id = 50

WITH CHECK OPTION CONSTRAINT emp\_dept\_50;

**Introduction to Oracle9*i*: SQL A-32**



<a name="br33"></a> 

**Practice 11 Solutions (continued)**

6\. Display the structure and contents of the DEPT50 view.

DESCRIBE dept50

SELECT   \*

FROM     dept50;

7\. Attempt to reassign Matos to department 80.

UPDATE   dept50

SET      deptno = 80

WHERE    employee = 'Matos';

If you have time, complete the following exercise:

8\. Create a view called SALARY\_VU based on the employee last names, department names, salaries,

and salary grades for all hr.employees. Use the hr.EMPLOYEES, DEPARTMENTS, and JOB\_GRADES

tables. Label the columns Employee, Department, Salary, and Grade, respectively.

CREATE OR REPLACE VIEW salary\_vu

AS

SELECT e.last\_name "Employee",

d.department\_name  "Department",

e.salary "Salary",

j.grade\_level "Grades"

FROM   hr.employees e,

departments d,

job\_grades j

WHERE  e.department\_id = d.department\_id

AND    e.salary BETWEEN j.lowest\_sal and j.highest\_sal;

**Introduction to Oracle9*i*: SQL A-33**



<a name="br34"></a> 

**Practice 12 Solutions**

1\. Create a sequence to be used with the primary key column of the DEPT table. The sequence should

start at 200 and have a maximum value of 1000. Have your sequence increment by ten numbers.

Name the sequence DEPT\_ID\_SEQ.

CREATE SEQUENCE dept\_id\_seq

START WITH 200

INCREMENT BY 10

MAXVALUE 1000;

2\. Write a query in a script to display the following information about your sequences: sequence name,

maximum value, increment size, and last number. Name the script lab12\_2.sql. Run the

statement in your script.

SELECT   sequence\_name, max\_value, increment\_by, last\_number

FROM     user\_sequences;

3\. Write a script to insert two rows into the DEPT table. Name your script

lab12\_3.sql.

Be sure to use the sequence that you created for the ID column. Add two departments named

Education and Administration. Confirm your additions. Run the commands in your script.

INSERT INTO dept

VALUES (dept\_id\_seq.nextval, 'Education');

INSERT INTO dept

VALUES (dept\_id\_seq.nextval, 'Administration');

4\. Create a nonunique index on the foreign key column (DEPT\_ID) in the EMP table.

CREATE INDEX emp\_dept\_id\_idx ON emp (dept\_id);

5\. Display the indexes and uniqueness that exist in the data dictionary for the EMP table. Save the

statement into a script named lab12\_5.sql.

SELECT   index\_name, table\_name, uniqueness

FROM     user\_indexes

WHERE    table\_name = 'EMP';

**Introduction to Oracle9*i*: SQL A-34**



<a name="br35"></a> 

**Practice 13 Solutions**

1\. What privilege should a user be given to log on to the Oracle Server? Is this a system or an object

privilege?

**The** CREATE SESSION **system privilege**

2\. What privilege should a user be given to create tables?

**The** CREATE TABLE **privilege**

3\. If you create a table, who can pass along privileges to other users on your table?

**You can, or anyone you have given those privileges to by using t he** WITH GRANT 

OPTION**.**

4\. You are the DBA. You are creating many users who require the same system privileges.

What should you use to make your job easier?

**Create a role containing the system privileges and grant the role to the users**

5\. What command do you use to change your password?

**The** ALTER USER **statement**

6\. Grant another user access to your DEPARTMENTS table. Have the user grant you query access to his

or her DEPARTMENTS table.

Team 2 executes the GRANT statement.

GRANT select

ON    departments

TO    <user1>;

Team 1 executes the GRANT statement.

GRANT select

ON    departments

TO    <user2>;

WHERE user1 is the name of team 1 and user2 is the name of team 2.

7\. Query all the rows in your DEPARTMENTS table.

SELECT  \*

FROM    departments;

**Introduction to Oracle9*i*: SQL A-35**



<a name="br36"></a> 

**Practice 13 Solutions (continued)**

8\. Add a new row to your DEPARTMENTS table. Team 1 should add Education as department

number 500. Team 2 should add Human Resources department number 510. Query the other team’s

table.

Team 1 executes this INSERT statement.

INSERT INTO departments(department\_id, department\_name)

VALUES (200, 'Education');

COMMIT;

Team 2 executes this INSERT statement.

INSERT INTO departments(department\_id, department\_name)

VALUES (210, 'Administration');

COMMIT;

9\. Create a synonym for the other team’s DEPARTMENTS table.

Team 1 creates a synonym named team2.

CREATE SYNONYM

team2

FOR <user2>.DEPARTMENTS;

Team 2 creates a synonym named team1.

CREATE SYNONYM

team1

FOR <user1>. DEPARTMENTS;

10\. Query all the rows in the other team’s DEPARTMENTS table by using your synonym.

Team 1 executes this SELECT statement.

SELECT  \*

FROM    team2;

Team 2 executes this SELECT statement.

SELECT  \*

FROM    team1;

**Introduction to Oracle9*i*: SQL A-36**



<a name="br37"></a> 

**Practice 13 Solutions (continued)**

11\. Query the USER\_TABLES data dictionary to see information about the tables that you own.

SELECT  table\_name

FROM    user\_tables;

12\. Query the ALL\_TABLES data dictionary view to see information about all the tables that you

can access. Exclude tables that you own.

SELECT  table\_name, owner

FROM    all\_tables

WHERE   owner  <> ***<your account>;***

13\. Revoke the SELECT privilege from the other team.

Team 1 revokes the privilege.

REVOKE select

ON     departments

FROM

user2;

Team 2 revokes the privilege.

REVOKE select

ON     departments 

FROM

user1;

**Introduction to Oracle9*i*: SQL A-37**



<a name="br38"></a> 

**Practice 14 Solutions**

1\. Create the tables based on the following table instance charts. Choose the appropriate data types and

be sure to add integrity constraints.

a. Table name: MEMBER

**Column\_** MEMBER\_

**Name**

LAST\_

NAME

FIRST\_NAM ADDRESS

E

CITY

PHONE

JOIN

\_

DATE

ID

**Key**

PK

**Type**

**Null/**

NN,U

NN

NN

**Unique**

**Default**

**Value**

System

Date

**Data**

NUMBER

VARCHAR2

VARCHAR2

VARCHAR2

VARCHAR2

VARCHAR2

DATE

**Type**

**Length**

10

25

25

100

30

15

CREATE TABLE member

(member\_id

NUMBER(10)

CONSTRAINT member\_member\_id\_pk PRIMARY KEY,

VARCHAR2(25)

last\_name

CONSTRAINT member\_last\_name\_nn NOT NULL,

VARCHAR2(25),

first\_name

address

VARCHAR2(100),

city VARCHAR2(30),

phone

VARCHAR2(15),

join\_date

DATE DEFAULT SYSDATE

CONSTRAINT member\_join\_date\_nn NOT NULL);

**Introduction to Oracle9*i*: SQL A-38**



<a name="br39"></a> 

**Practice 14 Solutions (continued)**

b. Table name: TITLE

**Column\_**

**Name**

TITLE\_ID

TITLE

DESCRIPTION

RATING

CATEGORY

RELEASE\_

DATE

**Key**

PK

**Type**

**Null/**

NN,U

NN

NN

**Unique**

**Check**

G, PG, R,

NC17, NR

DRAMA,

COMEDY,

ACTION,

CHILD,

SCIFI,

DOCUMEN-

TARY

**Data Type** NUMBER

**Length** 10

VARCHAR2

VARCHAR2

VARCHAR2

VARCHAR2

DATE

60

400

4

20

CREATE TABLE title

(title\_id NUMBER(10)

CONSTRAINT title\_title\_id\_pk PRIMARY KEY,

title

VARCHAR2(60)

CONSTRAINT title\_title\_nn NOT NULL,

description

VARCHAR2(400)

CONSTRAINT title\_description\_nn NOT NULL,

rating

VARCHAR2(4)

CONSTRAINT title\_rating\_ck CHECK

(rating IN ('G', 'PG', 'R', 'NC17', 'NR')),

category VARCHAR2(20),

CONSTRAINT title\_category\_ck CHECK

(category IN ('DRAMA', 'COMEDY', 'ACTION',

'CHILD', 'SCIFI', 'DOCUMENTARY')),

release\_date DATE);

**Introduction to Oracle9*i*: SQL A-39**



<a name="br40"></a> 

**Practice 14 Solutions (continued)**

c. Table name: TITLE\_COPY

**Column**

**Name**

**Key**

COPY\_ID

TITLE\_ID

PK,FK

STATUS

PK

**Type**

**Null/**

NN,U

NN,U

NN

**Unique**

**Check**

AVAILABLE,

DESTROYED,

RENTED,

RESERVED

**FK Ref**

**Table**

TITLE

**FK Ref**

**Column**

**Data**

TITLE\_ID

NUMBER

NUMBER

VARCHAR2

**Type**

**Length**

10

10

15

CREATE TABLE title\_copy

(copy\_id

title\_id

NUMBER(10),

NUMBER(10)

CONSTRAINT  title\_copy\_title\_if\_fk REFERENCES title(title\_id),

status VARCHAR2(15)

CONSTRAINT title\_copy\_status\_nn NOT NULL

CONSTRAINT title\_copy\_status\_ck CHECK (status IN

('AVAILABLE', 'DESTROYED','RENTED', 'RESERVED')),

CONSTRAINT  title\_copy\_copy\_id\_title\_id\_pk

PRIMARY KEY (copy\_id, title\_id));

**Introduction to Oracle9*i*: SQL A-40**



<a name="br41"></a> 

**Practice 14 Solutions (continued)**

d. Table name: RENTAL

**Column**

**Name**

**Key**

BOOK\_

DATE

MEMBER\_

ID

COPY\_

ID

ACT\_RET\_ EXP\_RET\_ TITLE\_

DATE

DATE

ID

PK

PK,FK1

PK,FK2

PK,FK2

**Type**

**Default**

**Value**

**FK Ref**

**Table**

**FK Ref**

**Column**

**Data**

System

Date

System Date

\+ 2 days

MEMBER

TITLE\_

COPY

TITLE\_

COPY

TITLE\_ID

MEMBER\_I COPY\_

D

NUMBER

ID

DATE

NUMBER DATE

DATE

NUMBER

**Type**

**Length**

10

10

10

CREATE TABLE rental

(book\_date

member\_id

DATE DEFAULT SYSDATE,

NUMBER(10)

CONSTRAINT rental\_member\_id\_fk

REFERENCES  member(member\_id),

copy\_id NUMBER(10),

act\_ret\_date DATE,

exp\_ret\_date DATE DEFAULT SYSDATE + 2,

title\_id

NUMBER(10),

CONSTRAINT  rental\_book\_date\_copy\_title\_pk

PRIMARY KEY (book\_date, member\_id,

copy\_id,title\_id),

CONSTRAINT  rental\_copy\_id\_title\_id\_fk

FOREIGN KEY (copy\_id, title\_id)

REFERENCES title\_copy(copy\_id, title\_id));

**Introduction to Oracle9*i*: SQL A-41**



<a name="br42"></a> 

**Practice 14 Solutions (continued)**

e. Table name: RESERVATION

**Column**

**Name**

**Key**

RES\_

DATE

MEMBER\_

ID

TITLE\_

ID

PK

PK,FK1

PK,FK2

**Type**

**Null/**

NN,U

NN,U

NN

**Unique**

**FK Ref**

**Table**

MEMBER

TITLE

**FK Ref**

MEMBER\_ID

TITLE\_ID

**Column**

**Data Type**

DATE

NUMBER

NUMBER

**Length**

10

10

CREATE TABLE reservation

(res\_date

member\_id

DATE,

NUMBER(10)

CONSTRAINT  reservation\_member\_id

REFERENCES member(member\_id),

title\_id

NUMBER(10)

CONSTRAINT  reservation\_title\_id

REFERENCES title(title\_id),

CONSTRAINT reservation\_resdate\_mem\_tit\_pk PRIMARY KEY

(res\_date, member\_id, title\_id));

**Introduction to Oracle9*i*: SQL A-42**



<a name="br43"></a> 

**Practice 14 Solutions (continued)**

2\. Verify that the tables and constraints were created properly by checking the data dictionary.

SELECT   table\_name

FROM     user\_tables

WHERE    table\_name IN ('MEMBER', 'TITLE', 'TITLE\_COPY',

'RENTAL', 'RESERVATION');

SELECT   constraint\_name, constraint\_type, table\_name

FROM     user\_constraints

WHERE    table\_name IN ('MEMBER', 'TITLE', 'TITLE\_COPY',

'RENTAL', 'RESERVATION');

3\. Create sequences to uniquely identify each row in the MEMBER table and the TITLE table.

a. Member number for the MEMBER table: start with 101; do not allow caching of the

values. Name the sequence MEMBER\_ID\_SEQ.

CREATE SEQUENCE member\_id\_seq

START WITH 101

NOCACHE;

b. Title number for the TITLE table: start with 92; no caching. Name the sequence

TITLE\_ID\_SEQ.

CREATE SEQUENCE title\_id\_seq

START WITH 92

NOCACHE;

c. Verify the existence of the sequences in the data dictionary.

SELECT  sequence\_name, increment\_by, last\_number

FROM    user\_sequences

WHERE   sequence\_name IN ('MEMBER\_ID\_SEQ', 'TITLE\_ID\_SEQ ');

**Introduction to Oracle9*i*: SQL A-43**



<a name="br44"></a> 

**Practice 14 Solutions (continued)**

4\. Add data to the tables. Create a script for each set of data to add.

a. Add movie titles to the TITLE table. Write a script to enter the movie information. Save the

statements in a script named lab14\_4a.sql*.* Use the sequences to uniquely identify each

title. Enter the release dates in the DD-MON-YYYY format. Remember that single quotation

marks in a character field must be specially handled. Verify your additions.

SET ECHO OFF

INSERT INTO title(title\_id, title, description, rating, 

category, release\_date)

VALUES (title\_id\_seq.NEXTVAL, 'Willie and Christmas Too',

'All of Willie''s friends make a Christmas list for

Santa, but Willie has yet to add his own wish list.',

'G', 'CHILD', TO\_DATE('05-OCT-1995','DD-MON-YYYY')

/

INSERT INTO title(title\_id , title, description, rating,

category, release\_date)

VALUES (title\_id\_seq.NEXTVAL, 'Alien Again', 'Yet another

installment of science fiction history.  Can the

heroine save the planet from the alien life form?',

'R', 'SCIFI', TO\_DATE( '19-MAY-1995','DD-MON-YYYY'))

/

INSERT INTO title(title\_id, title, description, rating,

category, release\_date)

VALUES (title\_id\_seq.NEXTVAL, 'The Glob', 'A meteor crashes

near a small American town and unleashes carnivorous

goo in this classic.', 'NR', 'SCIFI', 

TO\_DATE( '12-AUG-1995','DD-MON-YYYY'))

/

INSERT INTO title(title\_id, title, description, rating,

category, release\_date)

VALUES (title\_id\_seq.NEXTVAL, 'My Day Off', 'With a little

luck and a lot ingenuity, a teenager skips school for

a day in New York.', 'PG', 'COMEDY', 

TO\_DATE( '12-JUL-1995','DD-MON-YYYY'))

/

...

COMMIT

/

SET ECHO ON

SELECT  title

FROM    title;

**Introduction to Oracle9*i*: SQL A-44**



<a name="br45"></a> 

**Practice 14 Solutions (continued)**

**Title**

**Description**

**Rating**

**Category**

**Release\_date**

Willie and

Christmas

Too

All of Willie’s friends

make a Christmas list for

Santa, but Willie has yet to

add his own wish list.

G

CHILD

05-OCT-1995

Alien Again

Yet another installation of

science fiction history. Can

the heroine save the planet

from the alien life form?

R

SCIFI

SCIFI

19-MAY-1995

12-AUG-1995

The Glob

A meteor crashes near a

small American town and

unleashes carnivorous goo

in this classic.

NR

My Day Off

With a little luck and a lot

of ingenuity, a teenager

skips school for a day in

New York

PG

PG

NR

COMEDY 12-JUL-1995

Miracles on

Ice

A six-year-old has doubts

about Santa Claus, but she

discovers that miracles

really do exist.

DRAMA

ACTION

12-SEP-1995

01-JUN-1995

Soda Gang

After discovering a cache

of drugs, a young couple

find themselves pitted

against a vicious gang.

**Introduction to Oracle9*i*: SQL A-45**



<a name="br46"></a> 

**Practice 14 Solutions (continued)**

b. Add data to the MEMBER table. Place the insert statements in a script named

lab14\_4b.sql. Execute commands in the script. Be sure to use the sequence to add the

member numbers.

**First\_**

**Name**

**Last\_Name Address**

**City**

**Phone**

**Join\_Date**

Carmen

LaDoris

Midori

Mark

Velasquez

Ngao

283 King Street Seattle

206-899-6666 08-MAR-1990

586-355-8882 08-MAR-1990

254-852-5764 17-JUN-1991

5 Modrany

Bratislava

Nagayama

68 Via Centrale Sao Paolo

Quick-to-

See

6921 King

Way

Lagos

Hong Kong 41-559-87

Quebec

63-559-7777

07-APR-1990

18-JAN-1991

Audry

Molly

Ropeburn

86 Chu Street

Urguhart

3035 Laurier

418-542-9988 18-JAN-1991

SET ECHO OFF

SET VERIFY OFF

INSERT INTO member(member\_id, first\_name, last\_name, address,

city, phone, join\_date)

VALUES (member\_id\_seq.NEXTVAL, '&first\_name', '&last\_name',

'&address', '&city', '&phone', TO\_DATE('&join\_date',

'DD-MM-YYYY');

COMMIT;

SET VERIFY ON

SET ECHO ON

**Introduction to Oracle9*i*: SQL A-46**



<a name="br47"></a> 

**Practice 14 Solutions (continued)**

c. Add the following movie copies in the TITLE\_COPY table:

**Note:** Have the TITLE\_ID numbers available for this exercise.

**Title**

**Copy\_Id**

**Status**

Willie and Christmas Too

Alien Again

1

1

2

1

1

2

3

1

1

AVAILABLE

AVAILABLE

RENTED

AVAILABLE

AVAILABLE

AVAILABLE

RENTED

The Glob

My Day Off

Miracles on Ice

Soda Gang

AVAILABLE

AVAILABLE

INSERT INTO title\_copy(copy\_id, title\_id, status)

VALUES (1, 92, 'AVAILABLE');

INSERT INTO title\_copy(copy\_id, title\_id, status)

VALUES (1, 93, 'AVAILABLE');

INSERT INTO title\_copy(copy\_id, title\_id, status)

VALUES (2, 93, 'RENTED');

INSERT INTO title\_copy(copy\_id, title\_id, status)

VALUES (1, 94, 'AVAILABLE');

INSERT INTO title\_copy(copy\_id, title\_id, status)

VALUES (1, 95, 'AVAILABLE');

INSERT INTO title\_copy(copy\_id, title\_id,status)

VALUES (2, 95, 'AVAILABLE');

INSERT INTO title\_copy(copy\_id, title\_id,status)

VALUES (3, 95, 'RENTED');

INSERT INTO title\_copy(copy\_id, title\_id,status) 

VALUES (1, 96, 'AVAILABLE');

INSERT INTO title\_copy(copy\_id, title\_id,status)

VALUES (1, 97, 'AVAILABLE');

**Introduction to Oracle9*i*: SQL A-47**



<a name="br48"></a> 

**Practice 14 Solutions (continued)**

d. Add the following rentals to the RENTAL table:

**Note:** Title number may be different depending on sequence number.

**Title\_ Copy\_**

**Member\_**

**Id**

**Id**

**Id**

**Book\_date**

**Exp\_Ret\_Date**

**Act\_Ret\_Date**

92

1

101

101

102

106

3 days ago

1 day ago

2 days ago

93

95

97

2

3

1

1 day ago

2 days ago

4 days ago

1 day from now

Today

2 days ago

2 days ago

INSERT INTO rental(title\_id, copy\_id, member\_id,

book\_date, exp\_ret\_date, act\_ret\_date)

VALUES (92, 1, 101, sysdate-3, sysdate-1, sysdate-2);

INSERT INTO rental(title\_id, copy\_id, member\_id,

book\_date, exp\_ret\_date, act\_ret\_date)

VALUES (93, 2, 101, sysdate-1, sysdate-1, NULL);

INSERT INTO rental(title\_id, copy\_id, member\_id,

book\_date, exp\_ret\_date, act\_ret\_date)

VALUES (95, 3, 102, sysdate-2, sysdate, NULL);

INSERT INTO rental(title\_id, copy\_id, member\_id,

book\_date,  exp\_ret\_date,act\_ret\_date)

VALUES (97, 1, 106, sysdate-4, sysdate-2, sysdate-2);

COMMIT;

**Introduction to Oracle9*i*: SQL A-48**



<a name="br49"></a> 

**Practice 14 Solutions (continued)**

5\. Create a view named TITLE\_AVAIL to show the movie titles and the availability of

each copy and its expected return date if rented. Query all rows from the view. Order the results by

title.

CREATE VIEW title\_avail AS

SELECT   t.title, c.copy\_id, c.status, r.exp\_ret\_date

FROM     title t, title\_copy c, rental r

WHERE    t.title\_id = c.title\_id

AND      c.copy\_id = r.copy\_id(+)

AND      c.title\_id = r.title\_id(+);

SELECT   \*

FROM     title\_avail

ORDER BY title, copy\_id;

6\. Make changes to data in the tables.

a. Add a new title. The movie is “Interstellar Wars,” which is rated PG and classified as a

scifi movie. The release date is 07-JUL-77. The description is “Futuristic interstellar

action movie. Can the rebels save the humans from the evil empire?” Be sure to add a title

copy record for two copies.

INSERT INTO title(title\_id, title, description, rating,

category, release\_date)

VALUES (title\_id\_seq.NEXTVAL, 'Interstellar Wars',

'Futuristic interstellar action movie.  Can the

rebels save the humans from the evil Empire?',

'PG', 'SCIFI', '07-JUL-77');

INSERT INTO title\_copy (copy\_id, title\_id, status)

VALUES (1, 98, 'AVAILABLE');

INSERT INTO title\_copy (copy\_id, title\_id, status)

VALUES (2, 98, 'AVAILABLE');

b. Enter two reservations. One reservation is for Carmen Velasquez, who wants to rent

“Interstellar Wars.” The other is for Mark Quick-to-See, who wants to rent “Soda Gang.”

INSERT INTO reservation (res\_date, member\_id, title\_id)

VALUES (SYSDATE, 101, 98);

INSERT INTO reservation (res\_date, member\_id, title\_id)

VALUES (SYSDATE, 104, 97);

**Introduction to Oracle9*i*: SQL A-49**



<a name="br50"></a> 

**Practice 14 Solutions (continued)**

c. Customer Carmen Velasquez rents the movie “Interstellar Wars,” copy 1. Remove her

reservation for the movie. Record the information about the rental. Allow the default

value for the expected return date to be used. Verify that the rental was recorded by using

the view you created.

INSERT INTO rental(title\_id, copy\_id, member\_id)

VALUES (98,1,101);

UPDATE title\_copy

SET    status= 'RENTED'

WHERE  title\_id = 98

AND    copy\_id = 1;

DELETE

FROM   reservation

WHERE  member\_id = 101;

SELECT   \*

FROM     title\_avail

ORDER BY title, copy\_id;

7\. Make a modification to one of the tables.

a. Add a PRICE column to the TITLE table to record the purchase price of the video. The

column should have a total length of eight digits and two decimal places. Verify your

modifications.

ALTER TABLE title

ADD  (price NUMBER(8,2));

DESCRIBE title

**Introduction to Oracle9*i*: SQL A-50**



<a name="br51"></a> 

**Practice 14 Solutions (continued)**

b. Create a script named lab14\_7b.sql that contains update statements that update each

video with a price according to the following list. Run the commands in the script.

**Note:** Have the TITLE\_ID numbers available for this exercise.

**Title**

**Price**

Willie and Christmas Too

Alien Again

The Glob

My Day Off

Miracles on Ice

Soda Gang

25

35

35

35

30

35

29

Interstellar Wars

SET ECHO OFF

SET VERIFY OFF

DEFINE price=

DEFINE title\_id=

UPDATE title

SET    price = &price

WHERE  title\_id = &title\_id;

SET VERIFY OFF

SET ECHO OFF

c. Ensure that in the future all titles contain a price value. Verify the constraint.

ALTER TABLE title

MODIFY (price CONSTRAINT title\_price\_nn NOT NULL);

SELECT  constraint\_name, constraint\_type,

search\_condition

FROM    user\_constraints

WHERE   table\_name = 'TITLE';

**Introduction to Oracle9*i*: SQL A-51**



<a name="br52"></a> 

**Practice 14 Solutions (continued)**

8\. Create a report titled Customer History Report. This report contains each customer's

history of renting videos. Be sure to include the customer name, movie rented, dates of the

rental, and duration of rentals. Total the number of rentals for all customers for the reporting

period. Save the commands that generate the report in a script file named lab14\_8.sql*.*

SET ECHO OFF

SET VERIFY OFF

TTITLE 'Customer History Report'

BREAK ON member  SKIP 1 ON REPORT

SELECT

m.first\_name||' '||m.last\_name MEMBER, t.title, 

r.book\_date, r.act\_ret\_date - r.book\_date DURATION

member m, title t, rental r

r.member\_id = m.member\_id

r.title\_id = t.title\_id

FROM

WHERE

AND

ORDER BY member;

CLEAR BREAK

TTITLE OFF

SET VERIFY ON

SET ECHO ON

**Introduction to Oracle9*i*: SQL A-52**



<a name="br53"></a> 

**Practice 15 Solutions**

1\. List the department IDs for departments that do not contain the job ID ST\_CLERK, using SET

operators.

SELECT department\_id

FROM   departments

MINUS

SELECT department\_id

FROM   hr.employees

WHERE  job\_id = 'ST\_CLERK';

2\. Display the country ID and the name of the countries that have no departments located in them,

using SET operators.

SELECT  country\_id,country\_name

FROM   countries

MINUS

SELECT  l.country\_id,c.country\_name

FROM   locations l,   countries c

WHERE  l.country\_id = c.country\_id;

3\. Produce a list of jobs for departments 10, 50, and 20, in that order. Display job ID and

department ID, using SET operators.

COLUMN dummy PRINT

SELECT  job\_id, department\_id, 'x' dummy

FROM    hr.employees

WHERE department\_id = 10

UNION

SELECT  job\_id, department\_id, 'y' 

FROM    hr.employees

WHERE department\_id = 50

UNION

SELECT  job\_id, department\_id, 'z' 

FROM    hr.employees

WHERE department\_id = 20

ORDER BY  3;

COLUMN dummy NOPRINT

**Introduction to Oracle9*i*: SQL A-53**



<a name="br54"></a> 

**Practice 15 Solutions (continued)**

4\. List the employee IDs and job IDs of those hr.employees, who are currently in the job title that they

have held once before during their tenure with the company.

SELECT    employee\_id,job\_id

FROM      hr.employees

INTERSECT

SELECT   employee\_id,job\_id

FROM     job\_history;

5\. Write a compond query that lists the following :

•

Last names and department ID of all the hr.employees from the hr.EMPLOYEES table, irrespective

of whether they belong to any department

•

Department ID and department name of all the departments from the DEPARTMENTS table,

irrespective of whether they have hr.employees working in them

SELECT  last\_name,department\_id,TO\_CHAR(null)

FROM   hr.employees

UNION

SELECT  TO\_CHAR(null),department\_id,department\_name

FROM  departments;

**Introduction to Oracle9*i*: SQL A-54**



<a name="br55"></a> 

**Practice 16 Solutions**

1\. Alter the session to set the NLS\_DATE\_FORMAT to DD-MON-YYYY HH24:MI:SS.

ALTER SESSION SET NLS\_DATE\_FORMAT = 

'DD-MON-YYYY HH24:MI:SS';

2\. a. Write queries to display the time zone offsets (TZ\_OFFSET) for the following time zones.

*US/Pacific-New*

SELECT TZ\_OFFSET ('US/Pacific-New') from dual;

*Singapore*

SELECT TZ\_OFFSET ('Singapore') from dual;

*Egypt*

SELECT TZ\_OFFSET ('Egypt') from dual;

b. Alter the session to set the TIME\_ZONE parameter value to the time zone offset of

US/Pacific-New.

ALTER SESSION SET TIME\_ZONE = '-8:00';

c. Display the CURRENT\_DATE, CURRENT\_TIMESTAMP, and LOCALTIMESTAMP for this

session.

**Note**: The output might be different based on the date when the command is executed.

SELECT CURRENT\_DATE, CURRENT\_TIMESTAMP, LOCALTIMESTAMP

FROM DUAL; 

d. Alter the session to set the TIME\_ZONE parameter value to the time zone offset of

Singapore.

ALTER SESSION SET TIME\_ZONE = '+8:00';

e. Display the CURRENT\_DATE, CURRENT\_TIMESTAMP, LOCALTIMESTAMP for this

session.

**Note**: The output might be different based on the date when the command is executed.

SELECT CURRENT\_DATE, CURRENT\_TIMESTAMP, LOCALTIMESTAMP

FROM DUAL;

3\. Write a query to display the DBTIMEZONE and SESSIONTIMEZONE.

SELECT  DBTIMEZONE,SESSIONTIMEZONE

FROM DUAL;

**Introduction to Oracle9*i*: SQL A-55**



<a name="br56"></a> 

**Practice 16 Solutions (continued)**

4\. Write a query to extract the YEAR from HIRE\_DATE column of the hr.EMPLOYEES table for those

hr.employees who work in department 80.

SELECT last\_name, EXTRACT (YEAR FROM HIRE\_DATE)

FROM hr.employees

WHERE department\_id = 80;

**Introduction to Oracle9*i*: SQL A-56**



<a name="br57"></a> 

**Practice 17 Solutions**

1\. Write a query to display the following for those hr.employees whose manager ID is less than 120:

–

–

–

–

Manager ID

Job ID and total salary for every job ID for hr.employees who report to the same manager

Total salary of those managers

Total salary of those managers, irrespective of the job IDs

SELECT  manager\_id,job\_id,sum(salary)

FROM   hr.employees

WHERE manager\_id < 120

GROUP BY ROLLUP(manager\_id,job\_id);

2\. Observe the output from question 1. Write a query using the GROUPING function to determine

whether the NULL values in the columns corresponding to the GROUP BY expressions are caused by

the ROLLUP operation.

SELECT manager\_id MGR ,job\_id JOB,

sum(salary),GROUPING(manager\_id),GROUPING(job\_id)

FROM   hr.employees

WHERE manager\_id < 120

GROUP BY ROLLUP(manager\_id,job\_id);

3\. Write a query to display the following for those hr.employees whose manager ID is

less than 120 :

–

–

–

–

Manager ID

Job and total salaries for every job for hr.employees who report to the same manager

Total salary of those managers

Cross-tabulation values to display the total salary for every job, irrespective of the

manager

–

Total salary irrespective of all job titles

SELECT manager\_id, job\_id, sum(salary)

FROM   hr.employees

WHERE manager\_id < 120

GROUP BY CUBE(manager\_id, job\_id);

**Introduction to Oracle9*i*: SQL A-57**



<a name="br58"></a> 

**Practice 17 Solutions (continued)**

4\. Observe the output from question 3. Write a query using the GROUPING function to determine

whether the NULL values in the columns corresponding to the GROUP BY expressions are

caused by the CUBE operation.

SELECT manager\_id MGR ,job\_id JOB,

sum(salary),GROUPING(manager\_id),GROUPING(job\_id)

FROM   hr.employees

WHERE manager\_id < 120

GROUP BY CUBE(manager\_id,job\_id);

5\. Using GROUPING SETS, write a query to display the following groupings :

–

–

–

department\_id, manager\_id, job\_id

department\_id, job\_id

Manager\_id,  job\_id

The query should calculate the sum of the salaries for each of these groups.

SELECT department\_id, manager\_id, job\_id,  SUM(salary)

FROM hr.employees

GROUP BY 

GROUPING SETS ((department\_id, manager\_id, job\_id),

(department\_id,  job\_id),(manager\_id,job\_id));

**Introduction to Oracle9*i*: SQL A-58**



<a name="br59"></a> 

**Practice 18 Solutions**

1\. Write a query to display the last name, department number, and salary of any employee whose

department number and salary both match the department number and salary of any employee who

earns a commission.

SELECT last\_name, department\_id, salary

FROM   hr.employees

WHERE  (salary, department\_id) IN 

(SELECT  salary, department\_id

FROM    hr.employees

WHERE   commission\_pct IS NOT NULL);

2\. Display the last name, department name, and salary of any employee whose salary and commission

match the salary and commission of any employee located in location ID1700.

SELECT last\_name, department\_name, salary

FROM   hr.employees e, departments d

WHERE  e.department\_id = d.department\_id

AND   (salary, NVL(commission\_pct,0)) IN 

(SELECT salary, NVL(commission\_pct,0)

FROM

WHERE

AND

hr.employees e, departments  d

e.department\_id = d.department\_id

d.location\_id = 1700);

3\. Create a query to display the last name, hire date, and salary for all hr.employees who have the same

salary and commission as Kochhar.

**Note:** Do not display Kochhar in the result set.

SELECT last\_name, hire\_date, salary

FROM   hr.employees

WHERE  (salary, NVL(commission\_pct,0)) IN 

(SELECT salary, NVL(commission\_pct,0)

FROM

WHERE  last\_name = 'Kochhar')

AND last\_name != 'Kochhar';

hr.employees

4\. Create a query to display the hr.employees who earn a salary that is higher than the salary of

all of the sales managers (JOB\_ID = 'SA\_MAN'). Sort the results on salary from highest to

lowest.

SELECT last\_name, job\_id, salary

FROM   hr.employees

WHERE  salary > ALL 

(SELECT salary

FROM   hr.employees

WHERE  job\_id = 'SA\_MAN')

ORDER BY salary DESC;

**Introduction to Oracle9*i*: SQL A-59**



<a name="br60"></a> 

**Practice 18 Solutions (continued)**

5\. Display the details of the employee ID, last name, and department ID of those hr.employees who live

in cities whose name begins with *T*.

SELECT employee\_id, last\_name, department\_id

FROM   hr.employees

WHERE  department\_id IN (SELECT department\_id

FROM departments

WHERE location\_id IN

(SELECT  location\_id

FROM locations

WHERE city LIKE 'T%'));

6\. Write a query to find all hr.employees who earn more than the average salary in their departments.

Display last name, salary, department ID, and the average salary for the department. Sort by average

salary. Use alises for the columns retrieved by the query as shown in the sample output.

SELECT e.last\_name ename, e.salary salary, 

e.department\_id deptno, AVG(a.salary) dept\_avg

FROM    hr.employees e, hr.employees a

WHERE   e.department\_id = a.department\_id

AND     e.salary > (SELECT AVG(salary)

FROM   hr.employees

WHERE  department\_id = e.department\_id )

GROUP BY e.last\_name, e.salary, e.department\_id

ORDER BY AVG(a.salary);

7\. Find all hr.employees who are not supervisors.

a. First do this by using the NOT EXISTS operator.

SELECT outer.last\_name

FROM    hr.employees outer

WHERE  NOT EXISTS (SELECT 'X'

FROM hr.employees inner

WHERE inner.manager\_id = 

outer.employee\_id);

**Introduction to Oracle9*i*: SQL A-60**



<a name="br61"></a> 

**Practice 18 Solutions (continued)**

b. Can this be done by using the NOT IN operator? How, or why not?

SELECT outer.last\_name

FROM   hr.employees outer

WHERE  outer.employee\_id 

NOT IN (SELECT inner.manager\_id

FROM   hr.employees inner);

This alternative solution is not a good one. The subquery picks up a NULL value, so the entire

query returns no rows. The reason is that all conditions that compare a NULL value result in

NULL. Whenever NULL values are likely to be part of the value set, *do not* use NOT IN as a

substitute for NOT EXISTS.

8\. Write a query to display the last names of the hr.employees who earn less than the average salary in

their departments.

SELECT last\_name

FROM    hr.employees outer

WHERE outer.salary < (SELECT AVG(inner.salary)

FROM hr.employees inner

WHERE inner.department\_id 

= outer.department\_id);

9\. Write a query to display the last names who have one or more coworkers in their departments with

later hire dates but higher salaries.

SELECT  last\_name

FROM    hr.employees outer

WHERE EXISTS (SELECT 'X'

FROM hr.employees inner

WHERE inner.department\_id = 

outer.department\_id

AND inner.hire\_date > outer.hire\_date

AND inner.salary > outer.salary);

10\. Write a query to display the employee ID, last names of the hr.employees, and department names of all

hr.employees.

**Note**: Use a scalar subquery to retrieve the department name in the SELECT statement.

SELECT employee\_id, last\_name, 

(SELECT department\_name

FROM departments d

WHERE   e.department\_id =

d.department\_id ) department

FROM hr.employees e

ORDER BY department;

**Introduction to Oracle9*i*: SQL A-61**



<a name="br62"></a> 

**Practice 18 Solutions (continued)**

11\. Write a query to display the department names of those departments whose total salary cost is above

one-eighth (1/8) of the total salary cost of the whole company. Use the WITH clause to write this

query. Name the query SUMMARY.

WITH

summary AS (

SELECT department\_name, SUM(salary) AS dept\_total

FROM hr.employees, departments

WHERE hr.employees.department\_id =

departments.department\_id

GROUP BY department\_name)

SELECT department\_name, dept\_total

FROM summary

WHERE dept\_total > (

SELECT SUM(dept\_total) \* 1/8

FROM summary)

ORDER BY dept\_total DESC;

**Introduction to Oracle9*i*: SQL A-62**



<a name="br63"></a> 

**Practice 19 Solutions**

1\. Look at the following output. Is this output the result of a hierarchical query? Explain why or why

not.

a.

**Exhibit 1: This is not a hierarchical query; the report simply has a descending sort**

**on** SALARY**.**

**Exhibit 2: This is not a hierarchical query; there are two tables involved.**

**Exhibit 3: Yes, this is most definitely a hierarchical query as it displays the tree**

**structure representing the management reporting line from the** hr.EMPLOYEES **table.**

2\. Produce a report showing an organization chart for Mourgos’s department. Print last names, salaries,

and department IDs.

SELECT last\_name, salary, department\_id

FROM hr.employees

START WITH last\_name = 'Mourgos'

CONNECT BY PRIOR employee\_id = manager\_id;

3\. Create a report that shows the hierarchy of the managers for the employee Lorentz. Display his

immediate manager first.

SELECT last\_name

FROM hr.employees

WHERE last\_name != 'Lorentz'

START WITH last\_name = 'Lorentz'

CONNECT BY PRIOR manager\_id = employee\_id;

4\. Create an indented report showing the management hierarchy starting from the employee whose

LAST\_NAME is Kochhar. Print the employee’s last name, manager ID, and department ID. Give alias

names to the columns as shown in the sample output.

COLUMN name FORMAT A20

SELECT LPAD(last\_name, LENGTH(last\_name)+(LEVEL\*2)-2,'\_')

name,manager\_id mgr, department\_id deptno

FROM hr.employees

START WITH last\_name = 'Kochhar'

CONNECT BY PRIOR employee\_id = manager\_id

/

COLUMN name CLEAR

**Introduction to Oracle9*i*: SQL A-63**



<a name="br64"></a> 

**Practice 19 Solutions (continued)**

If you have time, complete the following exercises:

5\. Produce a company organization chart that shows the management hierarchy. Start with the person at

the top level, exclude all people with a job ID of IT\_PROG, and exclude De Haan and those

hr.employees who report to De Hann.

SELECT last\_name,employee\_id, manager\_id

FROM   hr.employees

WHERE  job\_id != 'IT\_PROG' 

START WITH manager\_id IS NULL

CONNECT BY PRIOR employee\_id = manager\_id

AND last\_name != 'De Haan';

**Introduction to Oracle9*i*: SQL A-64**



<a name="br65"></a> 

**Practice 20 Solutions**

1\. Run the cre\_sal\_history.sql script in the Labs folder to create the SAL\_HISTORY table.

@ \Labs\cre\_sal\_history.sql

2\. Display the structure of the SAL\_HISTORY table.

DESC sal\_history

3\. Run the cre\_mgr\_history.sql script in the Labs folder to create the MGR\_HISTORY table.

@ \Labs\cre\_mgr\_history.sql

4\. Display the structure of the MGR\_HISTORY table.

DESC mgr\_history

5\. Run the cre\_special\_sal.sql script in the Labs folder to create the SPECIAL\_SAL table.

@ \Labs\cre\_special\_sal.sql

6\. Display the structure of the SPECIAL\_SAL table.

DESC special\_sal 

7\. a. Write a query to do the following:

–

Retrieve the details of the employee ID, hire date, salary, and manager ID of those hr.employees

whose employee ID is less than 125 from the hr.EMPLOYEES table.

–

If the salary is more than $20,000, insert the details of employee ID and salary into the

SPECIAL\_SAL table.

–

–

Insert the details of the employee ID, hire date, and salary into the SAL\_HISTORY table.

Insert the details of the employee ID, manager ID, and SYSDATE into the MGR\_HISTORY

table.

INSERT ALL

WHEN SAL > 20000 THEN

INTO  special\_empsal VALUES (EMPID, SAL)

ELSE

INTO sal\_history VALUES(EMPID,HIREDATE,SAL)

INTO mgr\_history VALUES(EMPID,MGR,SAL)

SELECT employee\_id EMPID, hire\_date HIREDATE,

salary SAL, manager\_id MGR

FROM hr.employees 

WHERE employee\_id < 125;

**Introduction to Oracle9*i*: SQL A-65**



<a name="br66"></a> 

**Practice 20 Solutions (continued)**

b. Display the records from the SPECIAL\_SAL table.

SELECT \* FROM  special\_sal;

c. Display the records from the SAL\_HISTORY table.

SELECT \* FROM  sal\_history;

d. Display the records from the MGR\_HISTORY table.

SELECT \* FROM mgr\_history;

8\. a. Run the cre\_sales\_source\_data.sql script in the Labs folder to create the

SALES\_SOURCE\_DATA table.

@ \Labs\cre\_sales\_source\_data.sql

b. Run the ins\_sales\_source\_data.sql script in the Labs folder to insert records into the

SALES\_SOURCE\_DATA table.

@ \Labs\ins\_sales\_source\_data.sql

c. Display the structure of the SALES\_SOURCE\_DATA table.

DESC sales\_source\_data

d. Display the records from the SALES\_SOURCE\_DATA table.

SELECT \* FROM SALES\_SOURCE\_DATA;

e. Run the cre\_sales\_info.sql script in the Labs folder to create the SALES\_INFO table.

@ \Labs\cre\_sales\_info.sql

f. Display the structure of the SALES\_INFO table.

DESC sales\_info

g. Write a query to do the following:

–

Retrieve the details of the employee ID, week ID, sales on Monday, sales on Tuesday, sales

on Wednesday, sales on Thursday, and sales on Friday from the SALES\_SOURCE\_DATA

table.

–

Build a transformation such that each record retrieved from the SALES\_SOURCE\_DATA

table is converted into multiple records for the SALES\_INFO table.

**Hint**: Use a pivoting INSERT statement.

**Introduction to Oracle9*i*: SQL A-66**



<a name="br67"></a> 

**Practice 20 Solutions (continued)**

INSERT ALL

INTO sales\_info VALUES (employee\_id, week\_id, sales\_MON)

INTO sales\_info VALUES (employee\_id, week\_id, sales\_TUE)

INTO sales\_info VALUES (employee\_id, week\_id, sales\_WED)

INTO sales\_info VALUES (employee\_id, week\_id, sales\_THUR)

INTO sales\_info VALUES (employee\_id, week\_id, sales\_FRI)

SELECT EMPLOYEE\_ID, week\_id, sales\_MON, sales\_TUE,

sales\_WED, sales\_THUR,sales\_FRI  FROM sales\_source\_data;

h. Display the records from the SALES\_INFO table.

SELECT \* FROM sales\_info; 

9\. a. Create the DEPT\_NAMED\_INDEX table based on the following table instance chart. Name the

index for the PRIMARY KEY column as DEPT\_PK\_IDX.

**COLUMN Name**

**Deptno**

**Dname**

Primary Key

Data type

Length

Yes

Number

4

VARCHAR2

30

CREATE TABLE DEPT\_NAMED\_INDEX 

(deptno NUMBER(4)

PRIMARY KEY USING INDEX

(CREATE INDEX dept\_pk\_idx ON

DEPT\_NAMED\_INDEX(deptno)),

dname VARCHAR2(30));

b. Query the USER\_INDEXES table to display the INDEX\_NAME for the

DEPT\_NAMED\_INDEX table.

SELECT INDEX\_NAME, TABLE\_NAME

FROM USER\_INDEXES

WHERE TABLE\_NAME = 'DEPT\_NAMED\_INDEX';

**Introduction to Oracle9*i*: SQL A-67**



<a name="br68"></a> 

**Practice D Solutions**

1\. Write a script to describe and select the data from your tables. Use CHR(10) in the select list with

the concatenation operator ( || ) to generate a line feed in your report Save the output of the script

into my\_file1.sql. To save the file, select the SAVE option for the output, and execute the code.

Remember to save the file with a .sql extension. To execute the my\_file1.sql, browse to

locate the script, load the script, and execute the script.

SET PAGESIZE 0

SELECT 'DESC ' || table\_name || CHR(10) ||

'SELECT \* FROM ' || table\_name || ';'

FROM

/

user\_tables

SET PAGESIZE 24

SET LINESIZE 100

2\. Use SQL to generate SQL statements that revoke user privileges. Use the data dictionary views

USER\_TAB\_PRIVS\_MADE and USER\_COL\_PRIVS\_MADE.

a. Execute the script \Labs\privs.sql to grant privileges to the user SYSTEM*.*

b. Query the data dictionary views to check the privileges. In the sample output shown, note that

the data in the GRANTOR column can vary depending on who the GRANTOR is. Also the last

column that has been truncated is the GRANTABLE column.

COLUMN     grantee

FORMAT  A10

COLUMN     table\_name   FORMAT  A10

COLUMN     column\_name  FORMAT  A10

COLUMN     grantor

FORMAT  A10

COLUMN     privilege    FORMAT  A10

SELECT   \* 

FROM       user\_tab\_privs\_made

WHERE    grantee = 'SYSTEM';

SELECT   \*

FROM      user\_col\_privs\_made

WHERE    grantee = 'SYSTEM';

**Introduction to Oracle9*i*: SQL A-68**



<a name="br69"></a> 

**Practice D Solutions (continued)**

c. Produce a script to revoke the privileges. Save the output of the script into my\_file2.sql. To

save the file, select the SAVE option for the output, and execute the code. Remember to save the

file with a .sql extension. To execute the my\_file2.sql, browse to locate the script, load the

script, and execute the script.

SET VERIFY OFF

SET PAGESIZE 0

SELECT    'REVOKE ' || privilege || ' ON ' ||

table\_name || '  FROM system;'

FROM

user\_tab\_privs\_made

WHERE grantee = 'SYSTEM'

/

SELECT

DISTINCT

'REVOKE ' || privilege || ' ON ' ||

table\_name || '  FROM system;'

FROM

user\_col\_privs\_made

WHERE grantee = 'SYSTEM'

/

SET VERIFY ON

SET PAGESIZE 24

**Introduction to Oracle9*i*: SQL A-69**



<a name="br70"></a> 

**Introduction to Oracle9*i*: SQL A-70**


