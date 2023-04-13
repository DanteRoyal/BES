## 학습 키워드

- TCP/IP 통신
- TCP와 UDP
- Socket과 Socket API 구분
- URI와 URL
- 호스트(host)
  - IP 주소
  - Domain name
  - DNS
- 포트(port)
- path(경로)
- Java text blocks
- Java InputStream과 OutputStream
- Java try-with-resources

## TCP/IP 통신

- TCP/IP는 TCP와 IP를 합쳐서 부르는 것
- TCP는 무결성을 보장하는 연결을 통해 데이터를 전달해주는 프로토콜
- IP는 패킷들을 가장 효율적인 방식으로 전송하기 위한 프로토콜

## TCP와 UDP

### TCP

- 전송제어 프로토콜
- 연결 지향 프로토콜
- TCP 3 way handshake(논리적 연결)
- 데이터 전달을 보증: 클라이언트에서 데이터를 전송하면 서버에서 데이터가 제대로 왔는지 응답해줌
- 순서 보장: 순서를 표시하는 정보를 갖고 있기에 패킷의 순서가 잘못된 경우 순서가 잘못된 패킷을 알려주어 재 전송을 받아 순서를 보장함
- 즉, 무결성

### UDP

- 사용자 데이터 그램 프로토콜
- 무결성을 보장하지 않음
- 그냥 보내기 때문에 속도가 더 빠름
- 비연결이기 때문에 경로가 일정하지 않고 패킷들이 꼴리는대로 전송됨

## Socket과 Socket API 구분

Socket은 두 프로그램이 네트워크에서 데이터를 교환 할수 있게 양쪽에 생성되는 프로그램 간의 Endpoint. HTTP가 요청/응답이 있을 때만 데이터를 주고 받는 반면에 Socket은 계속 서로 연결을 유지하는 양방향 통신이다. 서버와 클라이언트가 실시간으로 데이터를 주고 받는 상황이 필요 할때 사용한다.
Sokect API는 자바에서 제공하는 Socket클래스를 이용하여 InputStream과 OutputStream을 통해 클라이언트/서버 간의 통신을 가능하도록 해준다.

```
EndPoint: IP 주소와 port번호의 조합을 의미하며 데이터 송/수신의 최종 목표점
```

## URI와 URL

- URI(Uniform Resource Identifier)
  - 리소스를 구분하여 준다.
  - 쿼리스트링이 대표적인 예시
- URL(Uniform Resource Locator)
  - 리소스의 위치를 표시

```
www.naver.com/posts/1
/posts까지가 URL
/1까지가 URI
```

## 호스트(host)

- 호스트란 네트워크에 연결되어 있는 컴퓨터들을 호스트라고 한다.

### IP 주소

- 네트워크 상의 컴퓨터들 끼리 통신을 위해 사용하는 고유의 주소

### Domain name

- IP 주소를 대신하여 문자로 된 이름을 사용하는 것.

### DNS(Domain Name System)

- Domain name/IP 주소를 각각 Key/Value로 저장하여 사용자가 웹브라우저에서 쉽게 원하는 사이트로 이동을 해주게 하는 시스템

## 포트(port)

한 컴퓨터에서 여러 프로그램을 사용하여 서버와 통신을 할 경우 컴퓨터는 데이터를 받았을때 어떤 프로그램으로 데이터를 전송해야 할지 정보가 없으면 모른다. 이에 사용 하는것이 포트이다. TCP에서 패킷에 어떤 프로그램이 받아야하는지 포트번호를 추가하여 보낸다.
기본적으로 웹서버는 80번 포트를 사용한다.

## path(경로)

리소스에 대한 경로. 일반적으로 port번호 뒤에 /의 뒷부분에 위치한다.

## Java text blocks

- 아래와 같은 코드를 `+`와 `/n`을 사용하여 만드는 것은 굉장히 번거 로워 지기 때문에 `"""`와 `"""`사이에 원하는 문자열을 넣어주면 공백과 `/n`도 적용 시켜서 처리해준다.

```
String body = """
            <html>
                <body>
                    <h1>안녕</h1>
                <body>
            </html>
            """;
```

## Java InputStream과 OutputStream (추가 공부후 업데이트)

![https://hudi.blog/java-inputstream-outputstream](/week1//image/input%3Aoutputstream.png)

- Stream은 기본적으로 데이터가 출발지에서 도착지로 단방향으로 흘러가는 것.
- 바이트 기반 입출력을 하는 스트림 클래스
  - 바이트 기반 입출력 스트림: 그림 등 모든 종류의 데이터들을 주고 받음
  - 문자 기반 입출력 스트림: 문자만 주고 받음

* 스트림은 단방향 통신이기 때문에 입력과 출력을 각각 사용해야함

## Java try-with-resources(추가 공부후 업데이트)

- `try-catch-finally`를 사용하는 경우의 단점을 보완함
- `try()`괄호안에 객체를 선언하면 try블록이 끝날 때 해당 객체를 자동으로 `close()` 함
- 괄호 안에 들어갈 객체는 AutoCloseable 인터페이스가 구현 되어 있어야함
