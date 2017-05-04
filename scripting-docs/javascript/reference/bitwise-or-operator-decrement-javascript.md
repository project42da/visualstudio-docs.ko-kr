---
title: "비트 논리합 연산자(|)(JavaScript) | Microsoft Docs"
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
  - "|"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "| 연산자"
  - "비트 연산자, Or 연산자"
  - "Or 연산자"
ms.assetid: ffc8f758-3151-478e-bafb-fc78f1c469a0
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 비트 논리합 연산자(|)(JavaScript)
두 식에 비트 OR 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = expression1 | expression2  
```  
  
## 매개 변수  
 *결과*  
 임의의 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## 설명  
 이          **&#124;** 연산자는 두 식의 이진 값에 대한 비트 OR 연산을 수행합니다.  이 연산의 결과는 다음과 같습니다.  
  
```javascript  
0101   (expression1)  
1100   (expression2)  
----  
1101   (result)  
```  
  
 두 식의 특정 자릿수 중 하나가 1이면 해당 자릿수의 결과 값은 1이 되고,  그렇지 않으면 해당 자릿수의 결과 값은 0이 됩니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [비트 논리합 할당 연산자\(&#124;\=\)](../../javascript/reference/bitwise-or-assignment-operator-decrement-equal-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)