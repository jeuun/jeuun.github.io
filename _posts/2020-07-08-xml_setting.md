---
title: "xml_setting"
layout: post
category: Spring_MVC
tags: [xml_setting]
excerpt: "xml_setting"
author: Jeuun
---
xml_setting (07/08)

# web.xml 설정
- DispatcherServlet 클래스를 Spring에서 제공하는 클래스로 설정한다. 
```java
<servlet>
	<servlet-name>appServlet</servlet-name>
	<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
	<load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
	<servlet-name>appServlet</servlet-name>
	<url-pattern>/</url-pattern>
</servlet-mapping>
```

# ApplicationContext 설정
- Spring MVC로 만든 웹 애플리케이션에 대한 설정을 하는 파일 
```java
<servlet>
	<servlet-name>appServlet</servlet-name>
	<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
	<init-param>
		<param-name>contextConfigLocation</param-name>
		<param-value>/WEB-INF/config/servlet-context.xml</param-value>
	</init-param>
	<load-on-startup>1</load-on-startup>
</servlet>
```

# RootContext 파일 설정
- Spring MVC 프로젝트 수행 시 사용할 Bean들을 정의하는 파일
```java
<context-param>
	<param-name>contextConfigLocation</param-name>
	<param-value>/WEB-INF/config/root-context.xml</param-value>
</context-param>

<listener>
	<listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener>
```

# 파라미터 필터 설정
파라미터에 한글이 있을 경우 

