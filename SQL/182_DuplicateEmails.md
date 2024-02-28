# 182. Duplicate Emails
* **Topic** --> **_SQL Schema_**

---
## Task Introduction 
Write a solution to report all the duplicate emails. Note that it's guaranteed that the email field is not **NULL**. Return the result table in any order. The result format is in the following example.
```sh
Table Name: Person Table 
+------------+---------+
| id         |  email  |
+------------+---------+
| 1          | a@b.com |
| 2          | c@d.com |
| 3          | a@b.com |
+------------+---------+
```
```sh
Output: 
+---------+
| Email   |
+---------+
| a@b.com |
+---------+
```
**Explanation**: a@b.com is repeated two times.

---
## Solution
```SQL
SELECT email
FROM Person 
GROUP BY email 
HAVING COUNT(DISTINCT id) > 1 
```
