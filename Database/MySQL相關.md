# MySQL相關
---

[啟動MySQL服務](#啟動MySQL服務)
[關閉MySQL服務](#關閉MySQL服務)
[重新啟動MySQL服務](#重新啟動MySQL服務)
[查詢MySQL目前版本](#查詢MySQL目前版本)
[登入](#登入)
[查詢並列出所有database](#查詢並列出所有database)
[進入某個database](#進入某個database)
[查詢並列出所有table](#查詢並列出所有table)
[查詢目前位於哪個database中](#查詢目前位於哪個database中)
[查詢table詳細資訊](#查詢table詳細資訊)
[查詢目前使用的編碼](#查詢目前使用的編碼)
[Functions](#Functions)
- [IFNULL](#IFNULL)
- [CONCAT](#CONCAT)
- [LENGTH](#LENGTH)
- [CHAR_LENGTH](#CHAR_LENGTH)
- [ISNULL](#ISNULL)
- [UPPER](#UPPER)
- [LOWER](#LOWER)
- [SUBSTR](#SUBSTR)
- [INSTR](#INSTR)
- [TRIM](#TRIM)
- [LPAD](#LPAD)
- [RPAD](#RPAD)
- [REPLACE](#REPLACE)
- [ROUND](#ROUND)
- [CEIL](#CEIL)
- [FLOOR](#FLOOR)
- [MOD](#MOD)

---

## 啟動MySQL服務
```sh
# 方式一
sudo service mysql start

# 方式二
sudo /etc/init.d/mysql start

# 方式三
sudo systemctl start mysqld
```

## 關閉MySQL服務
```sh
# 方式一
service mysqld stop

# 方式二
service mysql stop

# 方式三
/etc/init.d/mysqld stop
```

## 重新啟動MySQL服務
```sh
# 方式一
service mysql restart

# 方式二
service mysqld restart

# 方式三
/etc/init.d/mysqld restart
```

## 查詢MySQL目前版本
```sh
# 方式一
mysql -V

# 方式二
mysql --version

# 方式三 (在 mysql client 裡面執行)
select version();
```

## 登入
```sh
# [] 內中的如果是在 localhost 可省略
mysql [-h 位置 -P port號] -u 帳號 -p 
```

## 查詢並列出所有database
```sh
show databases;
```

## 進入某個database
```sh
use test_db;
```

## 查詢並列出所有table
```sh
# 已進入某個 database 可使用
show tables;

# 在 A database 查詢 test_db database 的 table
show tables from test_db;
```

## 查詢目前位於哪個database中
```sh
select database();
```

## 查詢table詳細資訊
```sh
# 查詢 Student table 的詳細資訊
desc Student;
```

## 查詢目前使用的編碼
```sql
SHOW VARIABLES LIKE '%char%';
```

## Functions
### IFNULL
如果第一個參數為 null，則 return 第二個參數
```sql
SELECT IFNULL(name, 'anonymous') FROM user;
```

### CONCAT
因為字串類型的資料無法透過 ＋ 號來串接，需要透過 CONCAT 來串接字串

```sql
SELECT 
	CONCAT(s.stu_firstname, s.stu_lastname) '姓名'
FROM student s;
```

### LENGTH
查詢字串佔幾 bytes
```sql
SELECT LENGTH('測試');
```

### CHAR_LENGTH
查詢字串有幾個字
```sql
SELECT CHAR_LENGTH('測試');
```

### ISNULL
```sql
-- 如果 commission 為 null, 回傳 1, 不為 null 則回傳 0
SELECT ISNULL(commission) FROM employee;
```

### UPPER
```sql
SELECT UPPER('john');
```

### LOWER
```sql
SELECT LOWER('john');
```

### SUBSTR
```sql
-- 從第 3 個字開始切 (起始為 1)
SELECT SUBSTR('john', 3);

-- 從第 2 個字開始往後切 1 位
SELECT SUBSTR('john', 2, 1);
```

### INSTR
找出某字串第一次出現的 index，若無則回傳 0
```sql
SELECT INSTR('qwerttrewq', 'tt');
```

### TRIM
```sql
SELECT TRIM('    JOHN    ');

-- 去掉前後 a 
SELECT TRIM('a' FROM 'ajoana');
```

### LPAD
往左邊補齊特定數量的字
```sql
SELECT LPAD('john', 6, '*');
```

### RPAD
往右邊邊補齊特定數量的字
```sql
SELECT RPAD('john', 6, '*');
```

### REPLACE
```sql
SELECT REPLACE('replacetest', 'test', 'success');
```

### ROUND
四捨五入
```sql
SELECT ROUND(1.523);

-- 取到小數點第二位
SELECT ROUND(1.523, 2);
```

### CEIL
取最大的整數
```sql
SELECT CEIL(1.2);

SELECT CEIL(1.0);
```

### FLOOR
取最小整數
```sql
SELECT FLOOR(9.99); -- 9

SELECT FLOOR(-9.99); -- -10
```

### TRUNCATE
無條件捨去
```sql
SELECT TRUNCATE(1.79999, 0); -- 1

-- 取到小數點第一位
SELECT TRUNCATE(1.79999, 1); -- 1.7
```

### MOD
取餘數
等同於以下公式
MOD(a, b) => a - a / b * b
```sql
SELECT MOD(10, 3);

SELECT MOD(-10, -3) -- -1;
```