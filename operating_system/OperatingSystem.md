# 운영체제란?
> 운영체제의 개념과 역할에 대해 알아보자

## 운영체제(OS, Operating System) 
<img src="https://github.com/chunghye98/CS-Archive/assets/57451700/ab5bfe04-d44b-40b1-8938-f7ef16df762e" width="30%">

실행할 프로그램에 필요한 **자원**을 할당하고 관리하며, 응용 프로그램과 하드웨어 간의 인터페이스로써 다른 응용 
프로그램이 유용한 작업을 할 수 있도록 환경을 제공해주는 프로그램이다.


항상 컴퓨터가 부팅될 때 메모리 내 **커널 영역 kernel space**
이라는 공간에 따로 적재되어 실행된다. 커널 영역을 제외한 영역은 **사용자 영역 user space**라 한다.

즉, 운영체제는 커널 영역에 적재되어 사용자 영역에 적재된 프로그램들에 자원을 할당하고 이들이 효율적으로 실행되도록 
만드는 시스템 프로그램이다.

<img src="https://github.com/chunghye98/CS-Archive/assets/57451700/82d89e74-3c67-429c-ab78-8fc7e84a0d5c" width="30%">

## 커널(Kernel)
운영체제의 핵심 서비스를 담당하는 부분
> 운영체제가 제공하는 서비스 중 커널에 포함되지 않는 서비스로는 `사용자 인터페이스(UI, User Interface)`가 있다. 이는 그저 컴퓨터와 상
호작용하기 위한 통로일 뿐 커널에 속한 기능은 아니다.    
운영체제가 제공하는 사용자 인터페이스의 종류에는 `그래픽 유저 인터페이스(GUI, Graphical User Interface)`와 `커맨드 라인 인터페이스
(CLI, Command Line Interface)`가 있다.

## 운영체제(커널)의 핵심 서비스
1. **프로세스 관리**    
   CPU는 한 번에 하나의 프로세스만 실행할 수 있기에 여러 프로세스를 조금씩 번갈아가며 실행한다. 각 프로세스마다 사용하는 자원이 다양하기
    때문에 운영체제는 다양한 프로세스를 효율적으로 관리하고 실행시킨다.
2. **자원 접근 및 할당**    
   - CPU    
     각 프로세스에 공정하게 CPU를 할당하기 위한 CPU 스케줄링
   - 메모리    
     운영체제가 프로세스에 어떻게 메모리를 할당하며, 메모리가 부족할 경우 극복 방법
   - 입출력장치    
     인터럽트 서비스 루틴을 통한 입출력 작업 수행
3. **파일 시스템 관리**    
   운영체제가 보조기억장치 속 데이터를 파일과 디렉터리로 관리하는 방법
    
   

## 참고
혼자 공부하는 컴퓨터구조 + 운영체제    
[tech-interview-for-developer](https://github.com/gyoogle/tech-interview-for-developer/blob/master/Computer%20Science/Operating%20System/Operation%20System.md)