## 스프링 MVC 컨트롤러 
- client가 요청을 하면, @Controller에 진입하고, 컨트롤러는 요청에 대한 작업을 수행하고, 뷰쪽으로 데이터를 전달한다.

### 컨트롤러 클래스 제작 순서
- @Controller를 이용해서 클래스를 생성한다.
- @RequestMapping을 이용해, view의 요청 경로 지정한다.
- 요청 처리 메소드(로직) 구현한다.
- 뷰 이름 리턴한다.

```
@Controller // 컨트롤러 지정 
public class HomeController { 

  // 뷰의 요청 경로 지정 
  @RequestMapping(value = "/", method = RequestMethod.GET) 
  public String home(Locale locale, Model model) { 
  
    // 로직 수행 
    logger.info("Welcome home! The client locale is {}.", locale); 
    Date date = new Date(); 
    DateFormat dateFormat = DateFormat.getDateTimeInstance(DateFormat.LONG, DateFormat.LONG, locale); 
    String formattedDate = dateFormat.format(date); 

    // Model 객체를 이용해서, view로 Data 전달 
    model.addAttribute("serverTime", formattedDate ); 

    // 뷰 파일 리턴
    return "home";  
  } 
}
```

### View의 요청 경로 설정하기
- 어노테이션을 사용하여 view 폴더안의 내가 목표로 하는 view의 경로(path)를 넣는다.
- 예를 들어, 경로가 /board/view 경로에 있을 경우 아래와 같이 작성한다.
- 리턴값도 똑같이 작성한다.
```
@Requestmapping("/board/view);

return "/board/view";
```

### Model 객체 사용법
- Model 객체를 파라미터로 받아서 데이터를 뷰로 넘길 수 있다.
- addAttribute를 사용하면 데이터를 뷰로 넘겨주고, 뷰에서는 ${}를 통해 값을 받을 수 있다.

```
@RequestMapping("/board/view")
public String view(Model model) {

  // 데이터만 설정 가능 (변수이름, 변수에 넣을 데이터 값)
  model.addAttribute("id", "abc");

  return "/board/view";
  
  
// 뷰 페이지
<body>
  <h1> view.jsp <h1>
  <p> 당신의 아이디는 ${id} 입니다. <p>
</body>
```

### ModelAndView 














