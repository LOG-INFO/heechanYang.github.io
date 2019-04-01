---
layout: post
title:  "스프링 빈의 생명 주기(Spring Bean's Life-Cycle) - LOG.INFO"
date:   2019-03-31 12:23:23 +0830
categories: Spring Framework
---

# 배경

본 포스팅에서는Spring Framework에서 Bean의 생명주기에 대해서 알아본다.

## Bean을 관리하는 Interface의 종류

Bean의 **인지 여부**를 관리하는 인터페이스로는 `BeanNameAware`, `BeanClassLoaderAware`, `ApplicationContextAware`이 있고,
Bean의 **생명주기**를 관리하는 인터페이스로는 `InitializingBean`, `DisposableBean`이 있습니다.

## Bean의 생명주기

1. **빈 인스턴스 생성**
2. **빈 프로퍼티에 의존성 주입**
3. **인지 여부 검사**
   1. `BeanNameAware`의 `setBeanName()`
   2. `BeanClassLoaderAware`의 `setBeanClassLoader()`
   3. `ApplicationContextAware`의 `setApplicationContext()`
4. **빈 생명 주기 콜백**
   1. 초기화 후, `InitializingBean`의 `@PostConstruct`
   2. 종료 전, `DisposableBean`의 `@Predestroy`
5. **빈 인스턴스 종료**

# 꼬리를 물고 물어~

- `InitializingBean` & `DisposableBean`

# 참고문헌

- [Spring Bean Life Cycle (빈 생명주기 관리) - 전산쟁이 블로그](https://javaslave.tistory.com/48)
- [Spring Bean Life Cycle Explained](https://howtodoinjava.com/spring-core/spring-bean-life-cycle/)