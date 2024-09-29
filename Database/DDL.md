# DDL (데이터 정의어)
DDL(Data Definition Language)은 데이터베이스에서 데이터 구조를 정의하거나 수정할 때 사용하는 SQL 명령어들의 집합이다.

## 주요 명령어
- CREATE
- ALTER
- DROP
- TRUNCASE

<hr>
<br><br>

### 1. CREATE
CREATE는 새로운 데이터베이스 객체를 생성할 떄 사용한다.
```SQL
CREATE TABLE Employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(50),
    salary NUMBER(10, 2)
);
```
Employees라는 테이블을 생성하는 구문이다.

<br>

### 2. ALTER
ALTER는 기존의 데이터베이스 객체를 수정할 때 사용한다. 주로 테이블에 컬럼을 추가하거나 삭제하거나, 데이터 타입을 변경하는 등의 작업에 사용됨

테이블의 컬럼 추가
```SQL
ALTER TABLE Employees
ADD hire_date DATE;
```

<br>

테이블의 컬럼 수정
```SQL
ALTER TABLE Employees
MODIFY salary NUMBER(12, 2);
```

<br>

테이블의 컬럼 삭제
```SQL
ALTER TABLE Employees
DROP COLUMN department;
```

<br>

### 3. DROP
DROP은 데이터베이스 객체를 삭제할 때 사용한다. (삭제된 객체는 복구할 수 없음)
```SQL
DROP TABLE Employees;
```

<br>

### 4. TRUNCATE
TRUNCATE는 테이블의 모든 데이터를 빠르게 삭제하는 명령어 이다. DELETE와 달리 각 행을 삭제하는 것이 아닌 테이블을 초기화하는 방식으로 동작하여 작업속도가 빠르지만 트랜잭션을 ROLLBACK 할 수 없다.
```SQL
TRUNCATE TABLE Employees;
```

<br>

### 5. RENAME
RENAME은 데이터베이스 객체의 이름을 변경할 때 사용
```SQL
RENAME TABLE Employees TO Staff;
```
