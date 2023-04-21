## 학습 키워드

- Collection Pattern

* CQS(CQRS까진 안 가셔도 됩니다. 추후에 다뤄요)

## Collection Pattern

```
REST에서 가장 중요하며 기본적인 규칙
1. URI는 리소스를 표현해야 한다
2. 자원에 대한 행위는 HTTP Method로 표현한다.
```

- RESTful API를 통해 접근하고 조작할수 있는 관련 리소스 그룹
- URI의 끝점에 리소스를 노출시켜 클라이언트는 표준화된 HTTP 메서드와 균일한 인터페이스를 사용하여 컬렉션 내의 리소스에 대해 CRUD작업을 한다.
- /users는 유저에 관련된 리소스 모음이고 /products는 제품 관련된 리소스의 모음

* /users/1 -> user : colloection, 1 : element

![직접 작성](/week2/image/URI.png)

## CQS

- Command Query Seperation
- 객체의 상태를 변경/수정하는 작업(커맨드)과 변경/수정하지 않고 읽어오기만 하는 작업(쿼리)을 분리하여 명확성과 유지관리 등을 개선하는 패턴

* 객체지향 프로그래밍에서 메서드가 작업을 수행하고 값을 반환하지 않는 명령이거나 값을 반환하고 객체의 상태를 수정하지 않는 쿼리여야함.
* 엄격한 규칙이 아니라 가이드라인이다.
