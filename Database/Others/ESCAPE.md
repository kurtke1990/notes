# ESCAPE
跳脫特殊字元
```sql
-- 找出姓名有 '中_X' 的學生，因為 _ 為 Wildcard，所以需要跳脫
SELECT * FROM student s WHERE s.stu_lastname LIKE '中$_%' ESCAPE '$';

-- 也可以使用 \ 跳脫
SELECT * FROM student s WHERE s.stu_lastname LIKE '中\_%';
```