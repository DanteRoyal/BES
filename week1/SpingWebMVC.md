## 학습 키워드

- Spring
- Spring Boot
- Spring initializer
- Web Server와 Web Application Server(WAS)
  - Tomcat
- Model-View-Controller(MVC) 아키텍처 패턴
- 관심사의 분리(Seperation of Concern)
- Spring MVC
- Java Annotation
- Spring Annotation
  - @RestController
    - @Controller
    - @ResponseBody
  - @GetMapping
    - @RequestMapping

## Spring

Spring Framework는 자바 애플리케이션 개발을 위한 오픈소스 프레임 워크이고 객체 지향 프로그래밍과 의존성 주입을 기반으로 개발자의 부담을 덜어주며, 스프링 프레임워크가 객체 생성 및 관리를 하므로 IoC는 객체간의 의존성을 관리하며 결합도를 낮춰주며 유지보수를 쉽게 해준다. AOP는 애플리케이션의 부가 기능을 모듈화 하여 관리하기 때문에 로깅,보안,트랜잭션 처리 등과 같은 공통 기능을 별도의 모듈로 구현하여 이를 필요로하는 모듈과 연결하여 사용 가능하게 한다. 다양한 데이터 액세스 기술을 지원하며, 애플리케이션 개발에 필요한 기본적인 대부분의 기능을 지원하기 때문에 개발자는 비지니스 로직에만 집중 할수 있다.

### 스프링의 핵심

- IoC/DI
- AOP
- PSA

## Spring Boot(더 알아보자)

- 복잡하고 짜증나는 스프링의 설정을 간편하게 해줌
- 톰캣을 내장형 웹 서버로 제공
- 스프링에 비해 개발, 테스트, 배포가 간편함

## Spring initializer

- Spring Boot 프로젝트를 생성하고 구성할 수 있는 웹 기반 툴
- 프로젝트 구조와 빌드 파일을 자동 생성하여 개발자가 작성 할 필요 없음

## Web Server와 Web Application Server(WAS)

### Tomcat

## Model-View-Controller(MVC) 아키텍처 패턴

![https://developer.mozilla.org/ko/docs/Glossary/MVC](/week1//image/MVC_Architecture.png)

- 애플리케이션의 논리와 UI를 분리하여 개발의 유지 보수와 확장성을 향상 시킴

* 각각 독립적으로 동작하여 하나의 요소를 변경하더라도 다른 요소에 영향을 미치지 않음.

1. Model: 데이터와 비지니스 로직을 담당. 데이터 처리, 저장, 검색 등의 작업이 이루어지고, 변경이 발생 할 경우 View에 알려야 할 상태 정보를 가지고 있음.
2. View: UI를 구성하고, Model의 데이터를 사용자에게 보여주고, 사용자의 입력을 받아 Controller로 전달
3. Controller: 사용자의 입력을 받아 Model과 View사이를 제어함. 사용자의 요청에 따라 Model의 상태를 변경하거나, 적절한 View를 선택하여 사용자에게 보여줌.

## 관심사의 분리(Seperation of Concern)

- 디자인 원칙중 하나
- 애플리케이션의 서론 다른 관심사를 독립적인 모듈로 분리하여 코드의 가독성, 재사용성, 유지 보수성을 향상 시키는 것을 목표
- 각 모듈은 한가지의 역할을 하게되며, 다른 모듈과 최소한의 상호작용을 함으로써 시스템이 변경되거나 확장될 때 다른 모듈에 영향을 주지 않고 수정 할 수 있음.

## Spring MVC

![https://terasolunaorg.github.io/guideline/5.3.1.RELEASE/en/Overview/SpringMVCOverview.html](/week1//image/Spring_MVC.png)
|이름|역할|
|:---------:|:-------:|
|D|역할|
|||

## Java Annotation

## Spring Annotation

## @RestController

@Controller
@ResponseBody

## @GetMapping

@RequestMapping
