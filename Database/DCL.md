# DCL (데이터 제어어)
DCL(Data Control Language)는 사용자의 권한과 접근을 제어하는 SQL 명령어다. 데이터베이스 관리자(DBA)나 권한을 가진 사용자가 데이터베이스 내에서 다른 사용자에게 권한을 부여하거나 회수하는 데 사용됨
주로 데이터의 보완과 접근제어를 관리하는 역할을 함

## 주요 명령어
- GRANT
- REVOKE

<hr>
<br><br>

### 1. GRANT
GRANT는 특정 사용자에게 테이블, 뷰, 시퀀스, 프로시저 등 데이터베이스 객체에 대한 접근 권한을 부여하는 역할을 한다.
```SQL
GRANT 권한1 [, 권한2, ...]
ON 객체
TO 사용자 [WITH GRANT OPTION];
);
```
- 권한 : SELECT, INSERT, UPDATE, DELETE 등 데이터를 조작할 수 있는 권한을 부여할 수 있음
- WITH GRANT OPTION : 이 옵션을 사용하면 권한을 부여받은 사용자가 다른 사용자에게도 권한을 부여할 수 있게 됨

<br>

### 2. REVOKE
REVOKE는 특정 사용자에게 부여된 권한을 회수하는 데 사용한다.

```SQL
REVOKE 권한1 [, 권한2, ...]
ON 객체
FROM 사용자;
```
- 권한 : GRANT와 마찬가지로 회수할 권한을 지정
- WITH GRANT OPTION : GRNAT와 마찬가지로 다른 사용자에게 부여한 권한도 함께 회수


