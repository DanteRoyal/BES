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
- TCP와 UDP를 사용하고, 80번 포트를 사용.
- 비연결(Connectionless)
  - 클라이언트가 요청을 보내고, 서버가 요청에 맞는 응답을 보내면 연결이 끊김
- 무상태(Stateless)
  - 연결을 끊는 순간 클라이언트와 서버는 서로의 상태정보를 유지하지 않는다 -> 다시 연결되면 기존에 연결된 적 있는 클라이언트인지 서버는 모름

## HTTP와 HTTPS의 차이(TLS)

### HTTPS(HyperText Transfer Protocol over Secure Socket Layer)

-
