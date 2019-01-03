# Spring Framework

: Java Enterprize Application 개발에 사용되는 Application Framework.

- Enterprize Application?  
    : 
- Application Framework?  
    : Application을 구성하는 Object가 생성되고 동작하는 방식에 대한 틀을 제공해주고, 코드를 작성하는 기준을 제시.

## Application의 기본 틀 - Spring Container

- Spring Container(Application Context)  
    : 'Spring Runtime Engine'으로, 설정정보를 참고하여 Application 을 구성하는 Object를 생성, 관리함.

## 공통 프로그래밍 모델 - IoC/DI, 서비스 추상화, AOP

- IoC? (Inversion of Control : 제어의 역전)  
    : 
- DI? (Dependency Injection : 의존성 주입)  
    : IoC의 일종으로,  
- 서비스 추상화?   
    : 구체적인 기술과 환경에 종속되지 않도록 유연한 추상 계층을 두는 방법. (Strategy Pattern 참조) 
    - 환경이나 서버, 특정 기술에 종속되지 않고 이식성이 뛰어나며 유연한 Application을 만들 수 있도록 해줌.
- AOP? (Aspect Oriented Programming)  
    : Application 코드에 산재해서 나타나는 부가적인 기능을 독립적으로 모듈화하는 프로그래밍 모델.
    - 다양한 엔터프라이즈 서비스를 적용하고도 깔끔한 코드를 유지할 수 있게 해줌.

## 기술 API

: Spring은 Enterprize Application을 개발의 다양한 영역에 바로 활용할 수 있는 방대한 양의 기술 API를 제공함
- UI 작성
- 웹 프레젠테이션 계층
- 비즈니스 서비스 계층
- 기반 서비스 계층
- 도메인 계층
- 데이터 액세스 계층
- 등


## 스프링을 사용한다! == 아래 세가지 요소를 적극적으로 활용해서 애플리케이션을 개발한다!

- 클래스가 스프링 컨테이너 위에서 오브젝트(Bean)로 만들어져 동작하도록
- 코드는 스프링의 프로그래밍 모델을 따라서
- 엔터프라이즈 기술을 사요할 때는 스프링이 제공하는 기술 API와 서비스를 활용하도록



# 나중에 찾아보자

- OXM?
- RestTemplate?
- Message Converter?
- @MVC?
- 내장형 DB
    - H2
    - HSQL
    - Derby
- 자바빈 규약?
    - 자바빈은 Default Constructor를 가져야 한다. 툴이나 프레임워크에서 리플렉션을 이용해 오브젝트를 생성하기 때문.
    - 자바빈의 프로퍼티들은 get으로 시작하는 getter와 set으로 시작하는 setter를 이용해 수정/조회할 수 있어야 한다.
- JDBC을 이용한 작업의 일반적인 순서
    1. DB 연결을 위한 Connection을 가져옴.
    2. SQL을 담은 Statement(or PreparedStatement)를 생성.
    3. 생성된 Statement를 실행.
    4. SQL을 생성. (조회의 경우 결과를 ResultSet으로 받아서 오브젝트에 옮겨줌)
    5. 작업 중에 생성된 Connection, Statement, ResultSet 같은 리소스는 작업 후 반드시 닫아줌.
    6. JDBC API가 만들어낸 Exception을 잡아서 직접 처리하거나 / 메소드에 throws를 선언하여 메서드 밖으로 던짐

- 관심사의 분리 (Seperation of Concerns)
    