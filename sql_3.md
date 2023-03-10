# β­ SQL Managing Tables

## π‘ CREATE TABLE statement 
- νμ΄λΈ μμ±
```sql
CREATE TABLE table_name (
  column_1 data_type,
  column_2 data_type,
  ...,
  constraints
);
```
- κ° νλμ μ μ©ν  λ°μ΄ν° νμ(data type) μμ±
- νμ΄λΈ λ° νλμ λν μ μ½ μ‘°κ±΄(constraints) μμ±
  > μ μ½ μ‘°κ±΄(Constraint): `λ°μ΄ν° λ¬΄κ²°μ±`μ μ§ν€κΈ° μν΄ λ°μ΄ν°λ₯Ό μλ ₯λ°μ λ μ€ννλ κ²μ¬ κ·μΉ  
  
  > λ°μ΄ν° λ¬΄κ²°μ±: λ°μ΄ν°μ μ νμ±κ³Ό μΌκ΄μ±μ λ³΄μ¦
  - PRIMARY KEY: ν΄λΉ νλλ₯Ό κΈ°λ³Έ ν€λ‘ μ§μ 
  - NOT NULL: ν΄λΉ νλμ NULL κ°μ μ μ₯νμ§ λͺ»νλλ‘ μ§μ 
    - λ°λμ NOT NULL μ μ½μ μ¬μ©ν  νμλ μμΌλ λ°μ΄ν°λ² μ΄μ€λ₯Ό μ¬μ©νλ νλ‘κ·Έλ¨μ λ°λΌ NULLμ μ μ₯ν  νμκ° μλ κ²½μ°κ° λ§μΌλ―λ‘ λλλ‘ NOT NULLλ‘ μ μ
    - 'κ°μ΄ μλ€'λΌλ ννμ νμ΄λΈμ κΈ°λ‘νλ κ²μ 0μ΄λ λΉ λ¬Έμμ΄ λ±μ μ¬μ©νλ κ²μΌλ‘ λμ²΄νλ κ²μ κΆμ₯

- AUTO_INCREMENT attribute
  - νμ΄λΈμ κΈ°λ³Έ ν€μ λν λ²νΈ μλ μμ±
  - κΈ°λ³Έ ν€ νλμ μ¬μ©
    - κ³ μ ν μ«μλ₯Ό λΆμ¬
  - μμ κ°μ 1μ΄λ©° λ°μ΄ν° μλ ₯ μ κ°μ μλ΅νλ©΄ μλμΌλ‘ 1μ© μ¦κ°
  - μ΄λ―Έ μ¬μ©ν κ°μ μ¬μ¬μ©νμ§ μμ
  - κΈ°λ³Έμ μΌλ‘ NOT NULL μ μ½ μ‘°κ±΄μ ν¬ν¨

```sql
CREATE TABLE examples (
  examId INT AUTO_INCREMENT,
  lastName VARCHAR(50) NOT NULL,
  firstName VARCHAR(50) NOT NULL,
  PRIMARY KEY (examId)
);
```

## π‘ DROP TABLE statement
- νμ΄λΈ μ­μ 
```sql
DROP TABLE table_name;
```
- DROP TABLE statement μ΄ν μ­μ ν  νμ΄λΈ μ΄λ¦ μμ±

## π‘ ALTER TABLE statement
- νμ΄λΈ νλ μ‘°μ(μμ±, μμ , μ­μ )
- ALTER TABLE **ADD** : νλ μΆκ°
  ```sql
  ALTER TABLE
    table_name
  ADD
    new_column_name column_definition;
  ```
  - ADD μ΄ν μΆκ°νκ³ μ νλ μ νλ μ΄λ¦κ³Ό λ°μ΄ν° νμ λ° μ μ½ μ‘°κ±΄ μμ±
  ```sql
  -- examples νμ΄λΈμ country νλ μΆκ°(λ¨, country νλλ κ°λ³ κΈΈμ΄ λ¬Έμμ΄ μ΅λ 100μμ΄λ©° NULL  κ°μ νμ©νμ§ μμ)

  ALTER TABLE
    examples
  ADD
    country VARCHAR(100) NOT NULL;
  ```
- ALTER TABLE **MODIFY** : νλ μμ± λ³κ²½
  ```sql
  ALTER TABLE
    table_name
  MODIFY
    column_name column_definition;
  ```
  - MODIFY ν€μλ μ΄ν λ³κ²½νκ³ μ νλ νλ μ΄λ¦, λ°μ΄ν° νμ λ° μ μ½ μ‘°κ±΄ μμ±
  ```sql
  -- examples νμ΄λΈμ lastName, firstName νλλ₯Ό κ°λ³ κΈΈμ΄ λ¬Έμμ΄ μ΅λ 10μκΉμ§ κ·Έλ¦¬κ³  NULL κ°μ νμ©νμ§ μλλ‘ λ³κ²½

  ALTER TABLE examples
  MODIFY lastName VARCHAR(10) NOT NULL,
  MODIFY firstName VARCHAR(10) NOT NULL;
  ```

- ALTER TABLE **CHANGE COLUMN** : νλ μ΄λ¦ λ³κ²½
  ```sql
  ALTER TABLE
    table_name
  CHANGE COLUMN
    original_name new_name column_definition;
  ```
  - CHANGE COLUMN ν€μλ μ΄ν κΈ°μ‘΄ νλ μ΄λ¦, λ³κ²½νκ³ μ νλ νλ μ΄λ¦, λ°μ΄ν° νμ λ° μ μ½ μ‘°κ±΄ μμ±
  ```sql
  -- examples νμ΄λΈμ country νλ μ΄λ¦μ stateλ‘ λ³κ²½(λ¨, λ°μ΄ν° νμ λ° μ μ½ μ‘°κ±΄μ κΈ°μ‘΄κ³Ό λμΌ)
  
  ALTER TABLE
    examples
  CHANGE COLUMN
    country state VARCHAR(100) NOT NULL;
  ```

- ALTER TABLE **DROP COLUMN** : νλ μ­μ 
  ```sql
  ALTER TABLE
    table_name
  DROP COLUMN
    column_name;
  ```
  - DROP COLUMN ν€μλ μ΄ν μ­μ νκ³ μ νλ νλ μ΄λ¦ μμ±
  ```sql
  -- examples νμ΄λΈμ stateμ age νλ μ­μ 

  ALTER TABLE
    examplese
  DROP COLUMN
    state,
  DROP COLUMN
    age;
  ```