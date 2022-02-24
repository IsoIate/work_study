## input value 값 가져오기
- input value를 가져오는 방법은 id, class, name으로 3가지이다.
- var id = $("#id").val()
- var class = $('.class').val()
- var name = $('input[name=abc]').val()

## name 지정자 가져오기, 동일 name 여러개 가져오기
- 동일한 name을 사용하는 요소의 값을 각각 가져오고 싶을 때 사용

```
// 예시
<input type="hidden" name="groupod" value="1">
<input type="hidden" name="groupod" value="2">
<input type="hidden" name="groupod" value="3">

<input type="button" id="commentbtn" value="배열만들기"/></td>

$(function(){

	$('#commentbtn').on('click', function(){
    	//값들의 갯수 -> 배열 길이를 지정
		var grpl = $("input[name=groupod]").length;
		//배열 생성
		var grparr = new Array(grpl);
		//배열에 값 주입
		for(var i=0; i<grpl; i++){                          
			grparr[i] = $("input[name=groupod]").eq(i).val();
	        alert(grparr[i]);
	    }
	});
});
```

## radio 선택된 값 가져오기
```
// radio 선택된 값 가져오기 
$('input[name=gender]:radio'); 
var radiovalue = $('input[name=라디오버튼네임]:checked').val();

// radio의 value값으로 선택하기 
$("input[@name=rList]").filter('input[@value='+sValue+']').attr("checked", "checked");
```

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
- $(".KGON").html("\<H1>케이곤\</H1>"); KGON이라는 클래스를 가진 CLASS에 \<H1>케이곤\</H1>이라는 HTML 태그를 포함한 문자열을 정의합니다. 
- $(".KGON").html(); KGON이라는 클래스를 가진 CLASS에서 HTML태그를 포함한 문자열을 가져옵니다.

### APPEND(), PREEND() 함수
- 이 함수는 요소의 마지막에 자식요소를 추가해 주는 함수입니다.
- $("#KGON").append("\<option value="kgon3">케이곤3\</option>"); KGON이라는 이름을 가진 ID의 마지막자식요소로 \<option value="kgon3">케이곤3\</option>을 추가합니다. 
- 이 함수는 요소의 처음에 자식요소를 추가해주는 함수입니다.
- $("#KGON").preend("\<option value="kgon0">케이곤0\</option>"); KGON이라는 이름을 가진 ID의 처음자식요소로 \<option value="kgon0">케이곤0\</option>을 추가합니다

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
## 이벤트리스너 안에서 쓰는 이벤트 함수들 
- 이벤트리스너 콜백함수안에 파라미터를 하나 추가하면 이벤트관련 함수들을 쓰실 수 있습니다. 
- e.target은 지금 실제 클릭한 요소
- e.currentTarget은 지금 이벤트리스너가 달린 곳 (참고로 this라고 쓰셔도 같은 의미입니다.)
- e.preventDefault()는 기본 동작을 막을 때 쓰고 
- e.stopPropagation()은 내 상위요소로의 이벤트 버블링을 중단할 때 씁니다. 

## eq() 함수
- 선택한 요소의 인덱스 번호에 해당하는 요소를 찾는다
- 없으면 null 반환

```
// 예시
<div class="test">
  <ul>
    <li>a</li>
    <li>b</li>
    <li>c</li>
  </ul>
</div>

<script>
  
  let testData = $(".test li").eq(1);

  // li태그중 1번 인덱스의 값인 b를 반환
  console.log(testData.text()); // b

</script>
```









