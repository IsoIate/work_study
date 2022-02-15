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
