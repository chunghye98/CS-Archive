# Race Condition이란?
> 동기화, 공유 자원, 임계 구역, Race Condition, 상호 배제에 대해 알아보자

## 동기화 Synchronization
프로세스들 사이의 수행 시기를 맞추는 것을 의미한다. 
- **실행 순서 제어**: 프로세스를 올바른 순서대로 실행하기
- **상호 배제**: 동시에 접근해서는 안 되는 자원에 하나의 프로세스만 접근하게 하기
이 두가지가 프로세스들 사이의 순서를 맞추기 위한 것이다.

### 실행 순서 제어를 위한 동기화
Writer 프로세스와 Reader 프로세스가 동시에 실행 중이라고 가정하자. Reader 프로세스는 Writer 프로세스의 실행이 끝나야 실행할 수 있다. 
이렇게 동시에 실행되는 프로세스를 올바른 순서대로 실행하는 것이 첫 번째 프로세스 동기화이다.

### 상호 배제를 위한 동기화
상호배제(mutual exclusion)는 공유가 불가능한 자원의 동시 사용을 피하기 위해 사용하는 알고리즘이다.

예를 들어, 계좌에 0원이 들어 있다고 가정하자. 프로세스 A는 현재 저축된 금액에 2만원을 넣는 프로세스이고, 프로세스 B는 현재 저축된 
금액에 5만원을 넣는 프로세스이다. A 프로세스의 값이 저장되기 전에 프로세스 B가 실행된다면 최종 잔액이 5만원이 될 수 있다. 
A가 끝나기 전에 B가 잔액을 읽었기 때문에 일어난 결과다.     
이를 해결하기 위해, A가 제대로 실행이 끝날 때까지 B가 기다리고, 이후에 B를 실행시켜야 한다.     
이와 같이 동시에 접근해서는 안 되는 자원에 동시에 접근하지 못하게 하는 것이 상호 배제를 위한 동기화이다.

## 공유 자원 shared resource
동시에 실행되는 프로세스들이 공동으로 사용하는 자원을 의미한다. 공유 자원은 전역 변수, 파일, 입출력장치, 보조기억장치 등이 될 수 있다. 

## 임계 구역 critical section
공유 자원 중에 두 개 이상의 프로세스를 동시에 실행하면 문제가 발생하는 자원이 있다. 이 자원에 접근하는 코드 영역을 임계 구역이라 한다.

## Race Condition
잘못된 실행으로 인해 여러 프로세스가 동시 다발적으로 임계 구역의 코드를 실행하여 문제가 발생하는 경우를 말한다.

## 임계 구역 문제 해결 원칙 3가지
1. **상호 배제 mutual exclusion**    
   한 프로세스가 임계 구역에 진입했다면 다른 프로세스는 임계 구역에 들어올 수 없다.
2. **진행 progress**    
   임계 구역에 어떤 프로세스도 진입하지 않았다면 임계 구역에 진입하고자 하는 프로세스는 들어갈 수 있어야 한다.
3. **유한 대기 bounded waiting**    
   한 프로세스가 임계 구역에 진입하고 싶다면 그 프로세스는 언젠가는 임게 구역에 들어올 수 있어야 한다.

<img src="https://github.com/chunghye98/CS-Archive/assets/57451700/f16866e7-b6d2-4e05-984a-8696abb6c78c" width="40%">

## 참고
혼자 공부하는 컴퓨터구조 + 운영체제  