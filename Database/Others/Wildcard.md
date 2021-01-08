# Wildcard
% 表示 0 個或 1 個以上的字
_ 表示 1 個字
```sql
-- %的使用
-- 查詢姓名中結尾為 '明' 的員工
SELECT * FROM employee WHERE name LIKE '%明';

-- _的使用
-- 查詢姓名第二個字為 '安' 的員工
SELECT * FROM employee WHERE name LIKE '_安%';
```