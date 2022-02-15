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

### 예외 처리
- 프로그램을 실행시켰을 때 발생하는 에러를 대응하기 위한 기능

#### try catch
- try catch 를 처리하는 방식은 아래와 같다.
- try 블록 안에서 예외가 발생하면 그 순간에 코드 실행을 중단
- 발생된 예외종류가 catch 블럭의 ( ) 안에 지정한 예외와 일치하면 그 안의 코드를 실행
- catch 블록 안의 코드가 모두 실행되면 try catch 블록 다음에 등장하는 코드를 실행

#### finally
- finally 구문은 예외처리가 발생여부를 떠나 무조건 실행하도록 하는 구문이다.

#### RuntimeExeption과 Exception
- RuntimeException은 실행시 발생하는 예외이고 Exception은 컴파일시 발생하는 예외이다. 
- 즉, Exception은 프로그램 작성시 이미 예측가능한 예외를 작성할 때 사용하고 RuntimeException은 발생 할수도 발생 안 할수도 있는 경우에 작성한다.

```
class FoolException extends RuntimeException {
}

public class Sample {
    public void sayNick(String nick) {
        if("fool".equals(nick)) {
            throw new FoolException();
        }
        System.out.println("당신의 별명은 "+nick+" 입니다.");
    }

    public static void main(String[] args) {
        Sample sample = new Sample();
        sample.sayNick("fool");
        sample.sayNick("genious");
    }
}
```
- 위 코드를 실행 시 RuntimeExceiption이 발생한다.
- 위 코드에서 RuntimeExceiption을 Exception으로 변경하면 컴파일 에러가 발생하며, 해당 부분을 아래처럼 수정해 주어야 정상실행이 가능하다.

```
class FoolException extends Exception {
}

public class Sample {
    public void sayNick(String nick) {
        try {
            if("fool".equals(nick)) {
                throw new FoolException();
            }
            System.out.println("당신의 별명은 "+nick+" 입니다.");
        }catch(FoolException e) {
            System.err.println("FoolException이 발생했습니다.");
        }
    }

    public static void main(String[] args) {
        Sample sample = new Sample();
        sample.sayNick("fool");
        sample.sayNick("genious");
    }
}
```

#### 예외 던지기 (throws)
- 메서드 내에서 예외를 처리하지 않고 메서드를 호출한 곳에서 예외를 처리하도록 하는 방법
- 메서드 뒤에 throws [예외명] 을 입력하여 사용한다.
- __예외 처리를 어디서 하느냐에 따라 프로그램의 수행 여부가 변경되므로 Exception의 위치는 대단히 중요하다.__ 

```
class FoolException extends Exception {
}

public class Sample {
    public void sayNick(String nick) throws FoolException {
        if("fool".equals(nick)) {
            throw new FoolException();
        }
        System.out.println("당신의 별명은 "+nick+" 입니다.");
    }

    public static void main(String[] args) {
        Sample sample = new Sample();
        try {
            sample.sayNick("fool");
            sample.sayNick("genious");
        } catch (FoolException e) {
            System.err.println("FoolException이 발생했습니다.");
        }
    }
}
```

## 특수기호
- &nb_sp; : ” ” : 공백(스페이스 한 칸)을 의미
- &l_t; : 부등호(<)
- &g_t; : 부등호(>)
- &a_mp; : 앰퍼샌드(&) 기호
- &q_uot; : 쌍따옴표(“)
- &#_035; : sharp(#)
- &#_039; : 따옴표(‘)










