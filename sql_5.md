# โญ SQL Multi Table Queries

## ๐ก Joining tables
- JOIN clause
  - ๋ ์ด์์ ํ์ด๋ธ์์ ๋ฐ์ดํฐ๋ฅผ ๊ฒ์ํ๋ ๋ฐฉ๋ฒ
  - JOIN ์ข๋ฅ
    - INNER JOIN
    - OUTER JOIN
      - LEFT JOIN
      - RIGHT JOIN

  - INNER JOIN clause
    - ๋ ํ์ด๋ธ์์ ๊ฐ์ด ์ผ์นํ๋ ๋ ์ฝ๋์ ๋ํด์๋ง ๊ฒฐ๊ณผ๋ฅผ ๋ฐํ
    ```sql
    SELECT
      select_list
    FROM
      table1
    INNER JOIN table2
      ON table1.fk = table2.pk;
    ```
    - FROM ์  ์ดํ ๋ฉ์ธํ์ด๋ธ ์ง์ (table1)
    - INNER JOIN ์  ์ดํ ๋ฉ์ธํ์ด๋ธ๊ณผ ์กฐ์ธํ  ํ์ด๋ธ์ ์ง์ (table2)
    - ON ํค์๋ ์ดํ ์กฐ์ธ ์กฐ๊ฑด์ ์์ฑ
      - ์กฐ์ธ ์กฐ๊ฑด์ table1๊ณผ table2 ๊ฐ์ ๋ ์ฝ๋๋ฅผ ์ผ์น์ํค๋ ๊ท์น์ ์ง์ 
    ```sql
    -- ํ์ด๋ธ orders์ ํ์ด๋ธ orderdetails๋ฅผ INNER JOIN ํ์ฌ orderNumber ๊ฐ์ด ๊ฐ์ ๋ ์ฝ๋์ orderNumber, status, priceEach ํ๋๋ฅผ ์กฐํ
    
    SELECT
      t1.orderNumber,
      t1.status,
      t2.priceEach
    FROM
      orders AS t1
    INNER JOIN orderdetails AS t2
      ON t1.orderNumber = t2.orderNumber;
    ```

  - LEFT [OUTER] JOIN clause
    - ์ค๋ฅธ์ชฝ ํ์ด๋ธ์ ์ผ์นํ๋ ๋ ์ฝ๋์ ํจ๊ป ์ผ์ชฝ ํ์ด๋ธ์ ๋ชจ๋  ๋ ์ฝ๋ ๋ฐํ
    ```sql
    SELECT
      select_list
    FROM
      table1
    LEFT [OUTER] JOIN table2
      ON table1.fk = table2.pk;
    ```
    - FROM ์  ์ดํ ์ผ์ชฝ ํ์ด๋ธ ์ง์ (table1)
    - LEFT JOIN ์  ์ดํ ์ค๋ฅธ์ชฝ ํ์ด๋ธ ์ง์ (table2)
    - ON ํค์๋ ์ดํ ์กฐ์ธ ์กฐ๊ฑด์ ์์ฑ
      - ์ผ์ชฝ ํ์ด๋ธ์ ๊ฐ ๋ ์ฝ๋๋ฅผ ์ค๋ฅธ์ชฝ ํ์ด๋ธ์ ๋ชจ๋  ๋ ์ฝ๋์ ์ผ์น์ํด
    - ์ผ์ชฝ์ ๋ฌด์กฐ๊ฑด ํ์ํ๊ณ , ๋งค์น๋๋ ๋ ์ฝ๋๊ฐ ์์ผ๋ฉด NULL์ ํ์
    - ์ผ์ชฝ ํ์ด๋ธ ํ ๊ฐ์ ๋ ์ฝ๋์ ์ฌ๋ฌ ๊ฐ์ ์ค๋ฅธ์ชฝ ํ์ด๋ธ ๋ ์ฝ๋๊ฐ ์ผ์นํ  ๊ฒฝ์ฐ ํด๋น ์ผ์ชฝ ๋ ์ฝ๋๋ฅผ ์ฌ๋ฌ ๋ฒ ํ์
    ```sql
    -- customers ๊ธฐ์ค์ผ๋ก customerNumber ํ๋๊ฐ ์ผ์นํ๋ ๋ ์ฝ๋์ ํจ๊ป customers ํ์ด๋ธ์ contactFirstName๊ณผ orders ํ์ด๋ธ์ orderNumber, status ํ๋ ์กฐํ(์ผ์ชฝ ํ์ด๋ธ์ customers, ์ค๋ฅธ์ชฝ ํ์ด๋ธ์ orders, ์ผ์นํ์ง ์๋ ๊ฒฝ์ฐ NULL)

    SELECT
      contactFirstName,
      orderNumber,
      status
    FROM
      customers
    LEFT JOIN orders
      ON orders.customerNumber = customers.customerNumber;
    ```

  - RIGHT [OUTER] JOIN clause
    - ์ผ์ชฝ ํ์ด๋ธ์ ์ผ์นํ๋ ๋ ์ฝ๋์ ํจ๊ป ์ค๋ฅธ์ชฝ ํ์ด๋ธ์ ๋ชจ๋  ๋ ์ฝ๋ ๋ฐํ
    ```sql
    SELECT
      select_list
    FROM
      table1
    RIGHT [OUTER] JOIN table2
      ON table1.fk = table2.pk;
    ```
    - FROM ์  ์ดํ ์ผ์ชฝ ํ์ด๋ธ ์ง์ (table1)
    - RIGHT JOIN ์  ์ดํ ์ค๋ฅธ์ชฝ ํ์ด๋ธ ์ง์ (table2)
    - ON ํค์๋ ์ดํ ์กฐ์ธ ์กฐ๊ฑด์ ์์ฑ
      - ์ค๋ฅธ์ชฝ ํ์ด๋ธ์ ๊ฐ ๋ ์ฝ๋๋ฅผ ์ผ์ชฝ ํ์ด๋ธ์ ๋ชจ๋  ๋ ์ฝ๋์ ์ผ์น์ํด
    - ์ค๋ฅธ์ชฝ์ ๋ฌด์กฐ๊ฑด ํ์ํ๊ณ , ๋งค์น๋๋ ๋ ์ฝ๋๊ฐ ์์ผ๋ฉด NULL์ ํ์
    - ์ค๋ฅธ์ชฝ ํ์ด๋ธ ํ ๊ฐ์ ๋ ์ฝ๋์ ์ฌ๋ฌ ๊ฐ์ ์ผ์ชฝ ํ์ด๋ธ ๋ ์ฝ๋๊ฐ ์ผ์นํ  ๊ฒฝ์ฐ ํด๋น ์ค๋ฅธ์ชฝ ๋ ์ฝ๋๋ฅผ ์ฌ๋ฌ ๋ฒ ํ์
    ```sql
    -- employeeNumber ํ๋์ salesRepEmployeeNumber ํ๋๊ฐ ์ผ์นํ๋ ๋ ์ฝ๋์ ํจ๊ป employeeNumber, firstName, customerNumber, contactFirstName ํ๋ ์กฐํ(์ผ์ชฝ ํ์ด๋ธ์ customers, ์ค๋ฅธ์ชฝ ํ์ด๋ธ์ employees, ์ผ์นํ์ง ์๋ ๊ฒฝ์ฐ NULL)

    SELECT
      employeeNumber,
      firstName,
      customerNumber,
      ContactFirstName
    FROM
      customers
    RIGHT JOIN employees
      ON salesRepEmployeeNumber = employeeNumber;
    ```

  - FULL [OUTER] JOIN clause
    - INNER, LEFT, RIGHT JOIN ์งํฉ์ ๋ชจ๋ ์ถ๋ ฅํ๋ JOIN ๋ฐฉ์
    - ๋ ๊ฐ ์ด์์ ํ์ด๋ธ ๊ฐ ์ถ๋ ฅํ  ์ ์๋ ๋ชจ๋  ๋ฐ์ดํฐ๋ฅผ ํฌํจํ ์งํฉ์ ์ถ๋ ฅ
    - MySQL์์๋ FULL OUTER JOIN์ ์ง์ํ์ง ์์ผ๋ฏ๋ก LEFT JOIN๊ณผ RIGHT JOIN์ UNION ํ์ฌ FULL OUTER JOIN์ ์ฌ์ฉํ  ์ ์์
    ```sql
    SELECT * FROM tableA
    LEFT JOIN tableB ON tableA.fk = tableB.id
    UNION
    SELECT * FROM tableA
    RIGHT JOIN tableB ON tableB.fk = tableB.id;
    ```