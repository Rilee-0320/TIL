# โญ SQL Nested Queries

## ๐ก Subquery
- ๋จ์ผ ์ฟผ๋ฆฌ๋ฌธ์ ์ฌ๋ฌ ํ์ด๋ธ์ ๋ฐ์ดํฐ๋ฅผ ๊ฒฐํฉํ๋ ๋ฐฉ๋ฒ
- ์กฐ๊ฑด์ ๋ฐ๋ผ ํ๋ ์ด์์ ํ์ด๋ธ์์ ๋ฐ์ดํฐ๋ฅผ ๊ฒ์ํ๋ ๋ฐ ์ฌ์ฉ
- SELECT, FROM, WHERE, HAVING ์  ๋ฑ์์ ๋ค์ํ ๋งฅ๋ฝ์์ ์ฌ์ฉ
```sql
-- ์๋น๋ฅผ ํ ๊ณ ๊ฐ ์ค ํ ๋ฒ์ ์ง๋ถํ ๊ธ์ก์ด ๊ฐ์ฅ ๋์ ๊ณ ๊ฐ์ customerNumber, amount, contactFirstName์ ์กฐํ(๊ณ ๊ฐ ํ์ด๋ธ์ customers, ์ง๋ถ ํ์ด๋ธ์ payments๋ฅผ ํ์ฉ)

SELECT customerNumber, amount, contactFirstName
FROM (
	SELECT *
    FROM payments
    INNER JOIN customers USING (customerNumber)
) AS mySub
WHERE amount = (
	SELECT MAX(amount)
    FROM payments
);
```
- EXISTS operator
  - ์ฟผ๋ฆฌ๋ฌธ์์ ๋ฐํ๋ ๋ ์ฝ๋์ ์กด์ฌ ์ฌ๋ถ๋ฅผ ํ์ธ
  ```sql
  SELECT
    select_list
  FROM
    table
  WHERE
    [NOT] EXISTS (subquery);
  ```
  - subquery๊ฐ ํ๋ ์ด์์ ํ์ ๋ฐํํ๋ฉด EXISTS ์ฐ์ฐ์๋ true๋ฅผ ๋ฐํํ๊ณ  ๊ทธ๋ ์ง ์์ผ๋ฉด false๋ฅผ ๋ฐํ
  - ์ฃผ๋ก WHERE ์ ์์ subquery์ ๋ฐํ ๊ฐ ์กด์ฌ ์ฌ๋ถ๋ฅผ ํ์ธํ๋ ๋ฐ ์ฌ์ฉ
  ```sql
  -- Paris์ ์๋ ์ฌ๋ฌด์ค์์ ์ผํ๋ ๋ชจ๋  ์ง์์ ๋ฒํธ, ์ด๋ฆ, ์ฑ์ ์กฐํ(์ง์ ํ์ด๋ธ์ employees, ์ฌ๋ฌด์ค ํ์ด๋ธ์ offices์ด๋ฉฐ ๋ ํ์ด๋ธ์ officeCode ํ๋๋ฅผ ๊ธฐ์ค์ผ๋ก ๋น๊ต)

  SELECT
    employeeNumber, firstName, lastName
  FROM
    employees
  WHERE
    EXISTS (
      SELECT *
      FROM offices
      WHERE city = 'Paris' AND offices.officeCode = employees.officeCode
    );
  ```

  ## ๐ก CASE statement
  - SQL ๋ฌธ์์ ์กฐ๊ฑด๋ฌธ์ ๊ตฌ์ฑ
  ```sql
  CASE case_value
    WHEN when_value1 THEN statements
    WHEN when_value2 THEN statements
    ...
    [ELSE else-statements]
  END CASE;
  ```
  - case_value๊ฐ when_value์ ๋์ผํ ๊ฒ์ ์ฐพ์ ๋๊น์ง ์์ฐจ์ ์ผ๋ก ๋น๊ต
  - when_value์ ๋์ผํ case_value๋ฅผ ์ฐพ์ผ๋ฉด ํด๋น THEN ์ ์ ์ฝ๋๋ฅผ ์คํ
  - ๋์ผํ ๊ฐ์ ์ฐพ์ง ๋ชปํ๋ฉด ELSE ์ ์ ์ฝ๋๋ฅผ ์คํ
    - ELSE ์ ์ด ์์ ๋ ๋์ผํ ๊ฐ์ ์ฐพ์ง ๋ชปํ๋ฉด ์ค๋ฅ ๋ฐ์
  ```sql
  -- orders ํ์ด๋ธ์ status์ ๋ฐ๋ผ ์์ธ ์ ๋ณด๋ฅผ ๋งค๊ฒจ ์กฐํ('In Process'๋ '์ฃผ๋ฌธ์ค', 'Shipped'๋ '๋ฐ์ฃผ์๋ฃ', 'Cancelled'๋ '์ฃผ๋ฌธ์ทจ์', ๊ทธ ์ธ๋ '๊ธฐํ์ฌ์ '๋ก ์ง์ )

  SELECT orderNumber, status,
    CASE
      WHEN status = 'In Process' THEN '์ฃผ๋ฌธ์ค'
      WHEN status = 'Shipped' THEN '๋ฐ์ฃผ์๋ฃ'
      WHEN status = 'Cancelled' THEN '์ฃผ๋ฌธ์ทจ์'
      ELSE '๊ธฐํ์ฌ์ '
    END AS details
  FROM orders;
  ```