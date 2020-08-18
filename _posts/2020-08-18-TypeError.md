---
title: "TypeError"
layout: post
category: Error
tags: [Error]
excerpt: "TypeError"
author: Jeuun
---

# TypeError

- TypeError 발생시 String일 경우

  - vo
  ```java
  private String boardSeq;
  ```
  
  - jsp
  ```java
  <input name="boardSeq" id="boardSeq"/>
  ```

  공백을 허용함. 

- int 타입일 경우

  - vo
  ```java
  private int boardSeq;
  ```

  - jsp
  ```java
  <input name="boardSeq" id="boardSeq" value="0"/>
  ```

  int 타입은 공백을 허용하지 않음으로 value 값을 지정해 준다.
