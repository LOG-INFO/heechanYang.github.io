---
layout: post
title:  "Java SE/EE/ME - LOG.INFO"
date:   2018-12-03 03:00:23 +0830
categories: Java
---

이번 포스트는 항상 궁금했지만 눈 앞의 일에 급급하여 찾아보지 않던 Java SE/EE/ME에 대해 알아본 내용을 정리해보았습니다. 

먼저 간단하게 Java SE/EE/ME는 모두 Java Platform에 속하며, Java SE가 이들의 기본이 됩니다. 

Java Platform은 Java로 기술된 프로그램 개발 및 배포에 필요한 소프트웨어 모임의 총칭이다. Java로 개발된 프로그램은 특정 운영체제나 하드웨어에 의존하지 않고 동일하게 작동하도록 바이트코드인 추상코드로 구현되며 JVM이라는 가상환경 위에서 동작합니다.

그럼 Java Platform 각각에 대해서 더 자세히 알아보도록 하겠습니다.

# Java SE (Java Standard Edition)

**Java SE**은 ava Application을 데스크탑 또는 서버에 배포할 수 있도록 지원해주는 표준 자바 플랫폼입니다. Java SE는 범용 API들을 정의하고 있으며, 자바 언어와 JVM의 규격(Specification)을 포함하고 있다. Java SE의 가장 널리 알려진 구현체(Implementation)들로는 Oracle사의 JDK(Java Development Kit)와 오픈소스 진영의 OpenJDK가 있습니다.

## 범용 패키지

- java.lang
- java.lang.ref
- java.lang.reflect
- java.io
- java.nio
- java.util

# Java EE (Java Enterprise Edition)

**Java EE**은 **Java SE의 확장 그리고 분산 컴퓨팅과 웹서비스와 같은 Enterprise feature들의 Specification을 포함**합니다. Java EE Application은 트랜잭션, 보안, 확장성, 동시성 그리고 Component들의 관리를 다루는 **Microservices** 또는 **Application Server** 등에서 실행됩니다.

Java EE는 다음과 같은 Specification들을 포함하고 있습니다.
- Web Specifications
    - Servlet
    - WebSocket
    - Java Server Faces(JSF)
    - Java Server Pages(JSP)
- Web Service Specifications
    - RESTful Web Services을 위한 API
    - JSON Processing을 위한 API
    - JSON Binding을 위한 API
    - XML Web Services을 위한 API
- Enterprise Specifications
    - Contexts and Dependency Injection : Spring Framework과 같은 DI 컨테이너를 제공하는 Specification
    - Enterprise Java Bean(EJB)
    - Java Persistence API (JPA)
    - Java Transaction API
    - Java Message Service
- Other Specifications
    - Validation
    - Batch Applications

> The Java platform (Enterprise Edition) differs from the Java Standard Edition Platform (Java SE) in that it adds libraries which provide functionality to deploy fault-tolerant, distributed, multi-tier Java software, based largely on modular components running on an application server.

# Java ME (Java Micro Edition)

**Java ME**은 제한된 자원을 가진 Embedded 또는 모바일 디바이스(Micro-controllers, 센서, 휴대폰, PDA, 셋톱박스 등)에서도 Java 프로그래밍 언어를 지원하기 위한 Java Platform 중 하나이고, Sun Microsystem사에서 고안하였습니다.

# 꼬리에 꼬리를 물어~~~

- **JSF** : JSF(Java Server Faces)
- **Facelets** : 
- **SOAP** : SOAP(Simple Object Access Protocol)은 일반적으로 널리 알려진 HTTP, HTTPS, SMTP 등을 통해 **XML 기반의 메시지**를 컴퓨터 네트워크 상에서 교환하는 프로토콜
- **Specification** : 규격? 사양? Specification?
- **JDK? JRE?**
- **Java 2?**

# 참고 문헌
- https://en.wikipedia.org/wiki/Java_Platform,_Standard_Edition
- https://www.oracle.com/technetwork/java/javase/overview/index.html
- https://en.wikipedia.org/wiki/Java_Platform,_Enterprise_Edition
- https://www.oracle.com/technetwork/java/javaee/overview/index.html
- https://en.wikipedia.org/wiki/Java_Platform,_Micro_Edition
- https://www.oracle.com/technetwork/java/embedded/javame/index.html
- https://en.wikipedia.org/wiki/JavaServer_Faces
- https://ko.wikipedia.org/wiki/SOAP
- https://stackoverflow.com/questions/2857376/difference-between-java-se-ee-me/45108378 