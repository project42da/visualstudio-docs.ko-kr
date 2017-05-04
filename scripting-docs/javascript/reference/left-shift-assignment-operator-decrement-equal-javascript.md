---
title: "왼쪽 시프트 대입 연산자(&lt;&lt;=)(JavaScript) | Microsoft Docs"
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
  - "<<="
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "<<= 연산자[JavaScript]"
  - "왼쪽 시프트 대입 연산자(<<=)[JavaScript]"
  - "왼쪽 시프트 연산자[JavaScript]"
  - "대입 연산자, JavaScript"
ms.assetid: 9f30ff46-48cc-4931-b260-edef31ff0076
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 왼쪽 시프트 대입 연산자(&lt;&lt;=)(JavaScript)
지정된 수의 비트를 왼쪽으로 이동하고 결과를 `result`에 할당합니다.  연산으로 비워진 비트는 0으로 채워집니다.  
  
## 구문  
  
```  
  
result <<= expression  
```  
  
## 매개 변수  
 `result`  
 임의의 변수입니다.  
  
 `expression`  
 이동할 비트 수입니다.  
  
## 설명  
 `<<=` 연산자를 사용하는 것은 `result = result << expression`을 지정하는 것과 동일합니다.  
  
 다음 예제에서는 `<<=` 연산자를 사용하는 방법을 보여 줍니다.  
  
```javascript  
// 14 is 00000000000000000000000000001110  
var temp = 14;  
temp <<= 2;   
document.write(temp);  
// 56 is 00000000000000000000000000111000  
Output: 56  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [비트 왼쪽 시프트 연산자\(\<\<\)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [비트 오른쪽 시프트 연산자\(\>\>\)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [부호 없는 오른쪽 시프트 연산자\(\>\>\>\)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)