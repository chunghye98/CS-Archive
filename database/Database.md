# Database란?
> DB, DBMS, DB System, Data Model, Schema, Database Language 에 대해 알아보자

## Database, DB
전자적으로 저장되고 사용되는 관련있는 데이터들의 조직화된 집합

## Database Management System
사용자에게 DB를 정의하고 만들과 관리하는 기능을 제공하는 소프트웨어 시스템
ex. PostgreSQL, MySQl, Oracle

### metadata
database를 정의하거나 기술하는 데이터, DBMS를 통해 저장/관리된다.    
ex. 데이터 유형, 구조, 제약 조건, 보안, 저장, 인덱스, 사용자 그룹 등

## Database System
database + DBMS + 연관된 applciations, 줄여서 database라고도 부른다.

## Data Models
- DB의 구조를 기술하는 데 사용될 수 있는 개념들이 모인 집합
  - DB 구조를 **추상화**해서 표현할 수 있는 수단을 제공한다.
  - DB 구조: 데이터 유형, 관계, 제약사항 등
- 여러 종류가 있으며 추상화 수준과 DB 구조화 방식이 조금씩 다르다
- DB에서 읽고 쓰기 위한 기본적인 동작(Operations)들도 포함한다

### Data Models 분류
1. **Conceptual Data Model**    
- 일반 사용자들이 쉽게 이해할 수 있는 개념들로 이루어진 모델
- 추상화 수준이 가장 높음
- 비즈니스 요구사항을 추상화하여 기술할 때 사용
ex. ER Diagram

2. **Logical Data Model**    
- 데이터가 컴퓨터에 저장될 때의 구조와 크게 다르지 않게 DB 구조화를 가능하게 한다.
- 특정 DBMS나 Storage에 종속되지 않는 수준에서 DB를 구조화할 수 있는 모델
ex. Relational Data Model(테이블 형태)

3. **Physical Data Model**    
- 컴퓨터에 데이터가 어떻게 파일 형태로 저장되는지를 기술할 수 있는 수단을 제공
- data format, data orderings, access path(ex. index) 등

## Database Schema
데이터 모델을 바탕으로 Database의 구조를 기술한 것이다.    
Schema는 Database를 설계할 때 정해지며 한 번 정해진 후에는 자주 바뀌지 않는다.

### Three-Schema Architecture
각 레벨을 독립시켜서 어느 레벨에서의 변화가 상위 레벨에 영향을 주지 않기 위해 스키마를 3계층으로 나눈다.

<img src="https://github.com/chunghye98/CS-Archive/assets/57451700/46c265f4-a01c-4597-a33d-27583ae7185a" width="40%">

1. **내부 스키마 Internal Schema**    
물리적으로 데이터가 어떻게 저장되는지 physical data model을 통해 표현한다.    


2. **외부 스키마 External Schema**    
특정 유저들이 필요로 하는 데이터만 표현한다. 그 외 알려줄 필요가 없는 데이터는 숨긴다.   
logical data model을 통해 표현한다.

3. **개념 스키마 Conceptual Schema**    
전체 Database에 대한 구조를 기술, 물리적인 저장 구조에 관한 내용은 숨긴다.

## Database Language
### DDL, Data Definition Language
conceptual schema를 정의하기 위해 사용되는 언어

### DML, Data Manipulation Language
Data 추가, 삭제, 수정, 검색 등의 기능을 제공하는 언어

### DCL, Data Control Language
데이터베이스에 접근하고 객체들을 사용하도록 권한을 부여하는 언어

### TCl, Transaction Control Language
논리적인 작업의 단위를 묶어서 트랜잭션 별로 제어하는 언어

## 참고
[쉬운코드](https://www.youtube.com/watch?v=aL0XXc1yGPs&list=PLcXyemr8ZeoREWGhhZi5FZs6cvymjIBVe)
