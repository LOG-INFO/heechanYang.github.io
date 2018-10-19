---
layout: post
title:  "TCP/UDP"
date:   2018-10-19 20:16:01 +0830
categories: Network
---

# TCP(Transmission Control Protocol)
TCP는 번역하여 '전송 제어 프로토콜'이라고 하며, IP Suite의 핵심 프로토콜 중 하나로, 합쳐서 TCP/IP라고 불린다.

TCP는 OSI 7 Layer 중 전송계층(Transport layer)에 위치한다.

## 역할
근거리통신망, 인트라넷, 인터넷에 연결된 컴퓨터에서 실행되는 프로그램 간에 일련의 옥텟을 안정적으로, 순서대로, 에러없이 교환할 수 있게 한다.

## 사용 예시
- 웹 브라우저들이 World Wide Web에서 서버에 연결할 때
- 이메일 전송
- 파일 전송

## 세션 연결
TCP는 **3-Way Handshake**를 통해 세션에 연결한다.

![3-way_handshake](/assets/images/3-way_handshake.PNG)

## 세션 해제
세션을 해제할 때는 **4-Way Handshake**방식을 취한다.

![4-way_handshake](/assets/images/4-way_handshake.PNG)

## 예시
![handshake_example](/assets/images/handshake_example.PNG)
\* (1)은 (5)~(7)의 과정이, (4)는 (11)~(14)의 과정이 생략된 것
## Flag
- **SYN(Synchronization)**  
    **"통신하자!"**  
    : 연결 요청. 세션 개설에 사용.  
    초기에 Sequence Number를 임의로 생성하여 전송.

- **ACK(Acknowledgement)**  
    **"ㅇㅋ!"**  
    : TCP계층에서 수신자가 발신자의 Sequence Number에 데이터의 길이 또는 양을 더한 값을 전송.  
    ACK의 번호와 응답을 통해 보낸 패킷의 손실을 판단하여 재전송하거나 다음 패킷을 전송.

- **FIN(Finish)**  
    **"끊자!"**  
    : 연결 해제 요청. 세션 종료에 사용.  
    발신자가 더이상 보낸 데이터가 없음을 보여줌.

- **RST(Reset)**  
    **"끊고 다시 연결하자!"**  
    : 강제로 세션을 초기화할 때 사용.  
    양방향에서 동시에 일어나는 중단작업으로, 비 정상적인 세션을 해제할 때 사용.

- PSH(Push)  
    : 대화형 트래픽에서 사용.  
    수신측은 버퍼가 찰 때까지 기다리지 않고, 수신 즉시 버퍼링된 데이터를 응용프로그램에 전달.

- URG(Urgent)  
    : Urgent pointer 필드에 값이 채워져있음을 알림.

## 장점
- 신뢰성 보장
- 순차 보장
## 단점
- 오버헤드가 큼
- 지연시간 긺


# UDP(User Datagram Protocol)
UDP는 TCP와 함께 데이터그램으로 알려진 단문 메시지를 교환하기 위해서 사용된다.

UDP 또한 TCP와 마찬가지로 IP Suite의 핵심 프로토콜 중 하나로서 전송계층에 위치한다.

## 장점
- 오버헤드가 작음
- 지연시간이 짧음

## 단점
- 전달 확인 못 함
- 순차 보장 못 함
