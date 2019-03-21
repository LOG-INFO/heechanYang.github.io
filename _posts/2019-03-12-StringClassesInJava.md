---
layout: post
title:  "String vs StringBuffer vs StringBuilder - LOG.INFO"
date:   2019-03-12 14:46:20 +0830
categories: Java
---

# 배경

`Java`에서 자주 사용되는 `String` 저장/처리 관련 Class인 `String`, `StringBuilder`, `StringBuffer`에 관하여 정리해보았다.

# String, StringBuilder, StringBuffer

- `String`은 **immutable**하여 thread-safe하고 조회 시 상대적으로 빠르지만, **수정 시 새로운 객체를 생성**하므로 느림.

  - `
    The implementation of the string concatenation operator ( + ) is left to the discretion of a Java compiler, as long as the compiler ultimately conforms to The Java™ Language Specification. For example, the javac compiler may implement the operator with StringBuffer, StringBuilder, or java.lang.invoke.StringConcatFactory depending on the JDK version. The implementation of string conversion is typically through the method toString, defined by Object and inherited by all classes in Java.
    `
  - 정리하면 JDK 버전에 따라 String에서의 + 오퍼레이터가 다르게 작동한다고 한다. StringBuffer를 쓰든 String Builder를 쓰든 등..
  - 참고로 Java는 Custom Operator 정의를 지원하지 않음.
    - 컴파일 시 변환해준다고 한다.

- `StringBuilder`는 **mutable**하여 수정 시 빠름. 단,  **thread-safe하지 않아** **멀티스레드 환경에 적합하지 않지만** 싱글스레드에선 `StringBuffer`보다 빠름.

- `StringBuffer`는 **mutable**하여 수정 시 빠름. **thread-safe**하여 **멀티스레드 환경에서도 적합**하지만 싱글스레드에서 `StringBuilder`보다 느림.

[정리]
- 조회가 훨씬 많을 경우 `String`을 쓰는 것이 낫다.
- 수정이 많을 경우 `StringBuilder`나 `StringBuffer`를 사용하는데,
  - 멀티스레드 환경에선 `StringBuffer`을 써야하고
  - 싱글스레드 환경에선 `StringBuilder`를 사용하는 것이 유리함.
- `JDK 1.5`부터는 `String` `+ 연산` 시 `StringBuilder`로 변환되어 처리한다고 한다.
  - 하지만 그렇다고 `+`연산을 남용하는 것은 비추. 새로운 `StringBuilder`를 생성하여 연산을 하기 떄문에 **공간낭비**, **시간낭비**.

# 참고문헌

- [String (Java SE 9 & JDK 9 ) - Oracle Docs](https://docs.oracle.com/javase/9/docs/api/java/lang/String.html)
- [String (Java Platform SE 7 ) - Oracle Docs](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html)
- [JAVA String, StringBuffer, StringBuilder 차이점](https://jeong-pro.tistory.com/85)
- [Java 문자열 연결 방법 비교](https://futurecreator.github.io/2018/06/02/java-string-concatenation/)