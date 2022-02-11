## ROW_NUMBER
- SELECT를 하나 생성해서 ORDER BY 없이 순번을 매길 수 있다
- 사용법

```
SELECT ROW_NUMBER() OVER(ORDER BY sal DESC) AS rownum
     , ename
     , job
     , sal
  FROM emp
 WHERE sal > 2000
```
![다운로드](https://user-images.githubusercontent.com/53891485/153320156-1f36e0d2-13f2-4ef4-bdf4-0d7255af0437.png)


## CASE
- 조건을 지정해 쿼리를 검색하는 방법
- CASE, WHEN, THEN, END 사용
- 사용법
```
CASE 컬럼  

     WHEN 조건1 THEN 값1 

     WHEN 조건2 THEN 값2 

     ELSE 값3 

     END 
```

## WITH
- 임시 테이블을 생성해 한번 정의한 값을 여러번 재사용할 수 있다.
- 사용법
```
WITH 사용할가상테이블별칭 AS (SELECT 문) ---1
SELECT * FROM 사용할가상테이블별칭 ---2


```









