## input value값 가져오기
- input value를 가져오는 방법은 id, class, name으로 3가지이다.
- var id = $("#id").val()
- var class = $('.class').val()
- var name = $('input[name=abc]').val()

## 자주 사용하는 jQuery 함수
### VAL() 함수
- 이 함수는 요소들의 값을 정의하거나 , 가져올 때 많이 사용하는 함수입니다. 
- VALUE값이 존재하는 INPUT이나 SELECT 등에서 사용함
- $("#KGON").val(3)은 KGON이라는 이름을 가진 ID의 VALUE값을 3으로 정의합니다. 
- $("#KGON").val();은 KGON이라는 이름을 가진 ID의 VALUE값을 가져옵니다.

### TEXT(), HTML() 함수
- 이 함수는 문자열을 정의하거나, HTML태그를 제외한 문자열을 가져올 때 많이 사용하는 함수입니다. 
- VALUE값이 존재하지 않는 DIV, SPAN 등에서 사용함
- $("#KGON").text("케이곤");은 KGON이라는 이름을 가진 ID에 케이곤이라는 문자열을 정의합니다. 
- $("#KGON").text();은 KGON이라는 이름을 가진 ID에 HTML태그를 제외한 문자열을 가져옵니다. 
- 이 함수는 HTML태그를 포함하여 정의하거나, HTML태그를 포함한 문자열을 가져올 때 많이 사용하는 함수입니다.
- $(".KGON").html("<H1>케이곤</H1>"); KGON이라는 클래스를 가진 CLASS에 <H1>케이곤</H1>이라는 HTML 태그를 포함한 문자열을 정의합니다. 
- $(".KGON").html(); KGON이라는 클래스를 가진 CLASS에서 HTML태그를 포함한 문자열을 가져옵니다.

### APPEND(), PREEND() 함수
- 이 함수는 요소의 마지막에 자식요소를 추가해 주는 함수입니다.
- $("#KGON").append("<\option value="kgon3">케이곤3</option>\"); KGON이라는 이름을 가진 ID의 마지막자식요소로 <option value="kgon3">케이곤3</option>을 추가합니다. 
- 이 함수는 요소의 처음에 자식요소를 추가해주는 함수입니다.
- $("#KGON").preend("<option value="kgon0">케이곤0</option>"); KGON이라는 이름을 가진 ID의 처음자식요소로 <option value="kgon0">케이곤0</option>을 추가합니다

## jQuery.extend()
- 복수의 오브젝트를 합쳐서(merge) 돌려주는 함수
- jQuery.extend(target[, object1][, objectN])
- 같은 프로퍼티가 존재 한다면 b의 값으로 덮어쓰기를 하며 b에 있는 프로퍼티가 새로운 값이라면 추가를 합니다.
```
var a = {
    id: 1,
    name: 'TAM'
};
 
var b = {
    name: 'TAM-new',
    hobby: 'football'  
};
 
$.extend(a, b);
 
console.log(a);
// 결과:
//  {
//      id: 1,
//      name: "TAM-new",
//      hobby: "football"
//  }
```
- 합쳐진 결과 값이 직접적으로 첫번째 파라메터에 반영이 되므로 첫번째 파라메터가 변하는걸 원치 않는 경우에는 아래와 같이 실행하면 된다
```
var a = {
    id: 1,
    name: 'TAM'
};
 
var b = {
    name: 'TAM-new',
    hobby: 'football'  
};
 
var newobject = $.extend({}, a, b);
```











