## input value값 가져오기
- input value를 가져오는 방법은 id, class, name으로 3가지이다.
- var id = $("#id").val()
- var class = $('.class').val()
- var name = $('input[name=abc]').val()

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











