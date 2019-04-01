---
layout: post
title:  "JavaScript란? - LOG.INFO"
date:   2019-03-30 14:00:00 +0830
categories: Node.js
---

# 배경

 안드로이드 개발을 해오다가 처음 백엔드에 입문할 당시 `Node.js`와 `Spring Franework` 중 어떤 것으로 개발을 할지 매우 고민한 적이 있다. 결국 기존에 `Java`로 개발해왔던지라 팔은 안쪽으로 굽는다고 `Spring Framework`을 선택하였지만, 나중에 꼭 `Node.js`로도 개발을 해보겠다고 다짐**만**하다가 드디어 시작하게 되었다. `Node.js`는 다음 포스트부터 알아보기로 하고 먼저 그의 기반이 되는 언어인 `JavaScript`에 대해 먼저 알아보기로 한다.

# JavaScript?

 먼저 JavaScript란 무엇인지에 대해서 알아보자.
- `가벼운` `인터프리터형` 또는 `JIT-컴파일형` 프로그래밍 언어
- `프로토타입 기반` 프로그래밍 언어
- `객체 기반`의 `스크립트 언어`

## JavaScript의 특징

- **거의** 모든 것이 객체
  - 기본 데이터 타입, null(?), undefined 제외
  - **함수도 객체**

## JavaScript의 자료형

- Primitive Type
  - Boolean
  - Null
  - Undefined
  - Number
  - String
  - Symbol
- Object
  - 배열
  - 함수

## JavaScript의 함수 선언

- 매개변수의 타입을 적지 않는다. (**동적 타입 언어이기 때문**)
- **호이스팅**에 영향 받음

1. 함수 선언문
- 함수명 반드시 있어야 함
```js
function 함수명(){
    // 함수 로직
}
```

2. 변수에 할당 가능
```js
var 함수명 = function (){
    // 함수 로직
}
```

3. **화살표 함수**
- 객체의 메소드를 
```js
() => {
    // 함수 로직
}
```

4. 화살표 함수도 변수에 할당 가능
```js
var 함수명 = () => {
    // 함수 로직
}
```

## JSON(JavaScript Object Notation)

## JavaScript 변수 선언 종류

| |var|let|const|
|-|---|---|-----|
|설명||||
|호환성|전부 호환|ES6 이후 호환|ES6 이후 호환|
|Scope|Function|Block|Block|
|재선언|가능|불가|불가|
|재할당|가능|가능|불가|
|비고|함수 밖에서 선언 시 전역변수||초기화 시 값을 대입하지 않으면 에러 발생|

# 꼬리를 물고 물어~

- `스크립트 언어` vs `컴파일 언어`
  - `스크립트 언어`
    - 코드를 한 줄씩 번역하면서 실행
  - `컴파일 언어`
    - 작성한 코드를 기계 언어로 번역한 후 실행
- `Closure`
- `JavaScript`? `Java`?
  - C언어 기반이라는 공통점만 있고 전혀 관계 없음
  - 그저 `JavaScript`라는 이름을 붙일 때 `Java`의 유명세에 편승하고자 비슷하게 지었다고 함.
  - 초기 이름은 `Mocha` -> `LiveScript` -> `JavaScript`
- **호이스팅**??

# 참고문헌

- [JavaScript - w3schools](https://www.w3schools.com/js/)
- [JavaScript - MDN - Mozilla](https://developer.mozilla.org/ko/docs/Web/JavaScript)
- SOPT 세미나 - 김현진
- [코딩 컨벤션](https://github.com/rwaldron/idiomatic.js/tree/master/translations/ko_KR)