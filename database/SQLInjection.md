# SQL Injection이란?
> SQL Injection에 대해 알아보자

## SQL Injection
해커에 의해 조작된 SQL 쿼리가 데이터베이스에 그대로 전달되어 비정상적 명령을 실행시키는 공격 기법

## 공격 방법
### 1. 인증 우회
input 창에 값을 입력함과 동시에 다른 쿼리를 함께 입력한다.     

__정상 요청__
```
SELECT * FROM USER WHERE ID = "abc" AND PASSWORD = "1234";
```

__공격 요청__    
```
1234; DELETE * USER FROM ID = "1";
```

보안이 완벽하지 않는 경우, 아이디와 비밀번호가 일치해서 true가 되고 delete 문도 데이터베이스에 영향을 줄 수 있다.    
기본 쿼리문의 where 절에 or 문을 추가하여 `'1' = '1'`과 같은 true문을 작성하여 무조건 적용되도록 수정한 뒤 DB를 조작할 수 있다.

### 2. 데이터 노출
시스템에서 발생하는 에러 메시지를 이용해 공격하는 방법이다.    
오류를 의도적으로 발생시켜, 해당 서비스의 데이터베이스 구조를 유추하여 해킹에 활용한다.

## 방어 방법
### 1. input 값을 받을 때, 특수문자 여부 검사하기
로그인 전, 검증 로직을 추가하여 미리 설정한 특수문자들이 들어왔을 때 요청을 막아낸다.

### 2. SQL 서버 오류 발생 시, 해당하는 에러 메시지 감추기
view를 활용하여 원본 데이터베이스 테이블에는 접근 권한을 높인다.     
일반 사용자는 view로만 접근하여 에러를 볼 수 없도록 만든다.

### 3. preparestatement 사용하기
preparestatement를 사용하면, 특수문자를 자동으로 escaping 해준다. (statement와는 다르게 쿼리문에서 전달인자 값을 ?로 받는 것)    
이를 활용해 서버 측에서 필터링 과정을 통해서 공격을 방어한다.

## 참고
[SQL Injection](https://github.com/gyoogle/tech-interview-for-developer/blob/master/Computer%20Science/Database/SQL%20Injection.md)
