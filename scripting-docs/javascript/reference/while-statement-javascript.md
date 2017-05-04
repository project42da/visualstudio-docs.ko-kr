---
title: "while 문(JavaScript) | Microsoft Docs"
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
  - "while_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "루프 구조, while 문"
  - "while 문"
ms.assetid: d63777cf-0e1a-4555-8d3a-334381001f48
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# while 문(JavaScript)
지정된 조건이 `false`일 때까지 문 또는 일련의 문을 실행합니다.  
  
## 구문  
  
```  
while (expression) {  
    statements  
}   
```  
  
## 매개 변수  
 `expression`  
 필수 요소.  루프를 반복하기 전마다 점검하는 부울 식입니다.  `expression`이 `true`이면 루프가 실행됩니다.  `expression`이 `false`이면 루프가 종료됩니다.  
  
 `statements`  
 선택 사항입니다.  `expression`이 `true`인 경우 실행할 하나 이상의 문입니다.  
  
## 설명  
 `while` 문은 루프가 처음 실행되기 전에 `expression`을 확인합니다.  이 때 `expression`이 `false`이면 루프가 실행되지 않습니다.  
  
## 예제  
 다음 예제는 `while` 문의 사용 예를 보여 줍니다.  
  
```javascript  
var i = 0;  
var j = 10;  
while (i < 100) {  
    if (i == j)  
        break;  
    i++;  
}  
document.write(i);  
  
// Output: 10  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [continue 문](../../javascript/reference/continue-statement-javascript.md)   
 [do...while 문](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [for...in 문](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)