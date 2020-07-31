---
title: "filter,interceptor,AOP"
layout: post
category: Note
tags: [filter,interceptor,AOP]
excerpt: "filter_interceptor_AOP"
author: Jeuun
---
filter,interceptor,AOP (07/31)

- 프로그램의 흐름의 앞이나 뒤에 공통적인 처리를 추가할 수 있는 방법이 있다.
- filter, interceptor, AOP 를 사용할 수 있다.

- 필터와 인터셉터는 적용 시점(실행되는 시점)이 다르다. 
- 필터는 스프링 프레임웍과는 무관하게 지정된 자원에 대해 동작한다.
- 스프링은 Dispatcher 서블릿으로 부터 시작됨으로 필터는 스프링 컨텍스트의 바깥에 존재하게 된다.

# filter
- Servlet에서 처리하기 전후를 다룰수 있다.\
- 광범위하다.

# interceptor
- 스프링의 Dispatcher 서블릿이 컨트롤러를 호출할 때 전, 후에 끼어든다.
- 그러므로 스프링 컨텍스트 내부에 존재하게 된다. 
- 여러개를 사용할 수 있다.
- 주로 사용하는 곳은 로그인 체크, 권한 체크, 프로그램 실행시간 계산작업 로그처리 등에 많이 사용된다.

- 특성 시점에 동작하는 네 개의 메소드 구현
1. preHandle() 
  -- 컨트롤러 메소드 실행 직전 수행, true를 반환하면 계속 진행이 되고 false를 리턴하면 실행 체인이 중지되고 반환된다. 
2. postHandle()
  -- 컨트롤러 메소드 실행 직후에 실행된다. 
  -- View 페이지 렌더링 전에 실행된다.
3. afterCompletion()
  -- View 페이지가 렌더링 되고 난 후에 실행된다.
4. afterConcurrentHandlingStarted()
  -- postHandle와 afterCompletion은 실행되지 않고, 이 메소드가 실행된다.
  
# AOP (Aspect Oriented Programming) : 관점 지향 프로그래밍
- 어떤 로직을 기준으로 핵심적인 관점, 부가적인 관점으로 나누어서 보고 그 관점을 기준으로 각각 모듈화하겠다는 것이다.
- 여기서 모듈화란 어떤 공통된 로직이나 기능을 하나의 단위로 묶는 것을 말한다.
- 기능을 핵심 비지니스 로직과 공통 모듈로 구분하고, 핵심 로직에 영향을 미치지 않고, 사이사이에 공통 모듈을 효과적으로 잘 끼워넣도록 하는 개발 방법이다.
- 공통 모듈을 만든 후에 코드 밖에서 이 모듈을 비지니스 로직에 삽입하는 것이 바로 AOP 적인 개발이다.
- 코드 밖에서 설정된다는 것이 핵심이다.

- 사용 예
  - 간단한 메소드 검사.
  - 트랜잭션 처리
  - 예외 반환
  - 아키텍쳐 검증



