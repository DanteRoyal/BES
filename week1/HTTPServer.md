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

## Blocking vs Non-Blocking(추가 공부 필요)

- Blocking: 호출된 대상이 자신의 작업을 완료 할때까지 작업의 제어권을 가지고 있어서 호출한 대상은 대기하는 것
- Non-Blocking: 호출된 대상이 자신의 작업을 완료하지 않았어도 호출한 대상은 다른일을 진행하는 것
