---
title: "checkbox value 및 c태그 사용"
layout: post
category: Note
tags: [checkbox value 및 c태그 사용]
excerpt: "checkbox value 및 c태그 사용"
author: Jeuun
---
checkbox value 및 c태그 사용 (10/08)

![image](https://user-images.githubusercontent.com/57126028/95402374-8051b380-094a-11eb-85ed-198b920e2606.png)<br>
1. fn:contains를 사용하여 문자열을 비교하여 checked를 줌.<br>

![image](https://user-images.githubusercontent.com/57126028/95402452-b42cd900-094a-11eb-8428-f176aa35bb47.png)<br>
2. fn:contains 속성으로 c문자열 비교시 c문자를 포함하는 다중값이 체크됨<br>

![image](https://user-images.githubusercontent.com/57126028/95402470-c3ac2200-094a-11eb-8e57-7ca1f2b25512.png)<br>
3. 다중값이 배열로 나온다는것을 알고 split을 사용하여 배열을 하나씩 출력한뒤 비교를 하려고 했지만 <br>
결과값은 결국 하나가 나오긴 했지만 배열 중 하나 값과 spring문자열과 비교를 하려고 해서 비교가 되지않아 checked를 하지 못함.<br>

![image](https://user-images.githubusercontent.com/57126028/95402576-0968ea80-094b-11eb-9ccd-ce6b8619f480.png)<br>
4. input으로 하기 전 c:set으로 ckecked라는 변수를 선언한 뒤, forTokens로 하나씩 꺼내 비교하여 같을시 checked변수에 checked의 값을 넣어줌. <br>

![image](https://user-images.githubusercontent.com/57126028/95402798-898f5000-094b-11eb-922b-48d568fb3d1b.png)<br>
- jsp를 java문 처럼 했을시 코드<br>





