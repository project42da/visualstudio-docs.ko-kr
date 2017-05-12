---
title: "if...else 문(JavaScript) | Microsoft Docs"
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
  - "else_JavaScriptKeyword"
  - "if_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "if 문, if...else"
  - "루프 구조, if...else 문"
ms.assetid: dfbe86e8-9c1e-4ef5-bb9c-7d1db7ce2506
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# if...else 문(JavaScript)
식의 값에 따라 문 그룹을 조건부로 실행합니다.  
  
## 구문  
  
```  
if (condition1) {  
    statement1  
}  
[else if (condition2) {  
    statement2  
}]  
[else {  
    statement3]   
}]  
```  
  
## 매개 변수  
 `condition1`  
 필수 요소.  부울 식입니다.  `condition1`이 `null` 또는 `undefined`이면 `condition1`은 `false`로 처리됩니다.  
  
 `statement1`  
 선택 사항입니다.  `condition1`이 **true**일 경우 실행되는 문입니다.  복합 문도 가능합니다.  
  
 `condition2`  
 확인할 조건입니다.  
  
 `statement2`  
 선택 사항입니다.  `condition2`가 `true`일 경우 실행되는 문입니다.  복합 문도 가능합니다.  
  
 `statement3`  
 `condition1`과 `condition2`가 모두 `false`이면 이 문이 실행됩니다.  
  
## 예제  
 다음 코드에서는 `if`, `if else` 및 `else`를 사용하는 방법을 보여 줍니다.  
  
 더 명확하게 표시하고 부주의로 인한 오류를 방지하려면 `statement1` 및 `statement2`를 중괄호\({}\)로 묶는 것이 좋습니다.  
  
```javascript  
var z = 3;  
if (x == 5) {  
    z = 10;  
}  
else if (x == 10) {  
    z = 15;  
}  
else {  
    z = 20;  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [조건부\(삼항\) 연산자\(?:\)](../../javascript/reference/conditional-ternary-operator-decrement-javascript.md)