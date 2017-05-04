---
title: "논리곱 연산자(&amp;&amp;)(JavaScript) | Microsoft Docs"
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
  - "&&"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "&amp;&amp; 연산자"
  - "논리곱 연산자"
ms.assetid: 4714dea9-1999-444a-8acd-72f0851e4f65
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 논리곱 연산자(&amp;&amp;)(JavaScript)
두 식의 논리곱 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = expression1 && expression2   
```  
  
## 매개 변수  
 `result`  
 모든 변수입니다.  
  
 `expression1`  
 임의의 식입니다.  
  
 `expression2`  
 임의의 식입니다.  
  
## 설명  
 `expression1`이 `false`로 평가되는 경우 `result`는 `expression1`입니다.  그렇지 않으면 `result`가 `expression2`입니다.  따라서 두 피연산자 모두 true인 경우 연산은 `true`를 반환하고 그러지 않은 경우 `false`를 반환합니다.  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 부울이 아닌 값을 부울 값으로 변환하는 데 다음과 같은 규칙을 사용합니다.  
  
-   모든 개체는 `true`인 것으로 간주됩니다.  
  
-   문자열은 비어 있는 경우 `false`인 것으로 간주됩니다.  
  
-   `null` 및 `undefined`는 `false`인 것으로 간주됩니다.  
  
-   숫자는 0인 경우 `false`입니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)