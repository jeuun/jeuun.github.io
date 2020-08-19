---
title: "isNotEmpty,iterate"
layout: post
category: Note
tags: [Note]
excerpt: "isNotEmpty,iterate"
author: Jeuun
---

# isNotEmpty

- isNotEmpty
  isNotEmpty는 값이 있을때만 실행되는 동적 쿼리이다. (property의 값이 비어있지 않을때)
  
  ```java
    <isNotEmpty property="position" prepend="AND">
			BOARD = #BOARD#
	  </isNotEmpty>
```
  - property : 있는지 없는지를 판단할 프로퍼티 이름
  - prepared : 있을 때 조건 앞에 붙는 논리 키워드 (AND, OR 등)

# iterate

- iterate
iterate는 해당 객체가 종료될때까지 반복한다.

```java
		<isNotEmpty property="boardList">
			AND board IN 
			<iterate property="boardList" open="(" close=")" conjunction=",">
				#boardList[]#
			</iterate>
		</isNotEmpty>
```
  - property = boardList
    - boardList는 배열변수이다.
  - open=”(“
    - iterate 쿼리 시작부분에 들어갈 기호를 ( 로 설정
  -  close=”)”
    - iterate 쿼리가 끝날 때 들어갈 기호를 )로 설정
  - conjunction=","
    - iterate가 종료되면 그 뒤에 추가 입력
    
   - 실행 결과
   ```java
   AND board IN (a, b, c)
   ```
