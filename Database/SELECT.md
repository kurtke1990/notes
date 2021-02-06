# SELECT
---

- [基本語法](SELECT.md#基本語法)
- [一般查詢](SELECT.md#一般查詢)
- [條件查詢](SELECT.md#條件查詢)

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
- \* (wildcard)
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