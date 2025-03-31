# SQL Interview Problems

## Easy Problems

1. **Basic SELECT Query**
   - Problem: Select all employees whose salary is above 50000
   ```sql
   -- Table: employees
   -- Columns: id, name, salary, department
   -- Sample Data:
   -- 1, John Doe, 60000, IT
   -- 2, Jane Smith, 45000, HR
   -- 3, Bob Wilson, 55000, Sales

   -- Required Query:
   SELECT * FROM employees WHERE salary > 50000;

   -- Expected Output:
   -- 1, John Doe, 60000, IT
   -- 3, Bob Wilson, 55000, Sales
   ```

2. **COUNT Function**
   - Problem: Count number of employees in each department
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT department, COUNT(*) as emp_count 
   FROM employees 
   GROUP BY department;

   -- Expected Output:
   -- IT, 5
   -- HR, 3
   -- Sales, 4
   ```

3. **ORDER BY**
   - Problem: List employees ordered by salary in descending order
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT name, salary 
   FROM employees 
   ORDER BY salary DESC;

   -- Expected Output:
   -- Mark Smith, 75000
   -- John Doe, 60000
   -- Bob Wilson, 55000
   ```

4. **DISTINCT**
   - Problem: Find unique departments
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT DISTINCT department 
   FROM employees;

   -- Expected Output:
   -- IT
   -- HR
   -- Sales
   ```

5. **Simple JOIN**
   - Problem: List employees with their department names
   ```sql
   -- Tables: employees, departments
   -- Required Query:
   SELECT e.name, d.dept_name 
   FROM employees e
   JOIN departments d ON e.department_id = d.id;

   -- Expected Output:
   -- John Doe, Information Technology
   -- Jane Smith, Human Resources
   ```

6. **WHERE with Multiple Conditions**
   - Problem: Find employees in IT department with salary > 45000
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT name, salary 
   FROM employees 
   WHERE department = 'IT' AND salary > 45000;

   -- Expected Output:
   -- John Doe, 60000
   -- Mike Johnson, 50000
   ```

7. **LIKE Operator**
   - Problem: Find employees whose names start with 'J'
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT name 
   FROM employees 
   WHERE name LIKE 'J%';

   -- Expected Output:
   -- John Doe
   -- Jane Smith
   -- James Wilson
   ```

8. **MIN and MAX**
   - Problem: Find minimum and maximum salaries per department
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT department, MIN(salary) as min_salary, MAX(salary) as max_salary 
   FROM employees 
   GROUP BY department;

   -- Expected Output:
   -- IT, 45000, 80000
   -- HR, 40000, 65000
   ```

9. **BETWEEN Operator**
   - Problem: Find employees with salaries between 40000 and 60000
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT name, salary 
   FROM employees 
   WHERE salary BETWEEN 40000 AND 60000;

   -- Expected Output:
   -- Jane Smith, 45000
   -- Bob Wilson, 55000
   ```

10. **NULL Values**
    - Problem: Find employees with no manager assigned
    ```sql
    -- Table: employees
    -- Required Query:
    SELECT name 
    FROM employees 
    WHERE manager_id IS NULL;

    -- Expected Output:
    -- John Doe
    -- Mark Smith
    ```

## Medium Problems

1. **Subquery**
   - Problem: Find employees who earn more than average salary
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT name, salary 
   FROM employees 
   WHERE salary > (SELECT AVG(salary) FROM employees);

   -- Expected Output:
   -- John Doe, 60000
   -- Mark Smith, 75000
   ```

2. **Multiple JOINs**
   - Problem: List employees with their department and project names
   ```sql
   -- Tables: employees, departments, projects
   -- Required Query:
   SELECT e.name, d.dept_name, p.project_name
   FROM employees e
   JOIN departments d ON e.department_id = d.id
   JOIN project_assignments pa ON e.id = pa.employee_id
   JOIN projects p ON pa.project_id = p.id;

   -- Expected Output:
   -- John Doe, IT, Project Alpha
   -- Jane Smith, HR, Project Beta
   ```

3. **Window Functions**
   - Problem: Rank employees by salary within each department
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT name, department, salary,
          RANK() OVER (PARTITION BY department ORDER BY salary DESC) as salary_rank
   FROM employees;

   -- Expected Output:
   -- John Doe, IT, 60000, 1
   -- Mike Ross, IT, 55000, 2
   ```

4. **CASE Statement**
   - Problem: Categorize employees by salary range
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT name,
          CASE 
              WHEN salary >= 60000 THEN 'High'
              WHEN salary >= 40000 THEN 'Medium'
              ELSE 'Low'
          END as salary_category
   FROM employees;

   -- Expected Output:
   -- John Doe, High
   -- Jane Smith, Medium
   ```

