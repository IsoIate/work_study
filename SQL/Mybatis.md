## 바인딩
- Mybatis에서는 \#과 \$를 사용해서 외부에서 전달된 파라미터를 동적인 쿼리 변수로 생성할 수 있다.

## \#를 사용할 때
- #을 사용할 경우 오라클의 PreparedStatment를 사용하게 된다.
- 변수에 자동으로 \'가 붙기 때문에 '#{id}' 등과 같이 작성하지 않아도 된다.
```
// 예제(name=John)
   a. mybatis mapper
      SELECT NAME FROM TEST WHERE NAME=#{name}

   b. 오라클에서 받은 쿼리
      SELECT NAME FROM TEST WHERE NAME = ?

// 실제 수행 쿼리
SELECT NAME FROM TEST WHERE NAME='John'
```


## \$를 사용할 때
- $는 간단히 스트링 자체를 변환(REPLACE)해 버린다
```
// 예제(score=99)
   a. mybatis mapper 
      SELECT NAME FROM TEST WHERE SCORE=${score}

   b. 오라클에서 받은 쿼리 
      SELECT NAME FROM TEST WHERE SCORE=99

// 실제 수행 쿼리
SELECT NAME FROM TEST WHERE NAME=99
```

### 차이점 
- 두 가지 결과가 비슷해 보이지만 \#을 사용할 경우 변수를 바인드 처리하기 때문에 NAME값이 달라져도 같은 쿼리로 인식함 (SOFT PARSE)
- 하지만 \$를 사용할 경우 쿼리 자체가 변경되어 들어가기 때문에 SCORE값이 달라지면 다른 쿼리로 인식하고 새로 파싱하는 등 속도가 느려짐 (HARD PARSE)
- 또한, \$를 사용할 경우 문자열 자체를 변형시켜 질의하게 되므로 보안상 취약할 수 있음

```
// 취약점 예시
user를 'admin'--로 세팅, password='aaa'
SELECT * FROM USER WHERE ID=${user} AND PASSWORD=${password}

// 실제 수행 쿼리
SELECT * FROM USER WHERE ID='admin'-- AND PASSWORD='aaa'
```
- admin 이후로 주석처리 되어 관리자로 접속이 가능하게 됨

















