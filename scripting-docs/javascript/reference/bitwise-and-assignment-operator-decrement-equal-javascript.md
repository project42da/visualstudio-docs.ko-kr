---
title: "비트 논리곱 할당 연산자(&amp;=)(JavaScript) | Microsoft Docs"
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
  - "&="
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "&= 연산자"
  - "대입 연산자, 비트[JavaScript]"
  - "AND 연산자"
  - "비트 연산자, AND 연산자"
ms.assetid: e7e2eabb-4fc1-4fdc-9dd8-1e6d715371fa
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 비트 논리곱 할당 연산자(&amp;=)(JavaScript)
변수 값과 식의 값에 대한 비트 AND 연산의 결과를 설정합니다.  변수와 식은 32비트 정수로 처리됩니다.  
  
## 구문  
  
```  
  
result &= expression  
```  
  
## 매개 변수  
 `result`  
 임의의 변수입니다.  
  
 `expression`  
 임의의 식입니다.  
  
## 설명  
 이 연산자를 사용하는 것은 다음을 지정하는 것과 동일합니다.  
  
```javascript  
result = result & expression  
```  
  
 [비트 논리곱 연산자\(&\)](../../javascript/reference/bitwise-and-operator-decrement-javascript.md)는 `result` 및 `expression` 값의 이진 표현에 대한 비트 AND 연산을 수행합니다.  이 연산 결과는 다음과 같습니다.  
  
```javascript  
// 9 is 00000000000000000000000000001001  
var expr1 = 9;  
  
// 5 is 00000000000000000000000000000101  
var expr2 = 5;  
  
// 1 is 00000000000000000000000000000001  
expr1 &= expr2;  
  
document.write(expr1);  
  
```  
  
 두 식의 특정 자릿수가 모두 1이면 해당 자릿수의 결과 값은 1이 됩니다.  그렇지 않으면 해당 자릿수의 결과 값은 0이 됩니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [비트 논리곱 연산자\(&\)](../../javascript/reference/bitwise-and-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)