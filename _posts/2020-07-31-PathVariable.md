---
title: "PathVariable"
layout: post
category: Spring_MVC
tags: [PathVariable]
excerpt: "PathVariable"
author: Jeuun
---
@PathVariable (07/31)

# @PathVariable
- url 경로에 변수를 넣어주는 기능이다.

```java
@RequestMapping("/page/{var}")
  public String page(
    @PathVariable String var,
    @PathVariable @PathVariable pageType
  ){
  String returnUrl = "page1";
  
  return returnUrl;
  }
```

- RequestMapping의 URL 정의 부분과 Method 내의 Parameter 부분에 정의를 하여 사용이 가능하다.
정의를 해준 두 부분이 동일하게 선언 -> var로 되어야 한다.

- url에서 각 구분자에 들어오는 값을 처리해야 할 때 사용한다.

- 실제로 @RequestParam과 @PathVariable 모두 복합적으로 사용을 한다.
