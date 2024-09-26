# Join
SQL에서 조인은 두 개 이상의 테이블을 결합하여 데이터를 조회할 때 사용하는 중요한 연산이다. 조인은 테이블 간의 관계를 설정하고 조건에 맞는 데이터를 결합하여 결과를 반환함

<hr>
<br><br>

## 조인의 종류
- 내부 조인 (INNER JOIN)
- 외부 조인 (OUTER JOIN)
- 교차 조인 (CROSS JOIN)
- 자체 조인 (SELF JOIN)
- 자연 조인 (NATURAL JOIN)

<br>

### 내부 조인 (INNER JOIN)
내부 조인은 두 테이블 간에 공통된 값을 가진 레코드만 결합하여 결과를 반환한다.(조건에 맞지 않는 레코드는 결과에서 제외됨)
```sql
SELECT A.name, B.department
FROM Employees A
INNER JOIN Departments B
ON A.department_id = B.department_id;
```
이 쿼리에서는 Employees테이블과 Departments테이블에서 department_id가 일치하는 레코드만 결합한다.

<br><br>

### 외부 조인 (OUTER JOIN)
외부 조인은 두 테이블의 조인 조건에 맞지 않는 레코드도 포함하여 결과를 반환한다. 외부 조인의 종류는 left, right, full 세 가지 종류가 있다.

#### 1. LEFT OUTER JOIN
왼쪽 테이블의 모든 레코드를 반환하고 만약 오른쪽 테이블에는 일치하는 값이 없으면 NULL을 반환한다.
```sql
SELECT A.name, B.department
FROM Employees A
LEFT OUTER JOIN Departments B
ON A.department_id = B.department_id;
```

#### 2. RIGHT OUTER JOIN
LEFT OUTER JOIN의 반대로 오른쪽 테이블의 모든 레코드를 반환하고, 왼쪽 테이블에 일치하는 값이 없으면 NULL을 반환
```sql
SELECT A.name, B.department
FROM Employees A
RIGHT OUTER JOIN Departments B
ON A.department_id = B.department_id;
```

#### 3. FULL OUTER JOIN
양쪽 테이블의 모든 레코드를 반환. 조인 조건에 맞지 않는 레코드에 대해선 NULL을 반환
```sql
SELECT A.name, B.department
FROM Employees A
FULL OUTER JOIN Departments B
ON A.department_id = B.department_id;
```

<br><br>

### 교차 조인 (CROSS JOIN)
교차 조인은 두 테이블 간에 모든 가능한 조합을 반환한다. 즉, 첫 번째 테이블의 각 레코드와 두 번째 테이블의 모든 레코드가 결합된다. 결과적으로 모든 레코드를 곱한 결과를 반환함
```sql
SELECT A.name, B.department
FROM Employees A
FULL OUTER JOIN Departments B
ON A.department_id = B.department_id;
```

<br><br>

### 자체 조인 (SELF JOIN)
자체 조인은 같은 테이블을 두 번 사용하여 조인을 수행하는 방법이다. 테이블 내의 데이터를 서로 비교하거나 연관시킬 때 사용한다. 보통 ALIAS(별칭)을 사용하여 테이블을 구분함
```sql
SELECT A.employee_id, A.name, B.name AS manager_name
FROM Employees A
INNER JOIN Employees B
ON A.manager_id = B.employee_id;
```

<br><br>

### 자연 조인 (NATURAL JOIN)
자연 조인은 두 테이블 간에 동일한 이름을 가진 컬럼을 자동으로 비교하여 조인을 수행한다.
```sql
SELECT *
FROM Employees
NATURAL JOIN Departments;
```
