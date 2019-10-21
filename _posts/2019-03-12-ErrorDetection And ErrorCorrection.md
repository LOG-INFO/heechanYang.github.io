---
layout: post
comments: true
title:  "Error Detection And Error Correction - LOG.INFO"
date:   2019-03-12 14:46:20 +0830
categories: Network
---

# 배경

네트워크 수업을 듣다가 Parity bit 얘기가 잠깐 나와서 이전에 배운 내용을 정리해보았다.

# 오류 발생 원인

- **감쇠(Attenuation)**
  - 신호가 전송 매체를 통해 이동하다가 약해지는 현상
  - 주파수가 높을수록 감쇠 현상이 심해짐
  - 해결하기 위해 중계기(Repeater)를 이용
- **지연 왜곡(Delay Distortion)**
  - 하나의 전송 매체를 통해 여러 신호를 전달했을 경우 주파수에 따라서 그 속도가 달라짐으로써 생기는 오류
- **상호 변조 잡음(Intermodulation Noise)**
  - 서로 다른 주파수들이 하나의 전송매체를 공유할 때 주파수 간의 합이나 차로 인해 새로운 주파수가 생성되는 잡음
  - 주로 유선 통신에서 발생
- **충격 잡음(Impurse Noise)**
  - 비연속적이고 불규칙한 진폭을 가지며, 순간적으로 높은 진폭이 발생하는 잡음
  - 번개 등에 의해 발생

# 에러 검출(Error Detection)

수신된 데이터에 오류가 없는지 여부를 확인

- **Parity Check**
  - 1 bit 오류 검출 가능
- **Cyclic Redundancy Check(CRC)**
  - 여러 bits 오류 검출 가능
  - `Exclusive OR` 연산 사용
  - `16-bit CRC` or `32-bit CRC`
- **Checksum**
  - 네트워크를 통해서 전송된 데이터의 값이 변경되었는지(무결성) 검사하는 값
  1. IP 패킷의 헤더를 16 Bits(2 Bytes)씩 끊는다.
  2. 끊은 것들을 전부 더한다.
     1. carry가 발생한다면 그것도 더한다
  3. 1의 보수를 취하면 그것이 `Checksum`.

# 에러 수정(Error Correction)

- **FEC**(전진 오류 수정, Forward Error Correction)
  - 오류를 검출하여 재전송 요구 없이 **스스로 수정**하는 방식
  - 역채널 필요 없음
  - 종류
    - **Hamming code** (검출 후 정정 가능, 1 bit 오류)
- **BEC**(후진 오류 수정, Backward Error Correction)
  - 오류가 발생하면 송신 측에 **재전송을 요구**하는 방식
  - 역채널 필요
  - 종류
    - **Parity check** (검출만 가능, 1 bit 오류)
    - **CRC** (검출만 가능, 여러 bits 오류)
  
# 참고문헌

- [패리티 비트(Parity bit), CRC, Checksum, 블럭 코딩, FEC - 김동은넷](http://blog.naver.com/PostView.nhn?blogId=no5100&logNo=220733958064)
- [데이터통신 제11절 오류(에러) 제어 방식 - 류프리](https://www.youtube.com/watch?time_continue=6&v=Y9Cc9T9_Ke0)