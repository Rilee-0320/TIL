# β­ SQL μ¬ν

## π‘ νΈλμ­μ(Transactions)

- μ¬λ¬ μΏΌλ¦¬λ¬Έμ λ¬Άμ΄μ νλμ μμμ²λΌ μ²λ¦¬νλ λ°©λ²
- μͺΌκ°μ§ μ μλ μλ¬΄ μ²λ¦¬μ λ¨μλ‘ μ μ²΄κ° μνλκ±°λ μ ν μνλμ§ μμμΌ ν¨(All or Nothing)

```sql
START TRANSACTION;
state_ments;
...
[ROLLBACK|COMMIT];
```

- START TRANSACTION
  - νΈλμ­μ κ΅¬λ¬Έμ μμμ μλ¦Ό
- COMMIT
  - λͺ¨λ  μμμ΄ μ μμ μΌλ‘ μλ£λλ©΄ νκΊΌλ²μ DBμ λ°μ
- ROLLBACK
  - λΆλΆμ μΌλ‘ μμμ΄ μ€ν¨νλ©΄ νΈλμ­μμμ μ§νν λͺ¨λ  μ°μ°μ μ·¨μνκ³  νΈλμ­μ μ€ν μ μΌλ‘ λλλ¦Ό
- κΈ°λ³Έμ μΌλ‘ MySQLμ μλμΌλ‘ λ³κ²½ μ¬ν­μ COMMIT ν¨
- λ³κ²½ μ¬ν­μ μλμΌλ‘ COMMIT νμ§ μμΌλ €λ©΄ 'SET autocommit = 0;' λ€μκ³Ό κ°μ΄ μ€μ 

## π‘ νΈλ¦¬κ±°(Triggers)

- νΉμ  μ΄λ²€νΈμ λν μλ΅μΌλ‘ μλμΌλ‘ μ€νλλ κ²

```sql
CREATE TRIGGER trigger_name
  {BEFORE|AFTER} {INSERT|UPDATE|DELETE}
  ON table_name FOR EACH ROW
  trigger_body;
```

- CREATE TRIGGER ν€μλ λ€μμ μμ±νλ €λ νΈλ¦¬κ±°μ μ΄λ¦μ μ§μ 
- κ° λ μ½λμ μ΄λ μμ μ νΈλ¦¬μ»€κ° μ€νλ μ§ μ§μ (μ½μ, μμ , μ­μ  μ /ν)
- ON ν€μλ λ€μ νΈλ¦¬κ±°κ° μν νμ΄λΈμ μ΄λ¦μ μ§μ 
- νΈλ¦¬κ±°κ° νμ±νλ  λ μ€νν  μ½λλ₯Ό trigger_bodyμ μ§μ 
  - μ¬λ¬ λͺλ Ήλ¬Έμ μ€ννλ €λ©΄ BEGIN END ν€μλλ‘ λ¬Άμ΄μ μ¬μ©

```sql
-- νΈλ¦¬κ±°λ₯Ό μ¬μ©ν΄ κΈ°μ‘΄ κ²μκΈμ΄ μμ λλ©΄ κ²μκΈμ μμ  μΌμ νλ κ°μ μ΅μ  μΌμλ‘ μλ°μ΄νΈνκΈ°
DELIMITER //
CREATE TRIGGER beforeArticleUpdate
  BEFORE UPDATE
  ON articles FOR EACH ROW
BEGIN
  SET NEW.updateAt = CURRENT_TIME();
END//
DELIMITER ;
```

- DELIMITER
  - SQLμ κ΅¬λ¬Έ λ¬Έμ(;)λ₯Ό λ³κ²½
  - BEGIN-END κ΅¬λ¬Έ μ¬μ΄μ μ¬λ¬ SQL λ¬Έμ΄ μμ±λκΈ° λλ¬Έμ νλμ νΈλ¦¬κ±°λ‘μ¨ μλλ  μ μλλ‘ μ¬μ©
- BEGIN-END
  - νλ μ΄μμ κ΅¬λ¬Έ λͺ©λ‘μ νν
  - BEGINκ³Ό END ν€μλλ‘ λλ¬μΈλ λ€μ€ κ΅¬λ¬Έμ κ΅¬μ±νκ² λ¨
- NEW

  - νΈλ¦¬κ±°μμ νΉμ  μμ  μ /νμ κ°μ μ κ·Όν  μ μλλ‘ μ κ³΅νλ ν€μλ
  - OLDμ NEW 2κ° μ κ³΅
  - μν©λ³ μ¬μ© μ¬λΆ  
    | |OLD|NEW|
    |---|-----|----|
    |INSERT|NO|YES|
    |UPDATE|YES|YES|
    |DELETE|YES|NO|

- Triggers κ΄λ ¨ μΆκ° λͺλ Ήλ¬Έ
  - νΈλ¦¬κ±° λͺ©λ‘ νμΈ
  ```sql
  SHOW TRIGGERS;
  ```
  - νΈλ¦¬κ±° μ­μ 
  ```sql
  DROP TRIGGER trigger_name;
  ```
