---
title: "@Bean@Component"
layout: post
category: Note
tags: [@Bean][@Component]
excerpt: "@Bean@Component"
author: Jeuun
---

@Bean,@Component (06/16)

# @Bean

@Bean 어노테이션의 경우 개발자가 직접 제어가 불가능한 외부 라이브러리 등을 Bean으로 만들려할 때 사용된다.<br>

<pre>
<code>
@Configuration
public class ApplicationConfig{
  @Bean
  public ArrayList<String> array(){
    return new ArrayList<String>();
  }
}
</code>
</pre>

# @Bean

 - 스프링 프레임 워크를 사용하면 많은 XML 설정 파일등을 작성하는 등 설정하는 방법이 어려운 편이기 때문에 보통 검색을 통해 설정 내용을 복사하거나, 
기존 설정파일들을 복붙하기 일수였다.
하지만 스프링 부트는 반복되는 개발환경 구축을 위한 코드작성등의 노력을 줄여주고 쉽고 빠르게 프로젝트를 설정할 수 있도록 도와준다.

 - 매우 빠르게 모든 스프링 개발에 관한 경험에 광범위한 접근을 제공한다.
 
 - name이라는 값을 이용하면 자신이 원하는 id로 Bean을 등록할 수 있다.
 
# @Component

- 개발자가 직접 작성한 Class를 Bean으로 등록하기 위한 어노테이션이다.

- @Bean과는 다르게 @Component는 name이 아닌 value를 이용해 Bean의 이름을 지정한다. 

# @Autowired

- @Component를 사용한 Bean의 의존성 주입은 @AutoWired 어노테이션을 이용할 수 있다.

- @Autowired 어노테이션의 경우 형(타입)을 통해 해당 자리에 들어올 객체를 판별하여 주입해준다. 

 
 


    
