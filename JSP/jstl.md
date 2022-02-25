## JSTL이란?
- 일반적으로 알고있는 JSTL이란 JSTL + EL의 조합을 말한다.
- HTML 코드 내에 java 코드인 스크립틀릿 <%= student %>를 ${student}로, <%=if %>문을 <c:if>, <%=for%>문을 <c:forEach>로 대체하여 사용한다.
- jstl은 라이브러리 이므로 사용하기 전에 헤더에 추가해 주어야 함
```
<% @taglib uri="http://java.sun.com/jstl/core" prefix="c" %>
```

### JSTL core의 태그들

- <c:set> :	변수명에 값을 할당
- <c:out> :	값을 출력
- <c:if> :	조건식에 해당하는 블럭과 사용될 scope설정
- <c:choose>	: 다른 언어의 switch와 비슷
- <c:when>	: switch문의 case에 해당
  - eq, ne, empty 사용 
- <c:otherwise> :	switch문의 default에 해당
- <c:forEach> :	다른언어의 loop문 items 속성에 배열을 할당할 수 있음
```
// 일반적인 사용 예
<c:forEach var="item" items="${items}">
     <p>번호 : ${status.index}</p>
     <p>책명 : ${item.name}</p>
     <p>저자 : ${item.author}</p>
     <p>출판사 : ${item.publisher}</p>
</c:forEach>
```

### 알아두면 좋은 JSTL 표현들
- javascript에서 model parameter를 가져오는 방법
```
var key = '<c:out value='${key}' />';
```
- javascript에서 context path를 가져오는 방법
```
var G_CONTEXT_PATH = "${pageContext.request.contextPath}";
```
- jsp에서 url의 get parameter 가져오는 방법
```
<c:if test="${param.loginFail eq 'true'}">
  <div class="login-fail">아이디 혹은 비밀번호가 일치하지 않습니다.</div>
</c:if>
```

## subString
- JSTL에서 문자를 자르고 싶을 때 사용
```
// 사용법
${fn:subString(String, num1, num2)}
```



















