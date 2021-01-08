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
[Functions](#Functions)
- [IFNULL](#IFNULL)
- [CONCAT](#CONCAT)
- [LENGTH](#LENGTH)
- [CHAR_LENGTH](#CHAR_LENGTH)

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