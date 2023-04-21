## 학습 키워드

- API(Application Programming Interface)
- 정보은닉(Information Hiding)과 캡슐화(Encapsulation)
  - 그리고 이 둘의 차이(많이들 혼용하니까 잘 알아두세요)
- Architecture와 Architecture Style의 차이
- REST(7가지 제약 조건 위주로 정리)
  - 교재에 나온 `필딩 제약 조건`을 좀 더 풀어서 정리해보세요.

## API(Application Programming Interface)

- 서로 다른 프로그램이 구조화 되고 표준화된 방식으로 통신 할수 있도록 하는 규칙 혹은 수단
- 카카오 로그인 연동을 하면 카카오의 로그인 API가 어떤식으로 작동하는지 몰라도 API문서를 토대로 사용 할수 있다

* 프론트 개발자들은 서버 개발자들의 API문서를 토대로 개발을 할수 있다

## 정보은닉(Information Hiding)과 캡슐화(Encapsulation)

- 정보은닉은 내부 정보에 대한 엑세스를 제한하는데 중점을 둔다.
  - 멤버를 private으로 선언한다.
- 캡슐화는 같은 모듈(클래스)로 변수와 메서드를 묶는 것이다.

## Architecture와 Architecture Style의 차이

- 아키텍처는 설계 및 구성을 의미한다.
- 아키텍처 스타일은 설계에 대한 제약조건의 집합이다.

## REST

- Representational State Trasfer

* REST는 Uniform connector 인터페이스라는 제약 조건과 네트워크 기반 아키텍처 스타일의 혼합이다.

- REST 아키텍처 스타일의 적용 범위는 네트워크 기반 어플리케이션으로 한정 된다.
- REST API : REST 아키텍처 스타일을 따르는 API

### 제약 조건

1. Starting with the Null Style

아키텍처에 설계 과정은 두 가지 관점이 있고, 첫번째는 아무것도 없는 상태에서 설계를 하고 시스템이 요구사항을 충족할 때까지 요소들을 추가해 아키텍처를 구성하며, 두번째는 어떠한 제약조건 없이 시작하여 점차 제약조건을 추가하는 것이다. 첫번째 관점은 창의성과 무한한 비전을 강조하고, 두번째 관점은 제약과 시스템 맥락에 대한 이해를 강조한다.
Null Style은 어떠한 제약 조건이 없는 상태이며, REST를 설명의 시작점이자, 두번째 관점으로 발전해왔다.

2. Client-Server

사용자 인터페이스에 대한 관심사와 데이터 저장에 대한 관심사를 분리하여 클라이언트의 이식성이 향상되고 서버 구성요소를 단순화하여 확장성이 향산된다.

3. Stateless

서버와 클라이언트의 통신에는 상태가 없어야 하며 모든 요청은 필요한 모든 데이터를 가지고 있어야한다. 가시성,신뢰성, 확장성이 향상되지만 네트워크의 성능저하라는 문제가 생긴다

4. Cache

위의 statless의 제약조건의 단점을 보완하기 위해 Cache 제약 조건이 추가 되었다. 이 제약 조건은 모든 응답이 캐싱 가능한지 아닌지를 알 수 있어야 한다

5. Uniform Interface

REST 아키텍처 스타일의 주요 제약조건이다. 일관된 통신 규칙들을 정의하여 클라이언트와 서버가 상호작용하는 것을 표준화를 목표로하며, 아래의 4가지 제약조건으로 구성된다. URI를 통한 리소스 식별 원칙, 표준 HTTP 메서드 사용, 자체 설명 메시지 및 HATEOAS를 준수함으로써 API는 보다 예측 가능하고 사용하기 쉽고 유연하게 변경할 수 있다.

- Identification of Resources

  RESTful API에서 리소스는 고유한 URI를 사용해 식별한다.

- Manipulation of Resources through Representations

  표준 HTTP 메서드를 활용하여 리소스에대한 CRUD를 수행한다

  - Representation : Data + metadata + meta-metadata HTTP 메세지라고 봐도 무방하다.

- Self-descriptive Messages

  자체를 정의하는 메세지를 사용해야 한다. 각 요청과 응답에는 클라이언트와 서버가 이해하는데 필요한 모든 정보를 가지고 있어야한다. Content-Type이 포함된 HTTP 헤더와 작업 결과를 나타내는 상태코드가 포함된다.

- Hypermedia as the Engine of Application State

  요청에 필요한 URI를 응답에 포함시켜 반환하여 모든 요청에 대한 응답을 동적으로 알려 준다.

6. Layered System

계층화된 아키텍처로 구성이 가능해야 하고, 각 계층은 서로 독립적으로 개발 유지관리 될수 있다. API는 7. Code-On-Demand(Optional)
서버가 응답으로 클라이언트에서 동적으로 실행 할수 있는 프로그램을 전달하면 클라이언트에서 실행 될수 있어야한다. 클라이언트는 이를 통해 동적으로 작동이 가능하지만 RESTful API의 필수 제약조건은 아니다.
