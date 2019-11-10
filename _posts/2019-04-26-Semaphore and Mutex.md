---
layout: post
comments: true
title:  "세마포어(Semaphore)와 뮤텍스(Mutex) - LOG.INFO"
date:   2019-04-26 19:03:23 +0830
categories: etc
---

## 배경

이전 포스팅에서는 교착상태(DeadLock)에 대해 알아보았다.  
본 포스팅에서는 세마포어(Semaphore)와 뮤텍스(Mutex)에 대해 알아본다.

먼저 이전 포스팅에서 했던 교착상태에 대해 간단히 되새겨 보고 가자.

## 교착 상태(DeadLock)란?

교착상태란 **두 개 이상의 작업이 서로 상대방의 작업이 끝나기 만을 기다리고 있기 때문에 결과적으로 아무것도 완료되지 못하는 상태**를 말한다.

## 임계 구역(Critical Section)

각 프로세스에서 공유 데이터를 액세스하는 프로그램 코드 부분

## 세마포어(Semaphore)

**세마포어**란 **여러 프로세스/스레드가 공유된 자원의 데이터에 접근하는 것을 `Signaling mechanism`을 이용하여 통제하는 것**을 말하며, 독일의 컴퓨터 사이언티스트인 Edsger Dijkstra가 고안하였다.

세마포어는 단순한 정수 변수이다.
- 세마포어가 0이라면 이미 제한된 수의 프로세스가 Critical Section에 접근하고 있는 상태이므로, 
    - 세마포어가 1 이상이 될 때까지 임계구역에 접근하는 다른 프로세스들은 대기하게 된다
- 세마포어가 1 이상의 수라면 다른 프로세스가 임계구역에 접근할 수 있다

### 세마포어 종류

- Counting Semaphore : 임의의 수의 리소스를 허용
  - **생산자-소비자** 문제 해결
- Binary Semaphore : 최대 한 개의 리소스를 허용
  - locked/unlocked 구현 시 사용

### 예시 - 독서실

- 어떤 독서실에는 공부를 할 수 있는 방이 10개가 있다.
- 각 방은 한 번에 한 명만 사용할 수 있다.
- 사용 중이던 학생이 사용을 종료해야 다른 학생이 사용할 수 있다.

1. 학생이 방을 사용하려면 먼저 카운터에 방이 있는지 물어봐야 한다.
   1. 방이 있다면 사용하고
   2. 방이 없다면 사용 중인 학생이 사용을 종료할 때까지 기다려야 한다.
2. 방을 사용하여 공부를 한다. (Critical Section)
3. 공부를 다 하고, 카운터에 가서 방 사용을 종료함을 알린다.
4. 새로운 학생이 방을 사용할 수 있게 된다.

### 구현

```java
// Wait : 프로세스가 Critical Section에 진입하기 전에 세마포어가 남아있는지 확인
// 만약 세마포어가 여유가 없으면
// block을 하거나 semaphore's queue에 삽입
void P(Semaphore S, int I) {
    while(S >= I) {
        S -= I
    }
}

// Signal : 프로세스가 Critical Section을 벗어나고 세마포어를 늘려줌
void V(Semaphore S, integer I) {
    S += I
}
```

## 뮤텍스(Mutex)

**뮤텍스**란 **공유된 자원의 데이터를 여러 프로세스/스레드가 접근하는 것을 `Locking mechanism`을 이용하여 제어하는 것**을 말한다.

뮤텍스는 기본적으로는 Binary Semaphore와 비슷하고, 때때로 기본적인 구현도 같다. - Wikipedia

다른 점이라면 '어떻게 사용되는가?'  
Mutex에서는 lock을 건 Thread만 해당 lock을 unlock할 수 있다.
그렇기에
- lock을 거는 Thread의 id를 저장해두고, unlock 시 검증을 한다.
- 우선순위가 높은 Thread가 대기할 때, 우선순위 변경을 쉽게 할 수 있다.
- 뮤텍스를 잡고 있는 Thread가 갑자기 종료되었을 시, 안전하게 뮤텍스를 release할 수 있다.
- 'mutex'는 재귀할 수 있다. 'thread'는 교착 상태를 일으키지 않고 여러 번 잠글 수 있다.(??)

## 세마포어와 뮤텍스의 차이

### Mutex

