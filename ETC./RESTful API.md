# 🔥 RESTful API  란?

> RESTful API를 알기 위해선 먼저 REST가 무엇인지 알아야 한다.

<hr>
<br><br>

## 🌼 REST 란 ?
REST(REpresentational State Transfer)의 약어로 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것을 의미한다.
- 하나의 URI는 하나의 고유한 Resources를 대표하도록 설계된다는 개념
- Method를 통해 해당 자원의 <code>CRUD</code>을 적용하는 것을 의미

## 🌼 REST 3요소
- Resources(자원) : 개별 사용자 자원에 대한 고유한 식별자
- HTTP Method : CRUD 작업을 HTTP로 수행, 클라이언트가 자원의 원하는 동작을 메서드로 요청
- Representation(표현) : 클라이언트의 포현 형태로 전달 됨(JSON, XML, HTML...)

## 🌼 HTTP Method
- GET : 사용자의 정보를 가져오는 요청
- POST : 새로운 사용자를 생성하는 요청
- PUT : 사용자의 정보를 업데이트 하는 요청
- DELETE : 사용자의 정보를 삭제하는 요청

## 🌼 REST의 6가지 특성, 제약
- 확장성 : 클라이언트 상태를 저장하지 않아 서버 확장에 용이하다.
- 단순한 인터페이스 : HTTP 메서드를 활용해 일관되고 직관적인 인터페이스 제공
- 클라이언트-서버 분리 : 독립적인 개발이 가능하여 유연성 증대
- 무상태성 : 요청마다 필요한 정보를 포함해 서버 부담을 줄임
- 캐시 가능성 : 자원의 응답을 캐시할 수 있는 성능 최적화

<hr>
<br><br>

# ⭐ 그래서 RESTful API 란?
#### RESTful API란 REST의 원칙을 따르는 API를 말한다. 
#### 자원 -> 메소드 -> 표현 을 통해 다루는 방식으로, 클라이언트와 서버 간의 상호작용을 간결하고 효율적으로 처리할 수 있다. 
