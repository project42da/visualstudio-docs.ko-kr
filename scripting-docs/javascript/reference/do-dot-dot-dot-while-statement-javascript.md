---
title: "do...while 문(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "do_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "do...while 문"
  - "루프 종료"
  - "루프 구조, do 및 do-while"
ms.assetid: 8b7782ba-fbad-48cd-9639-193566da6ae5
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# do...while 문(JavaScript)
문 블록을 한 번 실행한 후 조건식이 `false`가 될 때까지 루프를 반복 실행합니다.  
  
## 구문  
  
```  
do {  
    statement  
}  
while (expression) ;   
```  
  
## 매개 변수  
 `statement`  
 필수 요소.  `expression`이 `true`일 경우 실행되는 문입니다.  복합 문도 가능합니다.  
  
 `expression`  
 필수 요소.  `true` 또는 `false`에 해당하는 부울 값으로 강제 변환할 수 있는 식입니다.  `expression`이 `true`이면 루프가 다시 실행됩니다.  `expression`이 `false`이면 루프가 종료됩니다.  
  
## 설명  
 `do...while` 루프는 `while` 문과 달리 조건식이 계산되기 전에 한 번 실행됩니다.  
  
 `do…while` 블록의 아무 줄에서나 `break` 문을 사용하여 프로그램 흐름을 루프에서 빠져 나오게 하거나 `continue` 문을 사용하여 `while` 식으로 직접 이동할 수 있습니다.  
  
## 예제  
 다음 예제에서 `do...while` 루프의 문은 `i` 변수가 10보다 작은 동안에만 계속 실행됩니다.  
  
```javascript  
var i = 0;  
do {  
    document.write(i + " ");  
    i++;  
} while (i < 10);  
  
// Output: 0 1 2 3 4 5 6 7 8 9   
```  
  
## 예제  
 다음 예제에서는 조건이 충족되지 않았는데도 루프 내의 문이 한 번 실행됩니다.  
  
```javascript  
var i = 10;  
do {  
    document.write(i + " ");  
    i++;  
} while (i < 10);  
  
// Output: 10  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## 참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [continue 문](../../javascript/reference/continue-statement-javascript.md)   
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [for...in 문](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)   
 [Labeled 문](../../javascript/reference/labeled-statement-javascript.md)