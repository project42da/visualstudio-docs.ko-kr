---
title: "비트 논리곱 연산자(&amp;)(JavaScript) | Microsoft Docs"
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
  - "&"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "대입 연산자, 비트[JavaScript]"
  - "& 연산자, & 연산자 정보"
  - "AND 연산자"
  - "& 연산자"
  - "비트 연산자, AND 연산자"
  - "& 연산자, 비트 연산자"
ms.assetid: a8c17a55-2599-4518-98d7-671699f4d5f3
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 비트 논리곱 연산자(&amp;)(JavaScript)
두 32비트 식에 대한 비트 AND 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = expression1 & expression2  
```  
  
## 매개 변수  
 `result`  
 연산의 결과입니다.  
  
 `expression1`  
 임의의 식입니다.  
  
 `expression2`  
 임의의 식입니다.  
  
## 설명  
 `&`는 두 32비트 식의 각 비트에 대한 비트 AND 연산을 수행합니다.  두 비트 모두 1이면 결과는 1이 됩니다.  그렇지 않으면, 결과는 0이 됩니다.  
  
|Bit1|Bit2|AND 연산 값|  
|----------|----------|--------------|  
|0|0|0|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
  
 다음 예제에서는 `&` 연산자를 사용하는 방법을 보여 줍니다.  
  
```javascript  
// 9 is 00000000000000000000000000001001  
var expr1 = 9;  
  
// 5 is 00000000000000000000000000000101  
var expr2 = 5;  
  
// 1 is 00000000000000000000000000000001  
var result = expr1 & expr2;  
  
document.write(result);  
// Output: 1  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [비트 논리곱 할당 연산자\(&\=\)](../../javascript/reference/bitwise-and-assignment-operator-decrement-equal-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)