## 학습 키워드

- HTTP(Hypertext Transfer Protocol)
- HTTP와 HTTPS의 차이(TLS)
- 클라이언트-서버 모델
- stateless와 stateful
- HTTP Cookie와 HTTP Session
- HTTP 메시지 구조
  - HTTP 요청(Reuqest)와 응답(Response)
    - multipart/form-data
  - HTTP 요청 메서드(HTTP request methods)
    - 멱등성
  - HTTP 응답 상태 코드(HTTP response status code)
    - 리다이렉션

## HTTP(Hypertext Transfer Protocol)

- 웹에서 데이터를 어떤 형태로 요청(Request)하고 보낼지(Response)를 결정하는 프로토콜
  - 프로토콜 : 규약
  - 사용 초기에 HTML을 전송하는 프로토콜로 사용이 되었지만, 현재는 대부분의 데이터 형태를 전송가능 ex) Image, 음성, Json, Xml 등
- 텍스트 기반
- OSI 7계층과 TCP/IP를 기준으로 애플리케이션 레이어에 속함
  - 에플리케이션 레이어 : 다루는 데이터의 형식과 절차에 관련된 프로토콜이 속하는 레이어
- 기본으로 80번 포트를 사용.
- 비연결(Connectionless)
  - 클라이언트가 요청을 보내고, 서버가 요청에 맞는 응답을 보내면 연결이 끊김. 매 요청마다 다시 연결을 맺으며 KeepAlive와 같은 속성을 사용하여 매번 연결을 맺어 느려지는 것을 보완할 수 있음.
- 무상태(Stateless)
  - 연결을 끊는 순간 클라이언트와 서버는 서로의 상태정보를 유지하지 않는다. 즉, 다시 연결되면 기존에 연결된 적 있는 클라이언트인지 서버는 모르며 클라이언트의 상태를 보관하기 위해 쿠키,세션, JWT토큰 등을 사용하여 클라이언트를 식별함.

## HTTP와 HTTPS의 차이(TLS)

- HTTP는 텍스트를 주고 받기 때문에 요청/응답 과정에서 데이터가 노출 될 수 있기에 이러한 이슈를 해결하기 위해 사용 된 것이 HTTPS

* HTTP를 암호화하여 전송하면 HTTPS
* SSL(TLS) 프로토콜을 사용해 클라이언트와 서버가 요청/응답을 할때 텍스트를 공개키 암호화 방식으로 암호화한다.
* 기본으로 443번 포트를 사용.

![https://heidyhe.github.io/https/](/week1//image/HTTP_HTTPS_Layers.png)

## 클라이언트-서버 모델

- 2 tier architecture 혹은 클라이언트-서버 모델/아키텍처라고 부름.
- 클라이언트는 요청을 보내고, 서버는 요청에 따른 결과를 응답하는 구조.
- 리소스를 사용하는 곳은 클라이언트
- 리소스를 서브 해주는 곳은 서버
- 클라이언트-서버 간의 프로세스
  1. 클라이언트가 서버에 요청을 보내고 응답을 대기.
  2. 서버가 요청에 대한 결과를 만들어 응답.
  3. 응답 결과를 받아 클라이언트가 원하는 요청이 동작.

* 클라이언트-서버 모델에 DB가 추가되면 3 tier architecture라고 하며 이 경우엔 서버는 DB에 저장되어 있는 리소스를 전달해주는 역할만 하게됨.

## statelss와 stateful

서버가 클라이언트의 상태를 유지 하는 것을 stateful이라 하고, 유지 하지 않는 것을 stateless라고 한다. statless의 경우 캐싱,로드 밸런싱, 스케일 아웃이 장점이지만 서버는 매 요청마다 다시 클라이언트의 상태 정보를 받아야하고 클라이언트의 요청마다 자신의 부가정보를 줘야하기 때문에 때문에 로그인이 필요한 서비스의 경우 stateless의 방식으로는 한계가 있어 이에 쿠키와 세션을 사용해 서버가 클라이언트의 상태유지를 하는데 최소한의 stateful을 사용한다. 단순히 생각해보면 stateful 방식이 유리할것 같지만, 서버A가 클라이언트의 상태를 가지고 있을 경우 서버B는 해당 클라이언트의 상태를 가지고 있지 않아 사고가 발생해 failover 시스템이 작동 될 경우 서버가 클라이언트의 상태를 잃게 되는 문제가 생기고, 수 만명의 클라이언트 요청이 올 경우 서버가 클라이언트의 상태를 보존할 경우 요청을 처리 할 수 있는 서버의 capacity는 제한적일수 밖에 없다는 한계가 있다.
위에 이유로 이에 상태 데이터를 따로 캐시서버(Redis)에 저장하는 이유이기도 하다.

## HTTP Cookie와 HTTP Session

### HTTP Cookie

- 클라이언트의 상태를 브라우저에 저장하여 동일한 서버에 재요청시 전송하는 데이터
- 쿠키만 사용하여 사용자를 식별할 경우 쿠키의 값을 변경하면 다른 사용자의 정보나 권한을 얻게 될 수도 있어 세션을 사용함.

### HTTP Session

- 서버에 사용자를 식별할 데이터를 보관함.
- 서버에 세션Id를 Map의 형태로 key로 저장하고 사용자를 식별할수 있는 데이터를 value에 넣어 요청이 왔을시 쿠키에 있는 sessionId와 동일한 key의 값을 찾은뒤 value를 반환한다

* 세션이 생성되면 쿠키도 생성되어 반환된다.

## HTTP 메세지 구조

![https://developer.mozilla.org/ko/docs/Web/HTTP/Messages](/week1//image/HTTP_Messages.png)

- start line
  - start line에 요청이나 응답의 상태를 표시
  - 응답에서는 status line이라고 부름
- HTTP headers
  - HTTP 전송에 필요한 부가정보를 포함
- empty line
  - 헤더와 바디를 구분하는 공백
- body
  - 요청과 응답에 필요한 데이터를 작성하여 보내는 곳
  * HTML, 이미지,영상, JSON 등 byte로 표현 가능한 데이터를 전송가능

### HTTP 요청(Reuqest)와 응답(Response)

```
요청
Request-line
Format: [method]SP[request-target]SP[HTTP-version]CRLF
Ex    : GET /search?q=hello&hl=ko HTTP/1.1
```

- method: HTTP 메소드를 지정
- request-target: 요청 대상(쿼리스트링)
- HTTP-version

```
응답
Status-line
Format: [HTTP-version]SP[status-code]SP[reason-phrase]
Ex    : HTTP/1.1 200 OK
```

- HTTP-version
- HTTP 상태코드
- reason-phrase: 상태코드에 관한 간단한 설명

multipart/form-data

- Content-Type을 multiplart/form-data로 설정시 파일 업로드와 같이 바이너리 데이터를 전송시 사용한다.

### HTTP 요청 메서드(HTTP request methods)

GET

- 리소스 조회에 사용
- 쿼리스트링을 사용하여 필요한 리소스를 요청
- 보통 메세지 바디는 사용하지 않음

POST

- 메세지 바디를 통해 서버로 필요한 데이터를 요청
- 리소스 등록에 사용

PUT

- 리소스가 없을 경우 생성하고 있을 경우 수정함

PATCH

- 리소스 부분 변경
- 없을시 별도로 생성 안함

DELETE

- 리소스를 삭제
