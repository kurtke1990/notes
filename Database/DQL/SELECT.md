# SELECT
---

[基本語法](#基本語法)
[一般查詢](#一般查詢)
[Alias](#Alias)
[條件查詢](#條件查詢)

---

## 基本語法
```sql
SELECT A FROM B;
```

A 可以是
- constant (e.g. 100, 'A', '2021/01/01')
	- 字串類型與日期類型需要前後加上 ''
	- 數字不用
- function (e.g. CONCAT('A', 'B'))
- 一個或多個欄位名稱 (e.g. id, name)
- \*
- expression (e.g. 3/4, 3+2)

B 可以是
- table name

## 一般查詢
```sql
-- constant
SELECT 'john';
SELECT 100;

-- function
-- 計算出有幾個學生
SELECT COUNT(s.stu_id) FROM student s;

-- 一個或多個欄位名稱
SELECT stu_name, stu_id, stu_age FROM student;

-- *
-- 查詢所有學生的資料
SELECT * FROM student;

-- expression
SELECT 3*4;
```

## Alias
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

## 條件查詢
根據判斷條件進行查詢
```sql
-- 查詢大於 20 歲的學生
SELECT * FROM student s WHERE s.stu_age > 20;

-- 查詢姓氏不是王的學生
SELECT * FROM student s WHERE s.stu_firstname <> '王';

-- 查詢薪水在 45000 - 70000 萬之間的員工
-- 方式一: 使用 operator
SELECT * FROM employee WHERE salary >= 45000 AND salary <= 70000;

-- 方式二: 使用 between and (包含45000, 70000)
SELECT * FROM employee WHERE salary BETWEEN 45000 AND 70000;

-- 查詢在部門編號 001 或 018 的而且薪水高於 45000 的員工
SELECT * FROM employee WHERE dept_id = '001' OR dept_id = '018' AND salary > 45000;

-- 查詢在部門編號 001 或 018 的而且薪水高於 45000 的員工
SELECT * FROM employee WHERE dept_id = '001' OR dept_id = '018' AND salary > 45000;
```