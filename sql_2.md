# โญ SQL Single Table Queries

## ๐ก Querying data
- SELECT syntax
  - ํ์ด๋ธ์์ ๋ฐ์ดํฐ๋ฅผ ์กฐํ
  - SELECT ํค์๋ ๋ค์์ ๋ฐ์ดํฐ๋ฅผ ์ ํํ๋ ค๋ ํ๋๋ฅผ ํ๋ ์ด์ ์ง์ 
  - FROM ํค์๋ ๋ค์์ ๋ฐ์ดํฐ๋ฅผ ์ ํํ๋ ค๋ ํ์ด๋ธ์ ์ด๋ฆ์ ์ง์ 
  ```sql
  SELECT
    select_list
  FROM
    table_name;
  ```
  - \*(Asterisk): ๋ชจ๋  ๋ฐ์ดํฐ ์กฐํ ๊ฐ๋ฅ
  - AS keyword: ํ๋์ ์๋ก์ด ๋ณ์นญ์ ์ง์ 
  - ๊ธฐ๋ณธ์ ์ธ ์ฌ์น์ฐ์ฐ ์ฌ์ฉ ๊ฐ๋ฅ

## ๐ก Sorting data
- ORDER BY clause
  - ์กฐํ ๊ฒฐ๊ณผ์ ๋ ์ฝ๋๋ฅผ ์ ๋ ฌ
  - FROM clause ๋ค์ ์์น
  - ํ๋ ์ด์์ ํ๋๋ฅผ ๊ธฐ์ค์ผ๋ก ๊ฒฐ๊ณผ๋ฅผ ์ค๋ฆ์ฐจ์, ๋ด๋ฆผ์ฐจ์์ผ๋ก ์ ๋ ฌํ  ์ ์์
    - ASC: ์ค๋ฆ์ฐจ์(๊ธฐ๋ณธ๊ฐ)
    - DESC: ๋ด๋ฆผ์ฐจ์
  ```sql
  SELECT
    select_list
  FROM
    table_name
  ORDER BY
    column1 [ASC|DESC],
    column2 [ASC|DESC],
    ...;
  ```

## ๐ก Filtering data
- DISTINCT clause
  - ์กฐํ ๊ฒฐ๊ณผ์์ ์ค๋ณต๋ ๋ ์ฝ๋๋ฅผ ์ ๊ฑฐ
  ```sql
  SELECT DISTINCT
    select_list
  FROM
    table_name;
  ```
  - SELECT ํค์๋ ๋ฐ๋ก ๋ค์ ์์ฑํด์ผ ํจ
  - SELECT DISTINCT ํค์๋ ๋ค์์ ๊ณ ์ ํ ๊ฐ์ ์ ํํ๋ ค๋ ํ๋ ์ด์์ ํ๋๋ฅผ ์ง์ 

- WHERE clause
  - ์กฐํ ์ ํน์  ๊ฒ์ ์กฐ๊ฑด์ ์ง์ 
  ```sql
  SELECT
    select_list
  FROM
    table_name
  WHERE
    search_condition;
  ```

  - FROM clause ๋ค์ ์์น
  - search_condition์ ๋น๊ต์ฐ์ฐ์(=, >=, <=, IS, LIKE, IN, BETWEEN ๋ฑ) ๋ฐ ๋ผ๋ฆฌ์ฐ์ฐ์(AND(&&), OR(||), NOT(!) ๋ฑ)๋ฅผ ์ฌ์ฉํ๋ ๊ตฌ๋ฌธ์ด ์ฌ์ฉ๋จ
  - ํน์  ๋ฒ์๋ฅผ ์ง์ ํ  ๋๋ BETWEEN ์ฐ์ฐ์ ์ฌ์ฉ ๊ฐ๋ฅ

    ```sql
    -- ํ์ด๋ธ employees์์ officeCode ํ๋ ๊ฐ์ด 1์์ 4 ์ฌ์๊ฐ์ธ ๋ฐ์ดํฐ์ lastName, firstName, officeCode ์กฐํ(1๊ณผ 4 ํฌํจ)

    SELECT
      lastName, firstName, officeCode
    FROM
      employees
    WHERE
      officeCode >= 1
      AND officeCode <= 4;


    SELECT
      lastName, firstName, officeCode
    FROM
      employees
    WHERE
      officeCode BETWEEN 1 AND 4;

    -- ๋ ์ฟผ๋ฆฌ๋ฌธ ๋ชจ๋ ๋์ผํ ๋ฐ์ดํฐ๋ฅผ ์กฐํํจ
    ```

  - IN operator

    - ๊ฐ์ด ํน์  ๋ชฉ๋ก ์์ ์๋์ง ํ์ธ

    ```sql
    -- ํ์ด๋ธ employees์์ officeCode ํ๋ ๊ฐ์ด 1 ๋๋ 3 ๋๋ 4 ๊ฐ์ธ ๋ฐ์ดํฐ์ lastName, firstName, officeCode ์กฐํ

    SELECT
      lastName, firstName, officeCode
    FROM
      employees
    WHERE
      officeCode = 1
      OR officeCode = 3
      OR officeCode = 4;


    SELECT
      lastName, firstName, officeCode
    FROM
      employees
    WHERE
      officeCode IN (1, 3, 4);

    -- ๋ ์ฟผ๋ฆฌ๋ฌธ ๋ชจ๋ ๋์ผํ ๋ฐ์ดํฐ๋ฅผ ์กฐํํจ
    ```

  - LIKE operator

    - ์์ผ๋์นด๋๋ก ๊ฐ์ด ํน์  ํจํด๊ณผ ์ผ์นํ๋์ง ํ์ธ
    - Wildcard characters
      - '%' : **0๊ฐ ์ด์์ ๋ฌธ์์ด**๊ณผ ์ผ์นํ๋์ง ํ์ธ
      - '\_' : **๋จ์ผ ๋ฌธ์**์ ์ผ์นํ๋์ง ํ์ธ

    ```sql
    -- ํ์ด๋ธ employees์์ lastName ํ๋ ๊ฐ์ด 'son'์ผ๋ก ๋๋๋ ๋ฐ์ดํฐ์ lastName, firstName ์กฐํ

    SELECT
      lastName, firstName
    FROM
      employees
    WHERE
      lastName LIKE '%son';
    ```

    ```sql
    -- ํ์ด๋ธ employees์์ firstName ํ๋ ๊ฐ์ด 4์๋ฆฌ์ด๋ฉด์ 'y'๋ก ๋๋๋ ๋ฐ์ดํฐ์ lastName, firstName ์กฐํ

    SELECT
      lastName, firstName
    FROM
      employees
    WHERE
      firstName LIKE '___y';
    ```

