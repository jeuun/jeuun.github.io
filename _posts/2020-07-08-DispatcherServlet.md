---
title: "DispatcherServlet"
layout: post
category: Spring_MVC
tags: [DispatcherServlet]
excerpt: "DispatcherServlet"
author: Jeuun
---
DispatcherServlet (07/08)

# 동작방식

![그림3](https://user-images.githubusercontent.com/57126028/86879037-3a0b6f00-c125-11ea-803f-86cb712ab4fb.jpg)

# DispatcherServlet
- Servlet/JSP 에서 사용자 요청이 발생하면 이 요청 정보를 해석하고 개발자가 만든 코드를 동작시키는 첫번째 서블릿이다. 
- Spring MVC는 DispatcherServlet을 확대하여 Spring Framework가 가지고 있는 기능을 사용할 수 있도록 이 클래스를 재정의 하고있다. 
- SpringMVC 프로젝트 설정에서 가장 먼저 해야하는 DispatcherServlet 클래스를 Spring MVC에거 재정의한 클래스로 설정하는 일 이다. 

# 설정방식
- Spring MVC프로젝트를 설정하는 방식은 XML을 이용하는 방법과 Java 코드를 활용하는 방법이 있다. 
- 두 방법 모두 설정 방법이 매우 유사하다.

# pom.xml
- pom.xml에 servlet-api, jsp-api, jstl, springWebMVC 라이브러리를 설정한다. 


