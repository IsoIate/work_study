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
