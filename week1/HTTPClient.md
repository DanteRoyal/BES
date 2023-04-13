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

### DNS

## 포트(port)

## path(경로)

## Java text blocks

## Java InputStream과 OutputStream

## Java try-with-resources
