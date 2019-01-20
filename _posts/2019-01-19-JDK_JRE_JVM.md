---
layout: post
title:  "JDK/JRE/JVM - LOG.INFO"
date:   2019-01-19 17:19:22 +0830
categories: Java
---

이번 포스트는 JDK와 JRE, JVM에 대해 알아본다

# Java

일단 Java에 대해 간단히 말을 하면 **JCP에서 제안하고 JSR에서 통과된 프로그래밍 언어**를 말한다.

## Java code가 돌아가는 과정

1. 프로그램 실행 시 JVM은 OS로부터 자원을 할당받고, 용도에따라 영역을 나누어 관리한다.
2. javac(컴파일러)가 소스코드파일(.java)을 컴파일하여 바이트코드 파일(.class)을 생성한다.
3. ClassLoader를 통해 바이트코드 파일(.class)을 JVM에 로드한다
4. 로딩된 class 파일들은 Execution engine을 통해 해석된다
5. 해석된 바이트코드는 Runtime Data Area에 배치되어 수행된다

# JDK(Java Development Kit)란?

- Java 개발을 위한 여러 도구들을 포함하는 툴킷
  - javac, java 등
- JRE와 개발을 위해 필요한 도구(javac, java등)들을 포함

## 종류

- Oracle JDK
  - 2017년 8월, Oracle에서 Oracle JDK의 라이선스 변경(BSD->GPL)으로 상업적으로 무료로 사용하는 것이 불가능해졌다. 따라서 많은 곳에서 OpenJDK로 변경하는 사태가 벌어짐
- OpenJDK
  - 오픈소스 진영의 JDK로, 최근 라이선스 문제를 해결하고자 많이들 찾는다 (본인 포함)
- Zulu
  - Zulu라는 회사에서 배포하는 JDK. TCK를 통과함. 이 JDK는 아직 상업용도 무료이기에 Zulu로 넘어가는 곳도 많음.
- Zing
  - Zulu와 같은 회사에서 배포하는 JDK. 이것 역시 유료임.

# JVM(Java Virtual Machine)이란?

- Java Application을 실행하기위한 가상 머신
- 보통 JDK를 설치할 때 같이 설치됨
- JVM은 플랫폼에 의존적임
  - 즉, 리눅스의 JVM과 윈도우즈의 JVM은 다름
- 역할
  - 바이너리 코드를 읽음
  - 바이너리 코드를 검증
  - 바이너리 코드를 실행
  - 실행환경의 규격을 정의 (필요한 라이브러리 및 기타파일)

# JRE(Java Runtime Environment)란?

- JVM 이 자바 프로그램을 동작시킬 때 필요한 라이브러리 파일들과 기타 파일들을 가지고 있음
  - JRE는 JVM의 실행환경을 구현했다고 할 수 있음

![JDK_JVM_JRE](/assets/images/jdk_jvm_jre.PNG)

# 정리

- Oracle JDK도 비상업적 사용은 무료다
  - 개인 공부 등
- 하지만 상업적으로 사용할 땐 유료로 구독해야한다
  - 대신 기술지원도 해준다
  - 그래서 많은 기업들이 OpenJDK로 넘어갔다
- 기존에도 유료 Oracle JDK 모델이 있었다
  - 기업들이 기술적 지원을 위해 유료로 사용했겠지
- Oracle JDK와 OpenJDK의 차이
  - 과거엔 OpenJDK의 성능과 안정성이 떨어짐
  - 현재는 OracleJDK에서 추가로 제공하는 일부 Library를 제외하곤 다를 바 없음.
    - Font Library
    - Java Web Start
    - 등

# 꼬리를 물고 물어~~~

- OpenJDK을 관리하는 주체는 오라클이다
- `Java`는 `플랫폼 독립적`이지만, `JDK`, `JVM`, `JRE`는 `플랫폼 종속적`이다.

# 참고문헌

- [Kotlin 공홈](https://kotlinlang.org/)
- [Kotlin Wikipedia](https://en.wikipedia.org/wiki/Kotlin_(programming_language))
- [Android는 새 언어가 필요할까? Kotlin - Realm](https://academy.realm.io/kr/posts/android-kotlin/?_ga=2.127291149.184681768.1547018221-757539608.1547018221)
- [안드로이드 공식 언어가 된 Kotlin을 알아보자 by 박민우 - Realm](https://academy.realm.io/kr/posts/kotlin-official-android-language/)
- [정적언어(타입)과 동적언어(타입) - [IT 마이닝]](http://itmining.tistory.com/65)
- [Kotlin의 빛과 그림자 - 레진 기술 블로그](https://tech.lezhin.com/2017/08/03/the-case-against-kotlin)
- [JDK, JRE, JVM의 차이 - Two rab](http://tworab.tistory.com/13)
- [JVM, JRE, JDK의 차이 - 점프 투 자바](https://wikidocs.net/257)
- [Java 유료 논쟁, Oracle JDK와 OpenJDK의 차이 정리 - OKKY](https://okky.kr/article/490213?note=1490642)
- [자바가상머신, JVM이란 무엇인가? - _Jbee](http://asfirstalways.tistory.com/158)