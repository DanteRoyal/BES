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

* REST는 Uniform coonector 인터페이스라는 제약 조건과 네트워크 기반 아키텍처 스타일의 혼합이다.

- REST 아키텍처 스타일의 적용 범위는 네트워크 기반 어플리케이션으로 한정 된다.
- REST API : REST 아키텍처 스타일을 따르는 API

### 제약 조건

1. Starting with the Null Style

아키텍처에 설계 과정은 두 가지 관점이 있고, 첫번째는 아무것도 없는 상태에서 설계를 하고 시스템이 요구사항을 충족할 때까지 요소들을 추가해 아키텍처를 구성하며, 두번째는 어떠한 제약조건 없이 시작하여 점차 제약조건을 추가하는 것이다. 첫번째 관점은 창의성과 무한한 비전을 강조하고, 두번째 관점은 제약과 시스템 맥락에 대한 이해를 강조한다.
Null Style은 어떠한 제약 조건이 없는 상태이며, REST를 설명의 시작점이자, 두번째 관점으로 발전해왔다.

2. Client-Server
3. Stateless
4. Cache
5. Uniform Interface
6. Layered System
7. Code-On-Demand
