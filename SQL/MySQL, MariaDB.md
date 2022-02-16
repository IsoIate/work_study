## Cast
- 문자를 숫자로, 숫자를 문자로 변환하는 연산자
- cast type의 종류는 binary, char, signed (부호있는 숫자), date, datetime, time, unsigned (부호없는 숫자) 등이 있다.
- 사용방법
```
// 문자를 숫자로 변환할 때에는
select cast('1' as unsigned) as test
// 숫자를 문자로 변환할 때에는
select cast(2 as char(1)) as test
```

## LPAD, RPAD
- 왼쪽이나 오른쪽에 특정 문자를 원하는 자리수만큼 넣는 연산자
- LPAD : 왼쪽에 특정문자를 원하는 자리수만큼 채워서 반환
- 사용법 : LPAD(원본문자열 , 원하는 자리수, 채울 문자열)
```
SELECT LPAD('ABC',10,'0')  FROM DUAL;

// 결과 : 0000000ABC
```
- RPAD : 오른쪽에 특정문자를 원하는 자리수만큼 채워서 반환
- 사용법 : RPAD(원본문자열 , 원하는 자리수, 채울 문자열)
```
SELECT RPAD('ABC',10,'0')  FROM DUAL;

// 결과 : ABC0000000
```
