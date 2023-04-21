# 학습 키워드

- URI & URL & URN
- MIME type

## URL

URL = Uniform Resource Locator

리소스의 위치를 나타내는 문자열.

http 나 https와 같은 프로토콜을 포함하며 도메임 이름과 포트번호 등과 함께 리소스의 위치를 나타낸다

## URI

URI = Uniform Resource Identifier

URI는 리소스 자체를 식별하는 문자열

## URN

URN = Uniform Resource Name

URN은 자원의 이름을 의미한다

![https://www.researchgate.net/figure/The-illustration-of-the-URL-URN-and-URI-26_fig4_346585530](/week2/image/URLURIURN.png)

## MIME

- MIME은 파일 변환을 위한 포맷이다.

* 기존에 시스템에서 바이너리 파일을 전송하기 위해선 텍스트 파일로 변환이(인코딩) 필요하게 되어 MIME을 사용
* HTTP 요청 및 응답 그리고 메일 첨부파일과 같이 인터넷을 통해 전송되는 파일 및 데이터의 유형을 식별하는데 사용한다.
* 받는쪽에 데이터를 올바르게 처리할수 있게 도와준다.
* 슬래쉬(/)를 기준으로 기본 유형과 하위유형으로 구성된다.
* 인코딩 : 데이터를 원래 형식에서 다른 형식으로 변환하는 프로세스
* 디코딩 : 데이터를 원래 형식으로 다시 변환하는 프로세스

## MIME TYPE(Conetent Type, Media Type)

- 요청/응답 시에 HTTP 메세지의 헤더에서 Content-Type에 인코딩 된 데이터의 어떤 종류의 데이터 인지 담아 알려준다.
