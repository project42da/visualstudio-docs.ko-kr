---
title: "Labeled 문(JavaScript) | Microsoft Docs"
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
  - "labeled_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "continue 문"
  - "식별자, 문"
  - "labeled 문"
ms.assetid: 019f898e-9e27-4be4-a22f-c5927c7fcae2
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# Labeled 문(JavaScript)
문에 대한 식별자를 제공합니다.  
  
## 구문  
  
```  
  
      label :  
   statements   
```  
  
## 매개 변수  
 *label*  
 필수 요소.  labeled 문을 참조할 때 사용하는 고유 식별자입니다.  
  
 `statements`  
 선택 사항입니다.  *label*로 연결된 하나 이상의 문입니다.  
  
## 설명  
 레이블은 **break**와 **continue** 문에서 사용하여 **break**와 **continue**를 적용할 문을 지정합니다.  
  
## 예제  
 다음 코드에서 **continue** 문은 `Inner:` 문 다음에 오는 **for** 루프를 참조합니다.  `j`가 24이면 **continue** 문 때문에 **for** 루프가 다음 반복으로 이동합니다.  21부터 23, 25에서 30까지의 숫자가 각 줄에 인쇄됩니다.  
  
```javascript  
Outer:  
for (i = 1; i <= 10; i++) {  
   document.write ("<br />");  
   document.write ("i: " + i);  
   document.write (" j: ");  
  
Inner:  
   for (j = 21; j <= 30; j++) {  
      if (j == 24)  
          {  
          continue Inner;  
      }  
      document.write (j + " ");  
  }  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## 참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [continue 문](../../javascript/reference/continue-statement-javascript.md)