- Triggers μμ± μ μλ¬ ν΄κ²°

  - νΈλμ­μ μμ± ν μ μμ μΌλ‘ μ’λ£λμ§ μμ μλ¬κ° λ°μν  μ ν΄κ²°λ²
  - Error Code:2013. Lost connection to MySQL server during query
  - Error Code: 2015. Lock wait timeout exceeded; try restarting transaction

  ```sql
  -- μ€ν μ€μΈ νλ‘μΈμ€ λͺ©λ‘ νμΈ
  SELECT * FROM information_schema.INNODB_TRX;

  -- νΉμ  νλ‘μΈμ€μ trx_mysql_thread_id μ­μ 
  KILL [trx_mysql_thread_id1];
  ```

## π‘ μ κ·ν(Normalization)

- RDB μ€κ³ λ¨κ³μμ μ€λ³΅μ μ΅μννμ¬ λ°μ΄ν°λ₯Ό κ΅¬μ‘°ννλ κ³Όμ 
- μ 1 μ κ·ν
  - λ°μ΄ν°λ² μ΄μ€μ κ° νλμλ νλμ κ°λ§ μ μ₯ν΄μΌ ν¨
  - μ μ¬νκ² μ λ³΄λ₯Ό μ μ₯νλ λ κ°μ νλκ° μμ΄μλ μ λ¨
    - λ°λ³΅λλ λΆλΆμ μ°Ύμ νμ΄λΈμ λΆν νκ³  κΈ°λ³Έ ν€κ° λ  νλλ₯Ό μμ±
- μ 2 μ κ·ν
  - ν€κ°μ μ΄μ©ν΄ λ°μ΄ν°λ₯Ό νΉμ§μ§μ μ μλ κ²(ν¨μ μ’μμ±)μ μ°Ύμ νμ΄λΈμ λΆν 
- μ 3 μ κ·ν
  - κΈ°λ³Έ ν€ μ΄μΈμ λΆλΆμμ μ€λ³΅μ΄ μλμ§λ₯Ό μ‘°μ¬νμ¬ νμ΄λΈμ λΆν 
- μ κ·νμ λͺ©μ 
  - λ°μ΄ν°λ₯Ό μ½κ² κ΄λ¦¬νκΈ° μν΄
    - νλμ λ°μ΄ν°λ₯Ό λ¬΄μ‘°κ±΄ ν κ³³μμλ§ μμΉνλλ‘ ν¨
    - νμ΄λΈ κ°μ κ΄κ³λ ν€λ₯Ό ν΅ν΄ νμ±
    - λ°μ΄ν°λ₯Ό λ³κ²½νλλΌλ ν κ³³λ§ λ³κ²½νλ κ΅¬μ‘° νλ¦½

## π‘ λ°μ΄ν° λͺ¨λΈλ§(Data Modeling)

- λ°μ΄ν°λ² μ΄μ€ μμ€νμ μκ°μ μΌλ‘ νννλ νλ‘μΈμ€
- λ°μ΄ν° μ ν, λ°μ΄ν° κ°μ κ΄κ³ λ° λΆμ λ±μ ν΅ν΄ λΉμ¦λμ€ μκ΅¬μ¬ν­μ λ§λ€μ΄ λΌ μ μλλ‘ λμ
- ER(Entity-Relationship) Diagram
  - λ€μ΄μ΄κ·Έλ¨μ μ¬μ©νμ¬ λ°μ΄ν°λ² μ΄μ€μ Entity κ° κ΄κ³λ₯Ό λνλ΄λ λ°©λ²
  - Entity(β‘)λ μ¬κ°νμΌλ‘ λνλ΄λ©° νμ΄λΈμ λνλ
  - Attribute(β)λ μνμΌλ‘ λνλ΄λ©° νλλ₯Ό λνλ
  - Relation(β)μ λ§λ¦λͺ¨λ‘ λνλ΄λ©° κ΄κ³(PK, FK)λ₯Ό λνλ
  - Relationship νν λ°©λ²
    - Cardinality(κΈ°μ)
      - 1:1, 1:N, M:N λ± νλμ κ°μ²΄μ λͺ κ°μ κ°μ²΄κ° λμλλμ§ νννλ κ²
    - Optionality(μ ν κ°λ₯μ±)
      - κ΄κ³κ° νμμΈμ§ μλμ§ νννλ κ²
  - λ°μ΄ν° λͺ¨λΈλ§μ μ€μμ±
    - λ°μ΄ν°λ² μ΄μ€ μννΈμ¨μ΄ κ°λ° μ€λ₯ κ°μ
    - λ°μ΄ν°λ² μ΄μ€ μ€κ³ λ° μμ± μλμ ν¨μ¨μ± μ΄μ§
    - μ‘°μ§ μ μ²΄μμ λ°μ΄ν° λ¬Έμν λ° μμ€ν μ€κ³μ μΌκ΄μ± μ‘°μ±
    - λ°μ΄ν° μμ§λμ΄μ λΉμ¦λμ€ν κ°μ μ»€λ?€λμΌμ΄μ μ΄μ§
