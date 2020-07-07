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
