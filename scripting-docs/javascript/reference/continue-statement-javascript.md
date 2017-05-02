---
title: "continue 문(JavaScript) | Microsoft Docs"
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
  - "continue_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "continue 문"
  - "do...while 문"
  - "루프 구조, continue 문"
ms.assetid: f8a30d9f-e2de-4e1f-8668-4e4cf95f7df9
caps.latest.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 21
---
# continue 문(JavaScript)
현재 루프 반복을 중지하고 새로 반복을 시작합니다.  
  
## 구문  
  
```  
continue [label];  
```  
  
## 설명  
 선택적 `label` 인수는 `continue`가 적용되는 문을 지정합니다.  
  
 `continue` 문은 `while`, `do...while`, **for** 또는 `for...in` 루프 안에서만 사용할 수 있습니다.  `continue` 문을 실행하면 현재의 루프 반복이 중지되고 루프 시작 부분에서 프로그램 흐름이 계속 진행됩니다.  이때 다른 형식으로 된 루프에 다음과 같은 영향을 줍니다.  
  
-   `while`과 `do...while` 루프는 조건을 테스트하고 값이 true이면 루프를 다시 실행합니다.  
  
-   `for` 루프는 증가 식을 실행하고 테스트 식이 true이면 루프를 다시 실행합니다.  
  
-   `for...in` 루프는 지정한 변수의 다음 필드로 진행한 후 루프를 다시 실행합니다.  
  
## 예제  
 이 예제에서 루프는 1에서 9까지 반복합니다.  `continue`와 `for` 본문의 끝 사이에 있는 문은 `continue` 문이 `(i < 5)` 식과 함께 사용되기 때문에 건너뜁니다.  
  
```javascript  
for (var i = 1; i < 10; i++) {  
    if (i < 5) {  
        continue;  
    }  
    document.write (i);  
    document.write (" ");  
}  
  
// Output: 5 6 7 8 9  
```  
  
 다음 코드에서 `continue` 문은 앞에 `Inner:` 레이블이 오는 `for` 루프를 참조합니다.  `j`가 24이면 `continue` 문 때문에 `for` 루프가 다음 반복으로 이동합니다.  21부터 23, 25에서 30까지의 숫자가 각 줄에 인쇄됩니다.  
  
```javascript  
Outer:  
for (var i = 1; i <= 10; i++) {  
    document.write ("<br />");  
    document.write ("i: " + i);  
    document.write (" j: ");  
  
Inner:  
    for (var j = 21; j <= 30; j++) {  
        if (j == 24) {  
             continue Inner;  
        }  
        document.write (j + " ");  
    }  
}  
  
//Output:  
//i: 1 j: 21 22 23 25 26 27 28 29 30   
//i: 2 j: 21 22 23 25 26 27 28 29 30   
//i: 3 j: 21 22 23 25 26 27 28 29 30   
//i: 4 j: 21 22 23 25 26 27 28 29 30   
//i: 5 j: 21 22 23 25 26 27 28 29 30   
//i: 6 j: 21 22 23 25 26 27 28 29 30   
//i: 7 j: 21 22 23 25 26 27 28 29 30   
//i: 8 j: 21 22 23 25 26 27 28 29 30   
//i: 9 j: 21 22 23 25 26 27 28 29 30   
//i: 10 j: 21 22 23 25 26 27 28 29 30  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [do...while 문](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [for...in 문](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [Labeled 문](../../javascript/reference/labeled-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)