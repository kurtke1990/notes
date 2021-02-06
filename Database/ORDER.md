# ORDER
- 可以有一個以上的排序欄位、expression、function、alias
- 通常都會放在最後面，但如果有 LIMIT 除外

```sql
-- 查詢員工資料並依員工的薪水由多到少排序
SELECT * FROM employee ORDER BY salary DESC;

-- 查詢員工資料員工的薪水由少到多排序
SELECT * FROM employee ORDER BY salary ASC;
SELECT * FROM employee ORDER BY salary;

-- 查詢部門編號大於等於 90 的員工，根據到職日排序
SELECT * FROM employee
WHERE dept_id >= 90
ORDER BY hire_date ASC;

-- 查詢員工資料並根據年薪高低排序 (1)
SELECT *, salary * 12 * (1 + IFNULL(year_end_bonus_ratio, 0)) 年薪
FROM employee
ORDER BY 年薪 DESC;

-- 查詢員工資料並根據年薪高低排序 (2)
SELECT *, salary * 12 * (1 + IFNULL(year_end_bonus_ratio, 0)) 年薪
FROM employee
ORDER BY salary * 12 * (1 + IFNULL(year_end_bonus_ratio, 0)) DESC;

-- 查詢員工資料並根據薪資升冪排序，員工編號降冪排序
SELECT * FROM employee
DRDER BY salary ASC, emp_id DESC;
```