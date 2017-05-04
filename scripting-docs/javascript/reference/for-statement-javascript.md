---
title: "for 문(JavaScript) | Microsoft Docs"
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
  - "for_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "루프 구조, for 문"
ms.assetid: bae0ec40-152e-43f3-969b-3696489ec5c4
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# for 문(JavaScript)
지정한 조건이 true인 동안 문 블록을 실행합니다.  
  
## 구문  
  
```  
for ([initialization]; [test]; [increment])  
   statement   
```  
  
## 매개 변수  
 `initialization`  
 선택 사항입니다.  식입니다.  이 식은 루프가 실행되기 전에 한 번만 실행됩니다.  
  
 `test`  
 선택 사항입니다.  부울 식입니다.  `test`가 `true`이면 `statement`가 실행됩니다.  `test`가 `false`이면 루프가 종료됩니다.  
  
 `increment`  
 선택 사항입니다.  식입니다.  증분식은 모든 루프의 끝에서 실행됩니다.  
  
 `statement`  
 선택 사항입니다.  `test`가 **true**인 경우 실행할 하나 이상의 문입니다.  복합 문도 가능합니다.  
  
## 설명  
 `for` 루프는 보통 루프를 지정한 수만큼 실행할 경우에 사용합니다.  `for` 루프를 사용하면 손쉽게 배열을 반복하고 순차적으로 처리할 수 있습니다.  
  
 루프를 실행하기 전에 조건식을 테스트하므로 `for` 문은 0번 이상 실행됩니다.  
  
 `for` 루프 문 블록의 임의 줄에서 `break` 문을 사용하여 루프를 종료하거나, `continue` 문을 사용하여 제어를 루프의 다음 반복으로 이동할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `for` 문이 포함된 문을 다음과 같이 실행합니다.  
  
-   먼저 `i` 변수의 초기 값이 계산됩니다.  
  
-   그런 다음 `i`의 값이 9보다 작거나 같으면 `document.write` 문이 실행되고 `i`가 다시 계산됩니다.  
  
-   `i`가 9보다 크면 조건이 false가 되고 제어가 루프 밖으로 이동합니다.  
  
```javascript  
// i is set to 0 at the start and is incremented by 1 at the  
// end of each iteration.  
// The loop terminates when i is not less than or equal to  
// 9 before a loop iteration.  
for (var i = 0; i <= 9; i++) {  
   document.write (i);  
   document.write (" ");  
}  
  
// Output: 0 1 2 3 4 5 6 7 8 9  
```  
  
## 예제  
 `for` 문의 모든 식은 선택 사항입니다.  다음 예제에서는 `for` 문이 무한 루프를 만들고, `break` 문을 사용하여 루프를 종료합니다.  
  
```javascript  
var j = 0;  
for (;;) {  
    if (j >= 5) {  
        break;  
    }  
    j++;  
    document.write (j + " ");  
}  
  
// Output: 1 2 3 4 5  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [for...in 문](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)