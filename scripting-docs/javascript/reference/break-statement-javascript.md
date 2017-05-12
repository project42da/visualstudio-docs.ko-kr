---
title: "break 문(JavaScript) | Microsoft Docs"
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
  - "break_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "break 문"
  - "do...while 문"
ms.assetid: 5be0f2a8-5fe7-4a6c-89af-ca20a925ce87
caps.latest.revision: 23
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 23
---
# break 문(JavaScript)
현재 루프를 종료하거나 `label`로 연결된 경우에는 연결된 문을 종료합니다.  
  
## 구문  
  
```  
break [label];  
```  
  
## 설명  
 선택적인 `label` 인수는 중단할 문의 레이블을 지정합니다.  
  
 일반적으로 `break` 문은 `switch` 문에서 사용하고 `while`, `for`, `for...in` 또는 `do...while` 루프에서 사용됩니다.  `label` 인수는 `switch` 문에서 가장 많이 사용하지만 단순 문이나 복합 문에서 모두 사용할 수 있습니다.  
  
 `break` 문을 실행하면 현재 루프 또는 문이 종료되고 바로 다음 문의 스크립트 실행이 시작됩니다.  
  
## 예제  
 이 예제에서는 1부터 99까지 세는 카운터가 설정되지만 `break` 문으로 인해 14까지 센 다음 루프가 종료됩니다.  
  
```javascript  
for (var i = 1; i < 100; i++) {  
    if (i == 15) {  
        break;  
    }  
    document.write (i);  
    document.write (" ");  
}  
  
// Output: 1234567891011121314  
```  
  
 다음 코드에서 `break` 문은 `Inner:` 문 다음에 오는 `for` 루프를 참조합니다.  `j`가 24이면 `break` 문 때문에 프로그램 흐름이 해당 루프에서 빠져 나옵니다.  21부터 23까지의 숫자가 각 줄에 인쇄됩니다.  
  
```javascript  
Outer:  
for (var i = 1; i <= 10; i++) {  
    document.write ("<br />");  
    document.write ("i: " + i);  
    document.write (" j: ");  
Inner:  
    for (var j = 21; j <= 30; j++) {  
        if (j == 24) {  
            break Inner;  
        }  
        document.write (j + " ");  
    }  
}  
  
// Output:   
// i: 1 j: 21 22 23   
// i: 2 j: 21 22 23   
// i: 3 j: 21 22 23   
// i: 4 j: 21 22 23   
// i: 5 j: 21 22 23   
// i: 6 j: 21 22 23   
// i: 7 j: 21 22 23   
// i: 8 j: 21 22 23   
// i: 9 j: 21 22 23   
// i: 10 j: 21 22 23  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [continue 문](../../javascript/reference/continue-statement-javascript.md)   
 [do...while 문](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [for...in 문](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [Labeled 문](../../javascript/reference/labeled-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)