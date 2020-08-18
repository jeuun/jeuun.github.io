---
title: "controller 코드 정리"
layout: post
category: Note
tags: [Note]
excerpt: "controller 코드 정리"
author: Jeuun
---

# controller코드정리 - @ModelAttribute, @RequestParam

- controller코드정리 - @ModelAttribute, @RequestParam

- xml
boardVo는 alias로 board 설정
```java
 <select id="findBoard" resultType="board" parameterType="board">
   	 <![CDATA[
        SELECT 
        	* 
        FROM 
        	BOARD 
        WHERE 
        	SEQ = #{Seq}
        ]]>
    </select>
```
resultType="board"으로 vo 타입을 설정했다.

- controller
```java
	@RequestMapping(value="/view")
	public String view(
			@RequestParam("boardSeq") int boardSeq
			, Model model
			) {
		BoardVo vo = boardService.findBoard(boardSeq);
		model.addAttribute("board", vo);
		return "board/view.core";
	}
```

이렇게 하거나 
```java
@RequestMapping(value="/udt", method = RequestMethod.GET)
	public String udtpage(
			@ModelAttribute("searchVo") MecBoardVo searchVo
			, @RequestParam("boardSeq") int boardSeq
			, Model model
			) {
		BoardVo vo = boardService.findBoard(boardSeq);
		model.addAttribute("board", vo);
		return "board/udt.core";
	}
  ```
  - 굳이 @ModelAttribute 설정후 @RequestParam으로 Seq를 선언 XXX
  
- @ModelAttribute만 선언 후 Seq를 꺼내 쓰는 방법으로 변경
 
 ```java
BoardVo vo = boardService.findBoard(searchVo.getBoardSeq());
```
  
