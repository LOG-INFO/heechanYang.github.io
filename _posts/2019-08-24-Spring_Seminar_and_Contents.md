---
layout: post
title:  "Spring 세미나 (0) : 세미나 준비 및 목차 - LOG.INFO"
date:   2019-05-20 20:15:22 +0830
categories: etc
---

## 배경

그동안 미뤄왔던 서버세미나를 드디어 진행해보려고 합니다.

기술 스택은 Java, Spring Boot, MySQL으로 진행할 예정이구요. 자세한 사항은 정리해서 사전에 다시 공지할 예정입니다.

대상은 다음과 같습니다.
- EC Advance에서 서버를 사용하는 신입 기수 분들
- 서버에 관심이 있지만 어떻게 시작해야할지 모르는 분들

간단한 개념과 간단한 실습으로 구성할 예정이고, 깊은 내용까지는 다루지 않을 예정입니다. 깊은 내용까지 원하시는 분은 따로 질문주시면 답변드리겠습니다.

1차 : 2019.09.02 (월) 19:00 - 양희찬
2차 : 2019.09.09 (월) 19:00 - 조연희

## 사전 준비

이틀이라는 시간동안 세미나에서 모든 내용을 다루기는 어렵습니다. 간단한 내용은 사전에 따로 찾아와 주시고, 실습을 위한 환경을 **꼭!** 세팅해서 오셔야합니다.

- [Java(OpenJDK 12) 설치 및 환경설정](https://www.ihee.com/442)
- IntelliJ ([Community](https://www.jetbrains.com/idea/download/) or [Ultimate](https://whitepaek.tistory.com/6))
  - 약간 귀찮지만 Ultimate 추천.
  - (단, Community로도 실습 가능하긴 함. 그래도 Ultimate 추천)
  - (Eclipse, STS도 가능하긴 함. 그래도 IntelliJ Ultimate 추천)
- 서버란 무엇인지 찾아보고 보고 오기
  - [서버란 무엇인가요? - 얄팍한 코딩사전 - Youtube](https://www.youtube.com/watch?v=R0YJ-r-qLNE)
  - [WEB1 - 17. 인터넷을 여는 열쇠 : 서버와 클라이언트 - 생활코딩](https://opentutorials.org/course/3084/18890)
- [Postman 설치](https://www.getpostman.com/downloads/)
- MySQL 설치 ( [Windows](https://www.popit.kr/mysql-%EC%84%A4%EC%B9%98-%EC%9C%88%EB%8F%84%EC%9A%B0-%ED%99%98%EA%B2%BD/) / [macOS](https://whitepaek.tistory.com/16) )
- [MySQL Workbench 설치](https://dev.mysql.com/downloads/workbench/)
- [Spring Framework 공식 홈페이지 구경](https://spring.io) (다 읽을 필요 없음. 그냥 목차 보고 소개 정도만 보면 됨)
  - 참고로 실습은 [Spring Boo 2.x버전을 이용할 예정](https://docs.spring.io/spring-boot/docs/current/reference/html/)

# Day 1

## Spring Framework 개론

- 서버란?
- 프론트엔드와 백엔드
  - Client
  - Web Server
  - Web Application Server (WAS)
  - Database
- Spring Framework 구조 (MVC)
- Spring Boot란?
- 기술스택
  - 프로그래밍 언어 : **Java** or Kotlin
  - 백엔드 개발 프레임워크 : Spring Framework, Spring Boot
  - 데이터베이스 : MySQL
- 개발툴
  - IDE : **IntelliJ** or Eclipse or STS
  - DB 구축/운영 : MySQL Workbench
  - API 테스트 : Postman

## 실습 (1)

- 실제 프로젝트 구조
  - Controller.java
  - Service.java
  - DAO.java
  - Mapper.xml
- 프로젝트 생성
  - [Spring Initializr](https://start.spring.io/)
  - Dependencies
    - Spring Boot DevTools
    - Spring Web Starter
    - MySQL Driver
- Postman 사용법(미리 짜둔 API로 테스트하면서 보여주기)
- 간단한 API 개발 (경로별 다른 문자열 반환)
  - localhost:8080/helloworld
  - localhost:8080/bye
  - localhost:8080/currenttime
  - 간단한 계산
    - localhost:8080/sum?a=1&b=2
    - localhost:8080/sub?a=1&b=2
    - localhost:8080/mul?a=1&b=2
    - localhost:8080/div?a=1&b=2
    - localhost:8080/mod?a=1&b=2
  - Controller 나누기
    - /calculator/...
    - /string/...
- 정리
- 다음 실습 예고
  - 실제 MySQL DB와 연동

# Day 2

## 실습 (2)

1. 지난 실습 빠르게 복습
2. MySQL 실행
3. MySQL Workbench 연동
   1. 간단한 SQL 실습
      1. CREATE / DROP / INSERT / SELECT / UPDATE / DELETE
4. MyBatis Framework
5. MySQL 연결 설정
6. HTTP Methods
   1. Get - SELECT
   2. Post - INSERT
   3. Put - UPDATE
   4. Delete - DELETE
   5. Fetch - SELECT
   6. etc....
7. DAO vs DTO
8. 실제 SQL문 매핑
   1. INSERT 후 Workbench로 확인
   2. SELECT로 값 가져오기
   3. DELETE / UPDATE
9. 실제 안드로이드 어플리케이션과 연동
   1. 준비해간 Android 어플리케이션과 이렇게 연동된다는 것만 보여주고 끝
10. 정리