5. **Common Table Expressions (CTE)**
   - Problem: Find departments with above-average salaries
   ```sql
   -- Table: employees
   -- Required Query:
   WITH avg_salary AS (
       SELECT AVG(salary) as company_avg FROM employees
   )
   SELECT department, AVG(salary) as dept_avg
   FROM employees, avg_salary
   GROUP BY department
   HAVING AVG(salary) > avg_salary.company_avg;

   -- Expected Output:
   -- IT, 58000
   -- Finance, 62000
   ```

6. **Self JOIN**
   - Problem: List employees and their managers
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT e1.name as employee, e2.name as manager
   FROM employees e1
   LEFT JOIN employees e2 ON e1.manager_id = e2.id;

   -- Expected Output:
   -- Jane Smith, John Doe
   -- Mike Ross, John Doe
   ```

7. **GROUP BY with HAVING**
   - Problem: Find departments with more than 3 employees
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT department, COUNT(*) as emp_count
   FROM employees
   GROUP BY department
   HAVING COUNT(*) > 3;

   -- Expected Output:
   -- IT, 5
   -- Sales, 4
   ```

8. **Date Functions**
   - Problem: Calculate employee tenure in years
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT name, 
          DATEDIFF(YEAR, hire_date, GETDATE()) as tenure
   FROM employees;

   -- Expected Output:
   -- John Doe, 5
   -- Jane Smith, 3
   ```

9. **Pivot Tables**
   - Problem: Show department headcount by year
   ```sql
   -- Table: employees
   -- Required Query:
   SELECT *
   FROM (
       SELECT department, YEAR(hire_date) as hire_year
       FROM employees
   ) AS SourceTable
   PIVOT (
       COUNT(department)
       FOR hire_year IN (2020, 2021, 2022)
   ) AS PivotTable;

   -- Expected Output:
   -- IT, 2, 3, 1
   -- HR, 1, 1, 2
   ```

10. **String Functions**
    - Problem: Split full name into first and last name
    ```sql
    -- Table: employees
    -- Required Query:
    SELECT 
        LEFT(name, CHARINDEX(' ', name) - 1) as first_name,
        RIGHT(name, LEN(name) - CHARINDEX(' ', name)) as last_name
    FROM employees;

    -- Expected Output:
    -- John, Doe
    -- Jane, Smith
    ```

## Hard Problems

1. **Recursive CTE**
   - Problem: Find all employees in reporting hierarchy
   ```sql
   -- Table: employees
   -- Required Query:
   WITH RECURSIVE emp_hierarchy AS (
       SELECT id, name, manager_id, 1 as level
       FROM employees
       WHERE manager_id IS NULL
       UNION ALL
       SELECT e.id, e.name, e.manager_id, h.level + 1
       FROM employees e
       JOIN emp_hierarchy h ON e.manager_id = h.id
   )
   SELECT * FROM emp_hierarchy;

   -- Expected Output:
   -- 1, John Doe, NULL, 1
   -- 2, Jane Smith, 1, 2
   -- 3, Mike Ross, 2, 3
   ```

2. **Running Totals**
   - Problem: Calculate running total of sales by date
   ```sql
   -- Table: sales
   -- Required Query:
   SELECT 
       sale_date,
       amount,
       SUM(amount) OVER (ORDER BY sale_date) as running_total
   FROM sales;

   -- Expected Output:
   -- 2024-01-01, 1000, 1000
   -- 2024-01-02, 1500, 2500
   ```

3. **Gap Analysis**
   - Problem: Find gaps in continuous data
   ```sql
   -- Table: sequence_data
   -- Required Query:
   WITH numbers AS (
       SELECT seq_num,
              LEAD(seq_num) OVER (ORDER BY seq_num) as next_num
       FROM sequence_data
   )
   SELECT seq_num + 1 as gap_start, next_num - 1 as gap_end
   FROM numbers
   WHERE next_num - seq_num > 1;

   -- Expected Output:
   -- 5, 7
   -- 10, 12
   ```

4. **Islands Problem**
   - Problem: Group consecutive dates with same status
   ```sql
   -- Table: system_status
   -- Required Query:
   SELECT MIN(date) as start_date,
          MAX(date) as end_date,
          status
   FROM (
       SELECT date, status,
              ROW_NUMBER() OVER (ORDER BY date) -
              ROW_NUMBER() OVER (PARTITION BY status ORDER BY date) as grp
       FROM system_status
   ) t
   GROUP BY status, grp;

   -- Expected Output:
   -- 2024-01-01, 2024-01-03, online
   -- 2024-01-04, 2024-01-05, offline
   ```

5. **Moving Average**
   - Problem: Calculate 3-day moving average of sales
   ```sql
   -- Table: daily_sales
   -- Required Query:
   SELECT 
       sale_date,
       AVG(amount) OVER (
           ORDER BY sale_date
           ROWS BETWEEN 2 PRECEDING AND CURRENT ROW
       ) as moving_avg
   FROM daily_sales;

   -- Expected Output:
   -- 2024-01-01, 1000
   -- 2024-01-02, 1250
   -- 2024-01-03, 1500
   ```

6. **Dynamic Pivot**
   - Problem: Create dynamic pivot table based on categories
   ```sql
   -- Tables: sales, categories
   -- Required Query:
   DECLARE @columns NVARCHAR(MAX);
   DECLARE @sql NVARCHAR(MAX);

   SET @columns = STRING_AGG(QUOTENAME(category), ',')
   FROM (SELECT DISTINCT category FROM categories) t;

   SET @sql = N'
   SELECT *
   FROM (
       SELECT date, category, amount
       FROM sales s
       JOIN categories c ON s.category_id = c.id
   ) t
   PIVOT (
       SUM(amount)
       FOR category IN (' + @columns + ')
   ) p';

   EXEC sp_executesql @sql;

   -- Expected Output:
   -- Date, Electronics, Clothing, Food
   -- 2024-01-01, 1000, 500, 300
   ```

7. **Hierarchical Queries**
   - Problem: Calculate total budget including sub-departments
   ```sql
   -- Table: departments
   -- Required Query:
   WITH RECURSIVE dept_hierarchy AS (
       SELECT id, parent_id, budget
       FROM departments
       WHERE parent_id IS NULL
       UNION ALL
       SELECT d.id, d.parent_id, d.budget
       FROM departments d
       JOIN dept_hierarchy h ON d.parent_id = h.id
   )
   SELECT id,
          SUM(budget) OVER (PARTITION BY id) as total_budget
   FROM dept_hierarchy;

   -- Expected Output:
   -- 1, 150000
   -- 2, 75000
   ```

8. **Temporal Tables**
   - Problem: Track historical changes in employee data
   ```sql
   -- Tables: employees, employee_history
   -- Required Query:
   SELECT e.name,
          eh.salary,
          eh.effective_from,
          eh.effective_to
   FROM employees e
   JOIN employee_history eh ON e.id = eh.employee_id
   WHERE @date BETWEEN eh.effective_from AND eh.effective_to;

   -- Expected Output:
   -- John Doe, 50000, 2024-01-01, 2024-06-30
   -- John Doe, 60000, 2024-07-01, 9999-12-31
   ```

9. **Complex Aggregation**
   - Problem: Calculate percentage of sales by category and region
   ```sql
   -- Tables: sales, categories, regions
   -- Required Query:
   WITH sales_data AS (
       SELECT 
           c.category,
           r.region,
           SUM(s.amount) as total_sales,
           SUM(SUM(s.amount)) OVER () as grand_total
       FROM sales s
       JOIN categories c ON s.category_id = c.id
       JOIN regions r ON s.region_id = r.id
       GROUP BY c.category, r.region
   )
   SELECT 
       category,
       region,
       total_sales,
       (total_sales * 100.0 / grand_total) as percentage
   FROM sales_data;

   -- Expected Output:
   -- Electronics, North, 50000, 25.0
   -- Clothing, North, 30000, 15.0
   ```

10. **Performance Optimization**
    - Problem: Optimize slow-running sales report
    ```sql
    -- Tables: sales, products, customers
    -- Required Query:
    WITH sales_summary AS (
        SELECT 
            p.category,
            c.region,
            SUM(s.amount) as total_sales
        FROM sales s
        JOIN products p ON s.product_id = p.id
        JOIN customers c ON s.customer_id = c.id
        WHERE s.sale_date >= DATEADD(month, -1, GETDATE())
        GROUP BY p.category, c.region
    )
    SELECT *
    FROM sales_summary
    WHERE total_sales > (
        SELECT AVG(total_sales) * 1.5
        FROM sales_summary
    );

    -- Expected Output:
    -- Electronics, North, 75000
    -- Clothing, South, 65000
    ```