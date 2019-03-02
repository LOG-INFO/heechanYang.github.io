---
layout: post
title:  "Spring Security OAuth 2.0 (1) - LOG.INFO"
date:   2019-02-26 20:04:33 +0830
categories: Spring Framework
---

# 배경

`Spring Boot`를 사용하는 졸업 작품 개발 중 `인증`&`인가` 기능이 필요하여 `Spring Security`를 사용하기로 하였고, 사용하기 전에 `Spring Security`에 대해서 알아보고자 한다.

먼저 `인증`, `인가`, `접근제어`에 대해서 알아보자.

# 인증(Authentication), 인가(Authorization), 접근 제어(Access Control)

처음에 `인증`과 `인가`가 다른 표현인지 모르고 그때그때 아무거나 골라 쓰기도 하고, `인가`와 `접근 제어`의 차이가 헷갈렸던 기억이 있다. 간단히 각각의 정의를 보면 다음과 같다.

- `인증(Authentication)` : 해당 사용자가 맞는지 확인하는 절차
  - ex) 로그인
- `인가(Authorization)` : 권한 부여, 인증된 사용자에게 권한을 부여하는 것. 권한에 따라 접근 가능한 리소스가 제한된다.
  - ex) 일반 유저 / 프리미엄 유저 / 관리자 등
- `접근 제어(Access-Control)` : `리소스`에 접근 가능한 `권한`을 지정하는 것.
  - ex) `chmod 755 file`

그렇다면 이번엔 이러한 것들을 처리해주는 매커니즘들에 대해서 알아보자.

# 인증 프로토콜? 매커니즘?

## Kerberos

`Network authentication protocol`.

## OIDC(Open ID Connect)

Simple `identity layer` on top of the OAuth 2.0 protocol.

## SAML(Security Assertion Markup Language)

XML-based, open-standard data format for exchanging authentication and authorization data between parties.

## LDAP(Lightweight Directory Access Protocol)

`Software protocol` for enabling anyone to locate organizations, individuals, and other resources such as files and devices in a network, whether on the public Internet or on a corporate intranet.

## OAuth 2.0

`Authorization framework` that enables applications to obtain limited access to user accounts on an HTTP service

# 그래서 어떤 걸 선택해야할까?

`Most technology enabled organization interestingly use Google Apps for Business as directory and SSO. It also supports OAuth 2.0 and the Open ID connect endpoint which allows to build your own sign-in solution.`

물론 케바케겠지만 많은 테크 기업들이 OAuth 2.0과 그 위에 OIDC를 이용하여 Authentication을 덧붙여 사용한다고 한다.
따라서 본 프로젝트에서도 이 방법을 따를 예정이다.

OAuth 2.0, OIDC, 그리고 Spring Security OAuth 2.0 에 대해서는 다음 포스트에서 좀 더 자세히 다루겠다.

# 꼬리를 물고 물어~~

- SSO(통합 인증 : Single Sign On)
  - 한 번의 인증 과정으로 여러 컴퓨터 상의 자원을 이용 가능하게 하는 인증 기능
  - = 싱글 사인온 or 단일 계정 로그인 or 단일 인증
  
# 참고문헌

- [Authentication Protocols: LDAP vs Kerberos vs OAuth2 vs SAML vs RADIUS](https://www.getkisi.com/blog/authentication-protocols-overview)
- [The OAuth 2.0 Authorization Framework, RFC6749](https://tools.ietf.org/html/rfc6749)
- [통합 인증 - Wikipedia](https://ko.wikipedia.org/wiki/%ED%86%B5%ED%95%A9_%EC%9D%B8%EC%A6%9D)
- [SSO - Wikipedia](https://ko.wikipedia.org/wiki/%ED%86%B5%ED%95%A9_%EC%9D%B8%EC%A6%9D)
- [생활코딩 - WEB2 - OAuth 2.0](https://www.youtube.com/watch?v=9eKIYjcPXp4&list=PLuHgQVnccGMA4guyznDlykFJh28_R08Q-&index=1)