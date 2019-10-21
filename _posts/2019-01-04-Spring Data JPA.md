---
layout: post
comments: true
title:  "JPA(Java Persistence API)란? - LOG.INFO"
date:   2018-12-20 22:34:22 +0830
categories: java
---

이번 포스트는 Spring Framework에서 애용되는 ORM(Object-Relational Mapping)기술인 JPA에 대해 정리해 보았다.

# 배경

## 문제

요즘 MongoDB와 같은 NoSQL DB가 뜨고 있긴 하지만, 아직까지 대부분의 데이터베이스는 관계형 데이터베이스로 구축이 되어있다.

또, 주로 **객체**를 **관계형 DB**에 저장을 하고 있다.

문제는 반복되고 지루한 SQL 쿼리들을 매번 작성해야한다는 것이다. 더 문제는 **자바 객체**를 **SQL**로, **SQL**을 **자바 객체**로 바꿔주는 작업을 해야한다.

또한, 객체에 컬럼이 새로 수정되면 관련 쿼리들을 전부 찾아서 수정해주어야 한다. 이 과정은 굉장히 손이 많이 가며 실수하기 쉽다.

또한, 연관된 객체들을 불러오려면 먼저 연관된 객체들까지 전부 JOIN해서 가져와야함.

```java
Member member = memberDAO.find(id);
member.getTeam(); //hmmm..
member.getOrder().getDelivery(); // hmmm.........
```

또한, SQL 의존적인 개발이 불가피하다.  
- 개발자 ≒ SQL 매퍼

## 문제 발생 이유

### 패러다임의 불일치 - 객체지향 VS 관계형 DB


# JPA(Java Persistence API)

`JPA`란 `Java ORM API 표준`을 말하며 Java EE에 속한다. ORM은 Object와 RDBS의 개념적인 불일치를 해결하고자 나온 기술이다. 즉, RDB를 객체지향적으로 사용하기 위해 나온 기술이다. 주의해야 할 것은 ORM은 그저 데이터와 객체를 매핑해주는 기술이 아니다. ~~(이 부분에 대해선 나중에 보완하기로)~~

# Spring Data JPA

`Spring Data JPA`는 Spring Data 프로젝트의 일환으로, `Spring에서 JPA를 추상화한 것`을 말한다. Spring으로 개발한 Application에서 JPA을 기반으로 한 Data-access layer에대한 지원을 강화하여 데이터 접근을 수월하게 해준다.

오래 전부터 어플리케이션에서 Data-access layer를 구현하는 것은 성가신 일이었다. Pagination과 Auditing 같은 간단한 쿼리를 호출하는 데에도 수 많은 Bolier-plate code가 사용되었고, Column이 수정될 때마다 일일이 수정해줘야하는 것은 여간 귀찮은 일이 아니었다. 이러한 개발자들의 수고를 덜어주고자 나온 스펙이 JPA이고, 이것을 Spring에 맞게 추상화한 것이 Spring Data JPA이다. 

# Hibernate

`Hibernate`는 `JPA를 구현한 구현체`로 ORM Framework중 하나이다.

# 정리

- `JPA` : Java의 ORM 기술 표준 스펙
- `Spring Data JPA` : 스프링에서 JPA를 추상화한 것
- `Hibernate` : JPA를 실제로 구현한 구현체  
(JPA의 구현체로는 Hibernate 말고도 EclipseLink, DataNucleus가 있음)

### JPA의 장점

- Boiler-plate code를 대폭 감소시켜준다.
- 손 쉽게 RDB의 데이터와 객체를 매핑해줄 수 있다.
- 특정 데이터베이스에 종속되지 않고 개발할 수 있다.
- 도메인 변화에 대응하기 수월하다. 

### JPA의 단점

- 자동 생성되는 쿼리가 항상 가장 좋은 퍼포먼스를 가진다는 보장이 없다.  
(직접 짜는 쿼리의 성능이 더 좋을 수도 있음. 초기엔 직접 짠 쿼리보다 성능이 좋지 않은 경우가 많았다고 함. 하지만 점점 개선하여 성능이 훨씬 좋아졌다고 함.)
- 높은 러닝 커브 (어렵다 어려워..)

# 꼬리에 꼬리를 물어~~~

- Auditing : 수정일자, 생성일자, 생성자, 수정자 컬럼에 자동으로 값을 넣어주는 기능.
- Persistence??  

```
Persistence in this context covers three areas:  
- The API itself, defined in the `javax.persistence package`  
- JPQL(Java Persistence Query Language)  
- Object/Relational metadata
```

- Spring Data Family?
    - Spring Data JPA
    - Spring Data LDAp
    - Spring Data MongoDB

# 참고 문헌

- [https://victorydntmd.tistory.com/195](https://victorydntmd.tistory.com/195)
- [https://spring.io/projects/spring-data-jpa#overview](https://spring.io/projects/spring-data-jpa#overview)
- [https://www.inflearn.com/course/%EC%8A%A4%ED%94%84%EB%A7%81-%EB%8D%B0%EC%9D%B4%ED%84%B0-jpa/](https://www.inflearn.com/course/%EC%8A%A4%ED%94%84%EB%A7%81-%EB%8D%B0%EC%9D%B4%ED%84%B0-jpa/)
- [https://en.wikipedia.org/wiki/Java_Persistence_API](https://en.wikipedia.org/wiki/Java_Persistence_API)
- [http://www.libqa.com/wiki/769](http://www.libqa.com/wiki/769)