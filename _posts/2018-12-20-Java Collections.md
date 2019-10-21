---
layout: post
comments: true
title:  "Java Collections - LOG.INFO"
date:   2018-12-20 22:34:22 +0830
categories: java
---

이번 포스트는 Java의 Collection API을 정리해 보았습니다. 

# Java Collection Framework

# interface Collection\<E\>

- Collection 계급의 최상위 인터페이스.  
- element라 불리는 object들의 그룹을 표현한다.
- 중복 허용 O / 중복 허용 X
- 정렬 / 비정렬
- 동기 / 비동기
- 모든 범용(?) Collection의 구현체들은 두 개의 "표준" 생성자를 갖는다.
    - Empty Constructor
    - Single Map type param Constructor

# interface List\<E\>

## 구현체

- Vector\<E\>
- ArrayList\<E\>
- LinkedList\<E\>

# interface Set\<E\>

- 중복을 허용하지 않음
  - Map의 Key와 같은 성질을 띄고 있어 실제로 HashSet은 HashMap을 기반으로 짜여져 있다.
- Null값 허용

## 구현체

- HashSet\<E\>
- TreeSet\<E\>

# interface Map\<K, V\>

- 모든 범용(?) Map의 구현체들은 두 개의 "표준" 생성자를 갖는다.
    - Empty Constructor
    - Single Collection type param Constructor
- Key - Value 형식의 element들을 가지는 Map의 interface
- 키의 중복을 허용하지 않는다.
- TreeMap은 정렬 보장함 / HashMap은 정렬 보장 안 함

## 구현체

- HashMap\<K, V\>
- TreeMap\<K, V\>

# class LinkedList\<E\>

# 정리

# 꼬리에 꼬리를 물어~~~

- Map이 Collection에 속하지 못하는 이유?
  - 필요한 파라미터가 두 개(K, V)라서??
- Interface, Abstract Class, Class
- capacity? load factor? threshold?

# 참고 문헌

- https://en.wikipedia.org/wiki/List_of_HTTP_status_codes
- https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol
- https://ko.wikipedia.org/wiki/HTTP
- https://www.popit.kr/%EB%82%98%EB%A7%8C-%EB%AA%A8%EB%A5%B4%EA%B3%A0-%EC%9E%88%EB%8D%98-http2/
- https://developer.mozilla.org/ko/docs/Web/HTTP/Basics_of_HTTP/Evolution_of_HTTP
- https://item4.github.io/2018-02-08/Basic-HTTP-Status-Codes/
- http://www.ktword.co.kr/abbr_view.php?m_temp1=3790&id=902&nav=2