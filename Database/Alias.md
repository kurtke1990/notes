# Alias

如果欄位資料資複雜的計算才能得到，可透過 Alias 讓欄位名稱變得易懂

```sql
-- 方式一: 使用 AS
SELECT 3*4 AS 結果;

SELECT 
	s.stu_id AS 學號,
	s.stu_name AS 學生姓名,
	s.stu_age AS 學生年齡
FROM student s;

-- 方式二: 使用空格
SELECT 3*4 結果;

SELECT 
	s.stu_id 學號,
	s.stu_name 學生姓名,
	s.stu_age 學生年齡
FROM student s;

-- 如果 alias 中有特殊符號，alias 需要放在 '' 或 "" 中
SELECT 
	s.stu_id "學生 編號"
FROM student s;
```