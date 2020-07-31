---
title: "ModelAttribute"
layout: post
category: Note
tags: [ModelAttribute]
excerpt: "ModelAttribute"
author: Jeuun
---
ModelAttribute (07/06)

# ModelAttribute

1. 모델에 담아서 jsp에서 사용
2. 요청 파라미터로 넘어온 값들을 메서드 파라미터에 있는 객체(vo)에 바인딩 시켜준다.
3. @RequestParam 과는 다르게 검증(Validation)을 실시해준다.

- 주소에 값이 들어갈때 주소창으로 /search?age="나이" 
vo안에 만약 age가 int로 되어있을때 
@RequestParam int age
HTTP 400 - Bad Request에러를 클라이언트에 던진다.

- HttpServlet과 @RequestParam 은 1:1 매핑된다.

- 여러개의 요청 파라미터를 한번에 바인딩 시키기 위한 것이 커맨드 객체 
- 커맨드 객체의 정의가 폼안에 input이나 textarea등 name안에 있는 키값을 객체의 프로퍼티로 가지고, setter 메서드가 존재하면 커맨드 객체

-- 추가 (07/31)
- 메소드의 매개변수로 선언
  - 스프링 컨테이너가 생성하는 Command 객체의 이름은 클래스 이름의 첫 글자를 소문자로 변경한 이름이 자동으로 설정된다. (ex DataBean -> dataBean)
  - 이름을 변경하고 싶다면 @ModelAttribute("이름")으로 사용한다.

- 메소드에 선언
  - View에서 사용할 데이터를 설정하는 용도로 사용
  - @ModelAttribute가 설정된 메소드는 @RequestMapping이 적용된 메소드보다 먼저 호출
  - @ModelAttribute 메소드 실행 결과로 리턴되는 객체는 자동으로 Model에 저장
  - @modelAttribute 메소드 실행 결과로 리턴된 객체를 View 페이지에서 사용 가능
  
- 메소드에 선언되었을 경우 작동 방식
```java
@RequestMapping(value = "getBoardList.do")
public String getBoardList(Model model){
    model.addAttribute("post", new Post());
    return "boardList";
}

@ModelAttribute("commonCodeMap")
public Map<String, String> commonCodeMap(){
    Map<String, String> commonCodeMap = new HashMap<>();
    commonCodeMap.put("code1", "codeValue1");
    commonCodeMap.put("code2", "codeValue2");
    return commonCodeMap;
}
```
1. 클라이언트 getBoardList.do 요청
2. @ModelAttribute가 설정된 commonCodeMap 실행, return된 값 Model객체에 저장
3. 이 후 getBoardList() 메소드 실행
4. boardList 뷰가 띄어지면 뷰에서는 post와, commonCodeMap attribute를 사용할 수 있게 된다. (즉, Model 객체에 두 개의 attribute가 저장됨)

- 만약 모든 뷰에 특정 code를 갖고있어야 한다라고 하면 @ModelAttribute가 붙은 메소드에 code를 리턴하는 클래스를 만든 후 , 
모든 Controller에서 이 클래스를 상속받으면 반복적인 코딩을 하지않고도, view에서 code를 꺼내쓸 수 있게 된다.

참고 :https://cornswrold.tistory.com/316
  
  
