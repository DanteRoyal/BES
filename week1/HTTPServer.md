## 학습 키워드

- Java ServerSocket
- Blocking vs Non-Blocking

## Java ServerSocket

- ServerSocket은 자바에서 서버 프로그램을 만들때 사용하는 클래스이다. Client의 경우 요청과 응답만 하면 되지만, Server의 경우 요청을 받아 처리해야 하기 때문에 ServerSocket을 사용하여 Client의 접속을 확인하고 `Socket.accept()`메서드를 실행하여 클라이언트의 요청을 받아 들인다. 매 Client 마다 하나의 ServerSocket이 생성되며 이때마다 `accpet()`가 호출 되게 되어 서버의 과부하가 걸릴수 있다. 이에 쓰레드를 사용한다.
  |서버|통신방향|클라이언트|
  |:---------:|:---:|:-------:|
  |클라이언트의 요청을 받기위한 준비(ServerSocket, Listen)|||
  |클라이언트의 요청을 처리(Socket.accept())|<-|서버에 접속 요청(Socket)|
  |클라이언트가 보낸 요청을 읽음(Socket.getInputStream())|<-|서버에 요청 메세지를 보냄(Socket.OutputStream())|
  |클라이언트에 응답(Socket.getOutputStream())|->|서버가 보낸 메세지를 받음(Socket.getInputStream())|
  |종료 (Socket.close())| |종료(Socket.close())|

## Blocking vs Non-Blocking

- Blocking: 특정 작업이 완료될 때까지 프로세스의 흐름이 중단되는 것. 작업이 완료 될때까지 멈추게 되므로 비효율적
- Non-Blocking: 특정 작업이 완료되지 않아도 프로세스의 흐름을 계속 진행하는 것. 다른 작업을 병렬적으로 처리 할 수 있어 효율성이 증가. Non-blocking은 비동기 프로그래밍과 관련이 깊어 콜백함수, 프로미스, 이벤트 루프 등의 개념을 활용하여 구현 가능.
