# Key란?
> Relational Database 에서 사용하는 Key의 종류에 대해 알아보자

## Key
relation의 tuple을 식별할 수 있는 단일 속성 혹은 속성들의 집합을 의미한다.
기본키, 외래키, 후보키, 대체키가 있다.

- 유일성: 중복되는 값이 없다.
- 최소성: 필드를 조합하지 않고 최소 필드만 써서 키를 형성할 수 있다.


<img src="https://github.com/chunghye98/Algorithm/assets/57451700/cf9eabfb-7ae3-41b0-9423-be1e2563ede8" width="40%">

### 기본키 Primary Key
유일성과 최소성을 만족하는 키

### 외래키 Foreign Key
다른 테이블의 기본키를 그대로 참조하는 값으로 개체와의 관계를 식별하는 데 사용한다.

### 후보키 Candidate Key
기본키가 될 수 있는 후보들이며 유일성과 최소성을 동시에 만족한다.

### 대체키 Alternate Key
후보키가 두 개 이상일 경우 어느 하나를 기본키로 지정하고 남은 후보키들을 말한다.

### 슈퍼키 Super Key
각 레코드를 유일하게 식별할 수 있는 유일성을 갖춘 키이다.
