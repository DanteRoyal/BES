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

### Stateful(상태 유지)

- 클라이언트-서버 간 서버가 클라이언트의 상태를 보존하는 것

## HTTP Cookie와 HTTP Session

## HTTP 메세지 구조
