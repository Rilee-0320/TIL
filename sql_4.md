# β­ SQL Modifying Data

## π‘ INSERT statement
- νμ΄λΈ λ μ½λ μ½μ
```sql
INSERT INTO table_name (c1, c2, ...)
VALUES (v1, v2, ...);
```
- INSERT INTO μ  λ€μμ νμ΄λΈ μ΄λ¦κ³Ό κ΄νΈ μμ νλ λͺ©λ‘μ μμ±
- VALUES ν€μλ λ€μ κ΄νΈ μμ ν΄λΉ νλμ μ½μν  κ° λͺ©λ‘μ μμ±
```sql
-- articles νμ΄λΈμ κ° νλμ μ ν©ν λ°μ΄ν° μλ ₯(λ¨, createdAt νλμλ νμ¬ μμ±νλ λ μ§κ° μλμΌλ‘ μλ ₯, λλ¨Έμ§ νλ μμ¨)

INSERT INTO
  articles (title, content, createdAt)
VALUES
  ('mytitle', 'mycontent', CURDATE());
```
- `CURDATE()`: MySQLμ΄ μ κ³΅νλ Date Functions μ€ νλλ‘ νμ¬ λ μ§λ₯Ό λ°νν¨

## π‘ UPDATE statement
- νμ΄λΈ λ μ½λ μμ 
```sql
UPDATE table_name
SET column_name = expression,
[WHERE
  condition];
```
- SET μ  λ€μμ μμ ν  νλμ μ κ°μ μ§μ 
- WHERE μ μμ μμ ν  λ μ½λλ₯Ό μ§μ νλ μ‘°κ±΄ μμ±
  - WHERE μ μ μμ±νμ§ μμΌλ©΄ λͺ¨λ  λ μ½λλ₯Ό μμ ν¨
```sql
-- articles νμ΄λΈ λͺ¨λ  λ μ½λμ content νλ κ° μ€ λ¬Έμμ΄ 'content'λ₯Ό 'TEST'λ‘ λ³κ²½

UPDATE
  articles
SET
  content = REPLACE(content, 'content', 'TEST');
```
- `REPLACE(νλλͺ, 'κΈ°μ‘΄ λ¬Έμμ΄', 'λ³κ²½ λ¬Έμμ΄')` : MySQLμ΄ μ κ³΅νλ String Functions μ€ νλλ‘ μ§μ λ λ¬Έμμ΄μ λ³κ²½ν¨

## π‘ DELETE statement
- νμ΄λΈ λ μ½λ μ­μ 
```sql
DELETE FROM table_name
[WHERE
  condition];
```
- DELETE FROM μ  λ€μμ νμ΄λΈ μ΄λ¦ μμ±
- WHERE μ μμ μ­μ ν  λ μ½λλ₯Ό μ§μ νλ μ‘°κ±΄ μμ±
  - WHERE μ μ μμ±νμ§ μμΌλ©΄ λͺ¨λ  λ μ½λλ₯Ό μ­μ ν¨
```sql
-- articles νμ΄λΈμ 1λ² λ μ½λ μ­μ 

DELETE FROM
  articles
WHERE
  id = 1;
```

```sql
-- articles νμ΄λΈμμ κ°μ₯ μ΅κ·Όμ μμ±λ λ μ½λ 2κ°λ₯Ό μ­μ 
DELETE FROM
  articles
ORDER BY
  createdAt DESC
LIMIT 2;
```