- LIMIT clause

  - ์กฐํํ๋ ๋ ์ฝ๋ ์๋ฅผ ์ ํ

  ```sql
  SELECT
    select_list
  FROM
    table_name
  LIMIT [offset,] row_count;
  ```

  - LIMIT clause๋ ํ๋ ๋๋ ๋ ๊ฐ์ ์ธ์๋ฅผ ์ฌ์ฉ(0 ๋๋ ์์ ์ ์)
  - row_count๋ ์กฐํํ  ์ต๋ ๋ ์ฝ๋ ์๋ฅผ ์ง์ 
  - offset ์ง์  ์ ์ดํ๋ถํฐ ์กฐํ

  ```sql
  -- ํ์ด๋ธ customers์์ contactFirstName, creditLimit ํ๋ ๋ฐ์ดํฐ๋ฅผ creditLimit ๊ธฐ์ค ๋ด๋ฆผ์ฐจ์์ผ๋ก 4๋ฒ์งธ๋ถํฐ 7๋ฒ์งธ ๋ฐ์ดํฐ๋ง ์กฐํ

  SELECT
    contactFirstName, creditLimit
  FROM
    customers
  ORDER BY
    creditLimit DESC
  LIMIT 3, 4;
  ```

## ๐ก Grouping data
- GROUP BY clause
  - ์ง๊ณ ํจ์๋ก ๋ ์ฝ๋๋ฅผ ๊ทธ๋ฃนํํ์ฌ ์์ฝ๋ณธ ์์ฑ
  - ์ง๊ณ ํจ์(Aggregation Functions): ๊ฐ์ ๋ํ ๊ณ์ฐ์ ์ํํ๊ณ  ๋จ์ผํ ๊ฐ์ ๋ฐํํ๋ ํจ์
    - SUM, AVG, MAX, MIN, COUNT
  ```sql
  SELECT
    c1, c2, ..., cn, aggregate_function(ci)
  FROM
    table_name
  GROUP BY
    c1, c2, ..., cn;
  ```
  - FROM ๋ฐ WHERE ์  ๋ค์ ๋ฐฐ์น
  - GROUP BY ์  ๋ค์ ๊ทธ๋ฃนํํ  ํ๋ ๋ชฉ๋ก์ ์์ฑ
- HAVING clause
  - ์ง๊ณ ํญ๋ชฉ์ ๋ํ ์ธ๋ถ ์กฐ๊ฑด์ ์ง์ 
  - ์ฃผ๋ก GROUP BY์ ํจ๊ป ์ฌ์ฉ๋๋ฉฐ GROUP BY๊ฐ ์๋ค๋ฉด WHERE์ฒ๋ผ ๋์
  ```sql
  -- ํ์ด๋ธ customers์์ country ํ๋๋ฅผ ๊ทธ๋ฃนํํ์ฌ ๊ฐ ๊ทธ๋ฃน์ ๋ํ creditLimit์ ํ๊ท ๊ฐ์ด 80,000์ ์ด๊ณผํ๋ ๋ฐ์ดํฐ๋ง ์กฐํ

  SELECT
    country,
    AVG(CreditLimit)
  FROM
    customers
  GROUP BY
    country
  HAVING
    AVG(CreditLimit) > 80000;
  ```
