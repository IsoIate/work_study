## DOMContentLoaded, load, unload (beforeunload)
- DOMContentLoaded : HTML이 모두 로드되고, DOM 트리가 완성되었지만, 외부 리소스 (img 등)가 아직 로드되지 않았을 때
  - jQuery의 ready와 유사함
- load : 브라우저에 모든 리소스가 로드되었을 때
- unload : 페이지를 떠날 때

## foreach
- 오직 배열 객체에서만 사용가능한 함수 (ES6부터는 Map, Set도 가능)
```
var items = ['item1', 'item2', 'item3'];

items.forEach(function(item) {
    console.log(item);
});
// 출력 결과: item, item2, item3
```
## for in
- 객체의 속성들을 반복하여 작업을 수행
```
var obj = {
    a: 1, 
    b: 2, 
    c: 3
};

for (var prop in obj) {
    console.log(prop, obj[prop]); // a 1, b 2, c 3
}
```

## filter
- 특정 조건에 부합하는 값을 찾아서 그 값들로 새로운 배열을 만들어 리턴한다.

```
// 사용 예시
arr.filter(callback(element[, index[, array]])[, thisArg]

const arr = [1, undefined, null, false, , '', '    '];
const newArr = arr.filter(data);

newArr.forEach((e, i) => {
  document.write(i + " : " + e + '<br>')
})

function data(params) {
  return params != false && params != null && params != undefined;
}
```

## indexOf(), lastIndexOf()
- indexOf() : 호출하는 문자열 내 특정 값이 등장하는 첫 인덱스를 리턴하며, 발견되지 않으면 -1을 리턴함
- lastIndexOf() : 호출하는 문자열 내 특정 값이 등장하는 마지막 인덱스를 리턴하며, 발견되지 않으면 -1을 리턴함

```
// indexOf 예시 (배열도 사용 가능)
const text = 'Show me the money, big money';
const search = 'money';
console.log(text.indexOf(search)); // 12


// lastIndexOf 예시 (배열도 사용 가능)
const text = 'Show me the money, big money';
const search = 'money';
console.log(text.lastIndexOf(search)); // 23
```
- 위 두 함수를 사용하여 중복 체크를 할 수 있다.

```
const words = ['a', 'b', 'c', 'a'];

for(let i = 0; i < words.length; i++) {
  if(words.indexOf(words[i]) === words.lastIndexOf(words[i])) {
    console.log("unique word");
  }
  else {
    console.log("duplicated word");
  }
}

// 중복 단일 단일 중복
```






















