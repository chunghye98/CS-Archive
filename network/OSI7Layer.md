# OSI 7 계층이란?
> OSI 7 Layer에 대해 알아보자

## OSI 7 계층
네트워크에서 통신이 일어나는 과정을 7단계로 나눈 것이다.

<img src="https://camo.githubusercontent.com/ad7d385b0fdce7183bc739b1c0dd2fc28a72e5207159001cb9e6785610d5131d/68747470733a2f2f73373238302e7063646e2e636f2f77702d636f6e74656e742f75706c6f6164732f323031382f30362f6f73692d6d6f64656c2d372d6c61796572732d312e706e67" width="40%">

### 계층을 나누는 목적
통신이 일어나는 과정을 단계별로 알 수 있고, 특정한 곳에 이상이 생기면 그 단계만
수정할 수 있기 때문이다. 즉, 관심사의 분리다.

### 1L : 물리, Physical
단지 데이터를 전기적인 신호로 변환해서 주고받는 기능을 진행하는 공간이다.
즉, 데이터를 전송하는 역할이다.    
ex. 리피터, 케이블, 허브 등

### 2L : 데이터 링크, Data Link
물리 계층으로 송수신되는 정보를 관리하여 안전하게 전달되도록 도와주는 역할이다.
MAC 주소를 통해 통신한다. 데이터 단위는 __Frame__ 이다.  
NIC(Network Area Card, LAN 카드, H/W)가 MAC 주소를 갖는다.    
RARP 프로토콜로 MAC 주소로 IP 주소를 찾을 수 있다.    
ex. 브릿지, 스위치 등

### 3L : 네트워크, Network
데이터를 목적지까지 전달하는 기능을 한다. 라우터 안에 있는 라우터 테이블을 통해
이동할 경로를 선택하고, 해당 경로에 따라 패킷을 전달해준다.    
ip 주소를 사용하며, 데이터 단위는 패킷이다.    
라우팅, 흐름제어, 오류제어, 세그멘테이션 등을 수행하는 계층이다.   
ARP 프로토콜로 IP 주소로 MAC 주소를 찾을 수 있다.    
ex. 라우터

### 4L : 전송, Transport
TCP와 UDP 프로토콜을 통해 통신을 활성화한다. 포트를 열어두고,
프로그램들이 전송을 할 수 있도록 제공해준다.    
헤더에 Port 번호가 포함되어 있다. 데이터의 단위는 세그먼트다.    
ex. TCP, UDP

### 5L : 세션, Session
데이터가 통신하기 위한 논리적 연결을 담당한다. TCP/IP 세션을 만들고 없애는
책임을 지니고 있다(소켓을 연다).    
통신을 하고자 하는 두 호스트 간의 연결을 설정, 관리, 종료한다.
ex. Socket

### 6L : 표현, Presentation
데이터 표현에 대한 독립성을 제공하고 암호화하는 역할을 담당한다.
파일 인코딩, 명령어를 포장, 압축, 암호화한다(JPG -> JPEG).     
ex. JPEG, MPEG 등

### 7L : 응용, Application
end-point로 응용 프로세스와 직접 관계하며 일반적인 응용 서비스를 수행한다.
사용자 인터페이스, 전자우편, 데이터베이스 관리 등의 서비스를 제공한다.    
ex. HTTP, HTTPS, FTP 등

## 프로토콜 Protocol
컴퓨터 내부에서 또는 컴퓨터 사이에서 데이터 교환의 방식을 정의하는 규칙 체계

## 데이터 전송 과정
<img src="https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F0e0e3c41-05e2-43c6-bd7c-396e5fc4ef1c%2F99da61d2-56be-49cd-ad4d-f37a701560c7%2FUntitled.png?table=block&id=e495effb-bcd6-485b-bf1d-9ce01d5c79be&spaceId=0e0e3c41-05e2-43c6-bd7c-396e5fc4ef1c&width=1160&userId=1547f059-4016-482e-aafd-1b5aea9dc2a0&cache=v2" width="40%">

<img src="https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F0e0e3c41-05e2-43c6-bd7c-396e5fc4ef1c%2Fd3b4ed08-eef0-4036-a30e-55ff9fe99951%2FUntitled.png?table=block&id=ae60aef6-ce41-4f3a-a93f-23f60db31c59&spaceId=0e0e3c41-05e2-43c6-bd7c-396e5fc4ef1c&width=1160&userId=1547f059-4016-482e-aafd-1b5aea9dc2a0&cache=v2" width="40%">

송신자 측에서 주로 Encapsulation이 일어나고, 수신자 측에서 주로 
Decapsulation이 일어난다.

## 참고
[OSI 7 계층](https://github.com/gyoogle/tech-interview-for-developer/blob/master/Computer%20Science/Network/OSI%207%20%EA%B3%84%EC%B8%B5.md)