- 공유 리소스에 대한 접근을 조율하기 위해 `Locking Mechanism`(locking / unlocking)을 사용
- Binary Semaphore와 비슷하다
- critical section과 유사(?)
- 동기화 대상이 오직 하나
  - 예) 화장실 열쇠를 1개만! 가질 수 있다.

### Semaphore

- 공유 리소스에 대한 접근을 조율하기 위해 `Signaling Mechanism`(wait / signal)을 사용
- 카운트 기능으로 여러 개의 스레드가 접근 가능
- 동기화 대상이 하나 이상
  - 예) 화장실 칸이 4개이고 열쇠가 4개라면, 4명까지는 대기없이 사용할 수 있고 그 다음부터는 대기를 해야한다.

## 꼬리를 물고 물어~

### **생산자-소비자 문제(producer-consumer problem)**

- 한정 버퍼 문제(bounded-buffer problem)라고도 함
- 유한한 개수의 물건(데이터)을 임시로 보관하는 보관함(버퍼)에 여러 명의 생산자들과 소비자들이 접근한다. 생산자는 물건이 하나 만들어지면 그 공간에 저장한다. 이때 저장할 공간이 없는 문제가 발생할 수 있다. 소비자는 물건이 필요할 때 보관함에서 물건을 하나 가져온다. 이 때는 소비할 물건이 없는 문제가 발생할 수 있다.
- **세마포어**를 사용하여 해결

### **식사하는 철학자들 문제**

### **독자-저자 문제(Reader-Writer Problem)**

- 여러 명의 독자와 저자들이 하나의 저장 공간(버퍼)을 공유하며 이를 접근할 때 발생하는 문제
  - 독자
    - 독자는 공유 공간에서 데이터를 읽어온다.
    - 여러 명의 독자가 동시에 데이터를 읽어오는 것이 가능하다.
  - 저자
    - 저자는 공유 공간에 데이터를 쓴다.
    - 한 저자가 공유 공간에 데이터를 쓰고 있는 동안에는 그 저자만 접근이 가능하며, 다른 독자들과 저자들은 접근할 수 없다.

#### 저자 프로세스

```text
wait(wrt);    // 임계구역에 들어가기 위해 허가가 나기를 기다린다.
...
쓰기 작업 수행
...
signal(wrt);  // 임계구역에서 빠져나왔음을 알린다.
```

#### 독자 프로세스

```text
wait(mutex);
    readcount++;     // 독자 수 1 증가
    if readcount = 1
        wait(wrt);   // 쓰고 있는 저자가 없을 때까지 기다린다.
signal(mutex);
...
읽기 작업 수행
...
wait(mutex);
    readcount--;     // 독자 수 1 감소
    if readcount = 0
        signal(wrt); // 독자가 없다면 이를 알린다.
signal(mutex);
```

## 참고문헌

- [교착 상태 - 위키백과, 우리 모두의 백과사전](https://ko.wikipedia.org/wiki/%EA%B5%90%EC%B0%A9_%EC%83%81%ED%83%9C)
- [Semaphore (programming) - Wikipedia](https://en.wikipedia.org/wiki/Semaphore_(programming))
- [임계 구역 - 위키백과, 우리 모두의 백과사전](https://ko.wikipedia.org/wiki/%EC%9E%84%EA%B3%84_%EA%B5%AC%EC%97%AD)
- [[운영체제] 쓰레드 동기화, 세마포어(Semaphore), 뮤텍스(Mutex)](https://armful-log.tistory.com/16)
- [생산자-소비자 문제 - 위키백과, 우리 모두의 백과사전](https://ko.wikipedia.org/wiki/%EC%83%9D%EC%82%B0%EC%9E%90-%EC%86%8C%EB%B9%84%EC%9E%90_%EB%AC%B8%EC%A0%9C)
- [식사하는 철학자들 문제 - 위키백과, 우리 모두의 백과사전](https://ko.wikipedia.org/wiki/%EC%8B%9D%EC%82%AC%ED%95%98%EB%8A%94_%EC%B2%A0%ED%95%99%EC%9E%90%EB%93%A4_%EB%AC%B8%EC%A0%9C)
- [독자-저자 문제 - 위키백과, 우리 모두의 백과사전](https://ko.wikipedia.org/wiki/%EB%8F%85%EC%9E%90-%EC%A0%80%EC%9E%90_%EB%AC%B8%EC%A0%9C)