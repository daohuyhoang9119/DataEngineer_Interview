# SQL là gì?

**SQL** (Structured Query Language) là ngôn ngữ truy vấn dữ liệu, được sử dụng trong hầu hết các hệ quản trị cơ sở dữ liệu quan hệ (RDBMS) như Oracle, SQL Server, MySQL, v.v. SQL giúp quản lý, truy vấn và bảo trì dữ liệu hiệu quả.

---

## Mục lục

1. [Cơ sở dữ liệu là gì?](#cơ-sở-dữ-liệu-là-gì)
2. [DBMS là gì?](#dbms-là-gì)
3. [RDBMS là gì?](#rdbms-là-gì)
4. [SQL là gì?](#sql-là-gì)
5. [Sự khác biệt giữa SQL và MySQL?](#sự-khác-biệt-giữa-sql-và-mysql)
6. [Bảng và trường là gì?](#bảng-và-trường-là-gì)
7. [Ràng buộc trong SQL?](#ràng-buộc-trong-sql)
8. [Khoá chính là gì?](#khoá-chính-là-gì)
9. [Ràng buộc UNIQUE là gì?](#ràng-buộc-unique-là-gì)
10. [Khoá ngoại là gì?](#khoá-ngoại-là-gì)
11. [JOIN là gì? Các kiểu JOIN?](#join-là-gì-các-kiểu-join)
12. [Self-Join là gì?](#self-join-là-gì)
13. [Cross-Join là gì?](#cross-join-là-gì)
14. [Đánh chỉ mục là gì?](#đánh-chỉ-mục-là-gì)
15. [Toàn vẹn dữ liệu là gì?](#toàn-vẹn-dữ-liệu-là-gì)
16. [Truy vấn là gì?](#truy-vấn-là-gì)
17. [Truy vấn con là gì?](#truy-vấn-con-là-gì)
18. [Lệnh SELECT là gì?](#lệnh-select-là-gì)
19. [Các mệnh đề phổ biến với SELECT](#các-mệnh-đề-phổ-biến-với-select)
20. [UNION, MINUS, INTERSECT là gì?](#union-minus-intersect-là-gì)
21. [Con trỏ là gì?](#con-trỏ-là-gì)
22. [Thực thể và quan hệ là gì?](#thực-thể-và-quan-hệ-là-gì)
23. [Các kiểu quan hệ trong SQL?](#các-kiểu-quan-hệ-trong-sql)
24. [Alias trong SQL là gì?](#alias-trong-sql-là-gì)
25. [View là gì?](#view-là-gì)
26. [Normalization là gì?](#normalization-là-gì)
27. [Denormalization là gì?](#denormalization-là-gì)
28. [Các dạng chuẩn hoá?](#các-dạng-chuẩn-hoá)
29. [Lệnh TRUNCATE, DELETE, DROP là gì?](#lệnh-truncate-delete-drop-là-gì)
30. [Khác biệt giữa DELETE và TRUNCATE?](#khác-biệt-giữa-delete-và-truncate)
31. [Khác biệt giữa DROP và TRUNCATE?](#khác-biệt-giữa-drop-và-truncate)
32. [Hàm Aggregate và Scalar là gì?](#hàm-aggregate-và-scalar-là-gì)
33. [Hàm người dùng định nghĩa là gì?](#hàm-người-dùng-định-nghĩa-là-gì)
34. [OLTP là gì?](#oltp-là-gì)
35. [Khác biệt giữa OLTP và OLAP?](#khác-biệt-giữa-oltp-và-olap)
36. [Collation là gì?](#collation-là-gì)
37. [Stored Procedure là gì?](#stored-procedure-là-gì)
38. [Stored Procedure đệ quy là gì?](#stored-procedure-đệ-quy-là-gì)
39. [Tạo bảng trống giống bảng khác?](#tạo-bảng-trống-giống-bảng-khác)
40. [Pattern Matching trong SQL?](#pattern-matching-trong-sql)

---

## 1. Cơ sở dữ liệu là gì?

Cơ sở dữ liệu là tập hợp dữ liệu có tổ chức, lưu trữ và truy xuất từ hệ thống máy tính.

## 2. DBMS là gì?

**DBMS** (Database Management System) là phần mềm quản lý, truy xuất, chỉnh sửa và tổ chức cơ sở dữ liệu.

## 3. RDBMS là gì?

**RDBMS** (Relational Database Management System) lưu trữ dữ liệu dưới dạng bảng, xác định mối quan hệ giữa các bảng qua các trường chung.

## 4. SQL là gì?

SQL là ngôn ngữ chuẩn để truy vấn và quản lý dữ liệu trong RDBMS.

## 5. Sự khác biệt giữa SQL và MySQL?

- **SQL**: Ngôn ngữ truy vấn.
- **MySQL**: Hệ quản trị cơ sở dữ liệu sử dụng SQL.

## 6. Bảng và trường là gì?

- **Bảng**: Tập hợp dữ liệu lưu dưới dạng hàng và cột.
- **Trường**: Cột trong bảng.

## 7. Ràng buộc trong SQL?

Các ràng buộc phổ biến:

- `NOT NULL`
- `CHECK`
- `DEFAULT`
- `UNIQUE`
- `INDEX`
- `PRIMARY KEY`
- `FOREIGN KEY`

## 8. Khoá chính là gì?

Khóa chính (`PRIMARY KEY`) định danh duy nhất mỗi hàng trong bảng.

```sql
CREATE TABLE Students (
  ID INT NOT NULL,
  Name VARCHAR(255),
  PRIMARY KEY (ID)
);
```

## 9. Ràng buộc UNIQUE là gì?

Đảm bảo giá trị trong cột là duy nhất.

```sql
CREATE TABLE Students (
  ID INT NOT NULL UNIQUE,
  Name VARCHAR(255)
);
```

## 10. Khoá ngoại là gì?

Khóa ngoại (`FOREIGN KEY`) tham chiếu đến khóa chính ở bảng khác.

```sql
CREATE TABLE Students (
  ID INT NOT NULL,
  Name VARCHAR(255),
  LibraryID INT,
  PRIMARY KEY (ID),
  FOREIGN KEY (LibraryID) REFERENCES Library(LibraryID)
);
```

## 11. JOIN là gì? Các kiểu JOIN?

Kết hợp dữ liệu từ nhiều bảng dựa trên cột liên quan.

- **INNER JOIN**
- **LEFT (OUTER) JOIN**
- **RIGHT (OUTER) JOIN**
- **FULL (OUTER) JOIN**

```sql
SELECT *
FROM Table_A
INNER JOIN Table_B ON Table_A.col = Table_B.col;
```

## 12. Self-Join là gì?

Join một bảng với chính nó.

```sql
SELECT A.emp_id, A.emp_name, B.emp_id, B.emp_name
FROM employee A, employee B
WHERE A.emp_sup = B.emp_id;
```

## 13. Cross-Join là gì?

Tích Descartes của hai bảng.

```sql
SELECT stu.name, sub.subject
FROM students AS stu
CROSS JOIN subjects AS sub;
```

## 14. Đánh chỉ mục là gì?

Tăng tốc truy vấn dữ liệu.

```sql
CREATE INDEX index_name ON table_name (column_1, column_2);
DROP INDEX index_name;
```

## 15. Toàn vẹn dữ liệu là gì?

Đảm bảo tính nhất quán và chính xác của dữ liệu.

## 16. Truy vấn là gì?

Yêu cầu dữ liệu từ một hoặc nhiều bảng.

```sql
SELECT fname, lname FROM myDb.students WHERE student_id = 1;
UPDATE myDB.students SET fname = 'Captain' WHERE student_id = 1;
```

## 17. Truy vấn con là gì?

Truy vấn lồng trong truy vấn khác.

```sql
SELECT name, email
FROM contacts
WHERE roll_no IN (
  SELECT roll_no FROM students WHERE subject = 'Maths'
);
```

## 18. Lệnh SELECT là gì?

Lấy dữ liệu từ bảng.

```sql
SELECT * FROM myDB.students;
```

## 19. Các mệnh đề phổ biến với SELECT

- `WHERE`
- `ORDER BY`
- `GROUP BY`
- `HAVING`

```sql
SELECT COUNT(studentId), country
FROM myDB.students
WHERE country != "INDIA"
GROUP BY country
HAVING COUNT(studentID) > 5;
```

## 20. UNION, MINUS, INTERSECT là gì?

- `UNION`: Kết hợp kết quả hai truy vấn.
- `MINUS`: Loại bỏ kết quả truy vấn thứ hai khỏi thứ nhất.
- `INTERSECT`: Lấy phần giao của hai truy vấn.

```sql
SELECT name FROM Students
UNION
SELECT name FROM Contacts;
```

## 21. Con trỏ là gì?

Cấu trúc điều khiển để duyệt các bản ghi.

```sql
DECLARE db_cursor CURSOR FOR
SELECT name FROM myDB.students WHERE parent_name IN ('Sara', 'Ansh');
OPEN db_cursor;
FETCH NEXT FROM db_cursor INTO @name;
CLOSE db_cursor;
DEALLOCATE db_cursor;
```

## 22. Thực thể và quan hệ là gì?

- **Thực thể**: Đối tượng có thể xác định được.
- **Quan hệ**: Liên kết giữa các thực thể.

## 23. Các kiểu quan hệ trong SQL?

- One-to-One
- One-to-Many
- Many-to-Many
- Self-Referencing

## 24. Alias trong SQL là gì?

Tên tạm cho bảng hoặc cột.

```sql
SELECT A.emp_name AS "Employee"
FROM employee A;
```

## 25. View là gì?

Bảng ảo dựa trên kết quả truy vấn.

## 26. Normalization là gì?

Tổ chức dữ liệu hiệu quả, giảm dư thừa.

## 27. Denormalization là gì?

Ngược lại với chuẩn hóa, thêm dư thừa để tăng hiệu suất.

## 28. Các dạng chuẩn hoá?

- 1NF: Không có thuộc tính lặp.
- 2NF: Không có phụ thuộc bộ phận.
- 3NF: Không có phụ thuộc bắc cầu.

## 29. Lệnh TRUNCATE, DELETE, DROP là gì?

```sql
DELETE FROM Candidates WHERE CandidateId > 1000;
TRUNCATE TABLE Candidates;
DROP TABLE Candidates;
```

## 30. Khác biệt giữa DELETE và TRUNCATE?

- `TRUNCATE`: Xóa tất cả hàng, giải phóng không gian.
- `DELETE`: Xóa hàng theo điều kiện, không giải phóng không gian.

## 31. Khác biệt giữa DROP và TRUNCATE?

- `DROP`: Xóa bảng và mọi liên kết.
- `TRUNCATE`: Xóa dữ liệu, giữ cấu trúc bảng.

## 32. Hàm Aggregate và Scalar là gì?

- **Aggregate**: AVG(), COUNT(), MIN(), MAX(), SUM(), ...
- **Scalar**: LEN(), UCASE(), LCASE(), CONCAT(), NOW(), ...

## 33. Hàm người dùng định nghĩa là gì?

Hàm do người dùng tự định nghĩa, trả về giá trị scalar hoặc bảng.

## 34. OLTP là gì?

Online Transaction Processing, hỗ trợ giao dịch ngắn, nhiều người dùng.

## 35. Khác biệt giữa OLTP và OLAP?

- **OLTP**: Giao dịch ngắn, nhiều người dùng, truy vấn đơn giản.
- **OLAP**: Phân tích dữ liệu, truy vấn phức tạp, dữ liệu tổng hợp.

## 36. Collation là gì?

Tập hợp quy tắc xác định cách dữ liệu được sắp xếp và so sánh.

## 37. Stored Procedure là gì?

Chương trình con lưu trong database.

```sql
DELIMITER $$
CREATE PROCEDURE FetchAllStudents()
BEGIN
  SELECT * FROM myDB.students;
END $$
DELIMITER ;
```

## 38. Stored Procedure đệ quy là gì?

Procedure tự gọi chính nó.

## 39. Tạo bảng trống giống bảng khác?

```sql
SELECT * INTO Students_copy FROM Students WHERE 1 = 2;
```

## 40. Pattern Matching trong SQL?

```sql
SELECT * FROM students WHERE first_name LIKE 'K%';
SELECT * FROM students WHERE first_name NOT LIKE 'K%';
SELECT * FROM students WHERE first_name LIKE '%K%';
SELECT * FROM students WHERE first_name LIKE '__K%';
SELECT * FROM students WHERE first_name LIKE '____';
```

---

> **Ghi chú:**  
> Tài liệu này tổng hợp các câu hỏi phỏng vấn SQL cơ bản đến nâng cao, phù hợp cho ôn tập và phỏng vấn vị trí Data Engineer/Data Analyst.
