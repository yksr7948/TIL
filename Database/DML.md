# DML(데이터 조작어)
DML(Data Manipulation language)은 데이터베이스 내의 데이터를 조작하는 데 사용되는 SQL명령어들의 집합이다. 데이터의 조회, 삽입, 삭제, 수정 작업에 사용되며, DML 명령어는 주로 테이블의 행을 처리함

## 주요 명령어
- SELECT(조회)
- INSERT(삽입)
- UPDATE(수정)
- DELETE(삭제)

<hr>
<br><br>

### 1. SELECT
테이블에서 데이터를 조회할때 사용함. 특정 컬럼을 선택하거나 조건을 설정하여 원하는 데이터를 필터링 하여 가져올 수 있다. 
```SQL
SELECT name, salary
FROM Employees
WHERE department = 'IT';
```
이 쿼리는 Employees 테이블에서 department가 IT인 직원의 name, salary를 뽑아오는 쿼리이다.

#### 추가 옵션
- DISTINCT : 중복 제거
- ORDER BY : 특정 컬럼 기준으로 정렬
- GROUP BY : 데이터 그룹화
- JOIN : 두 개 이상의 테이블 결합

<br>

### 2. INSERT
INSERT는 테이블에 새로운 행을 삽입할 때 사용한다.

행 삽입
```SQL
INSERT INTO Employees (employee_id, name, department, salary)
VALUES (1, '김태웅', 'IT', 4000);
```

<br>

다중 행 삽입
```SQL
INSERT INTO Employees (employee_id, name, department, salary)
VALUES 
(2, '유재석', 'IT', 7000),
(3, '박명수', 'IT', 6000);
```

<br>

### 3. UPDATE
UPDATE는 기존 데이터의 값을 수정할 때 사용된다. 특정 조건에 맞는 행의 데이터를 수정할 수 있음
```SQL
UPDATE Employees
SET salary = 4500
WHERE employee_id = 1;
```

<br>

### 4. DELETE
DELETE는 테이블에서 데이터를 삭제할 때 사용된다. 특정 조건에 맞는 행만 삭제하거나 조건 없이 테이블의 모든 데이터를 삭제할 수 있음
```SQL
DELETE FROM Employees
WHERE employee_id = 1;
```

<hr>
<br><br>

## DML과 트랜잭션
DML 명령어는 트랜잭션의 일부로 처리될 수 있다. 트랜잭션은 일관성을 있는 상태를 보장하기 위해 여러 DML 작업을 하나의 그룹으로 묶어 처리한다. 

트랜잭션이 성공하면 COMMIT을 작업이 완료되고, 실패하면 ROLLBACK으로 이전 상태로 되돌릴 수 있다.

```SQL
BEGIN;

INSERT INTO Employees (employee_id, name, department, salary)
VALUES (4, '하동훈', 'IT', 4500);

UPDATE Employees
SET salary = 4800
WHERE employee_id = 4;

COMMIT;
```
새로운 직원 정보를 삽입하고 연봉을 업데이트한 후, COMMIT으로 작업을 확정함. 중간에 오류가 발생하면 ROLLBACK으로 모든 변경사항을 취소할 수 있다.
