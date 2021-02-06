# Operators
---

[Arithmetic](Operators.md#Arithmetic)
[Comparison](Operators.md#Comparison)
[Logical](Operators.md#Logical)

---

## Arithmetic

SELECT 數字 (+-\*/) 數字 -> 直接做相對應的計算
SELECT 字串 (+-\*/) 數字 -> 先將字串試著轉數字，若成功
做相對應的計算，若失敗，先將字串轉換成 0 再做相對應的計算
SELECT 數字或字串 (+-\*/) null -> 結果為 null

```sql
-- 15
SELECT 10 + 5;
-- 5
SELECT 10 - 5;
-- 50
SELECT 10 * 5;
-- 2
SELECT 10 / 5;

-- 15
SELECT 10 + '5';
-- 5
SELECT 10 - '5';
-- 50
SELECT 10 * '5';
-- 2
SELECT 10 / '5';

-- 以下均為 null
SELECT null + 5;
SELECT null - 5;
SELECT null * 5;
SELECT null / 5;
SELECT null + '10';
SELECT null - '10';
SELECT null * '10';
SELECT null / '10';
```

## Comparison

通常搭配 WHERE clause 一起使用

```sql
-- = 等於
SELECT * FROM product
WHERE price = 18;

-- > 大於
SELECT * FROM product
WHERE price > 30;

-- < 小於
SELECT * FROM product
WHERE price < 30;

-- >= 大於等於
SELECT * FROM product
WHERE price >= 30;

-- <= 小於等於
SELECT * FROM product
WHERE price <= 30;

-- <> 不等於
SELECT * FROM product
WHERE price <> 30;
```

## Logical

當有兩個以上條件進行判斷時使用

```sql
-- AND
-- 查詢在英國倫敦的 customer
SELECT * FROM customer
WHERE city = "London" AND contry = "UK";

-- BETWEEN AND
-- 查詢價格在 50 與 60 間的 product
SELECT * FROM product
WHERE price BETWEEN 50 AND 60;

-- IN
-- 查詢在倫敦或巴黎的 customer
SELECT * FROM customer
WHERE city IN ('Paris','London');

-- LIKE
-- 模糊搜尋 name 開頭為 s 的 customer
SELECT * FROM customer
WHERE name LIKE 's%';

-- NOT
-- 模糊搜尋 name 不是開頭為 s 的 customer
SELECT * FROM customer
WHERE name NOT LIKE 's%';

-- OR
-- 查詢在英國或在倫敦的 customer
SELECT * FROM customer
WHERE city = "London" OR contry = "UK";
```