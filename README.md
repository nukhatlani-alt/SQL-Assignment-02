SELECT
p.product_name,
b.brand_name
FROM production.products AS p
INNER JOIN production.brands AS b
ON p.brand_id = b.brand_id;

SELECT
s.store_id,
s.store_name
FROM sales.stores AS s
LEFT JOIN sales.staffs AS st
ON s.store_id = st.store_id
WHERE st.staff_id IS NULL;

SELECT
p.product_name,
s.quantity
FROM production.products AS p
INNER JOIN production.stocks AS s
ON p.product_id = s.product_id
WHERE s.quantity < 5
AND s.store_id = 1;

SELECT
manager.staff_id AS manager_id,
manager.first_name AS manager_first_name,
manager.last_name AS manager_last_name,
employee.staff_id AS employee_id,
employee.first_name AS employee_first_name,
employee.last_name AS employee_last_name,
1 AS count_placeholder
FROM sales.staffs AS employee
INNER JOIN sales.staffs AS manager
ON employee.manager_id = manager.staff_id;
