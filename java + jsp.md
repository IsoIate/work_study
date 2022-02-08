### toString과 String.value()의 차이점

- String.valueOf() - 파라미터가 null이면 문자열 "null"을 만들어서 반환한다.
- toString() - 대상 값이 null이면 NPE를 발생시키고 Object에 담긴 값이 String이 아니여도 출력한다.

- String.valueOf()는 null체크를 "null".equals(string) 형태로 체크함

### Map.Entry
- Map.Entry 는 Map 형태의 인터페이스를 만드는데 사용한다.
- Map을 For 문에서 돌려줄 경우 인터페이스 용도로 사용한다.

```
HashMap<String, Integer> map = new HashMap<>();
      map.put("A", 3);
      map.put("B", 4); // map에 Key, Value 삽입


    for (Map.Entry<String, Integer> entry : map.entrySet()) {
        System.out.println("getKey : " + entry.getKey());
        System.out.println("getValue : " + entry.getValue());
    }
```

### StringUtils
- 문자열에 작업하는 관련기능을 모아둔 라이브러리
- StringUtils.replace("문자열", "찾을문자", "변경문자")

```
  String replace = StringUtils.replace("abcabc", "abc", "bbb");
  System.out.println(replace)   // bbbabc
```
