---
title: "Bitwise NOT 연산자(~)(JavaScript) | Microsoft Docs"
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
  - "~"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "비트 연산자, NOT 연산자"
  - "NOT 연산자"
ms.assetid: 39f92474-fe05-4a8b-9ad8-caca93f82bca
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# Bitwise NOT 연산자(~)(JavaScript)
식에 비트 부정 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = ~ expression  
```  
  
## 매개 변수  
 *결과*  
 임의의 변수입니다.  
  
 *expression*  
 임의의 식입니다.  
  
## 설명  
 `~` 연산자와 같은 모든 단일 연산자는 다음과 같이 식을 계산합니다.  
  
-   undefined 또는 `null` 식에 적용되면 런타임 오류가 일어납니다.  
  
-   개체를 문자열로 변환합니다.  
  
-   가능한 경우 문자열이 숫자로 변환됩니다.  변환되지 않으면 런타임 오류가 발생합니다.  
  
-   부울 값은 숫자로 처리됩니다\(false인 경우 0, true인 경우 1\).  
  
 연산자는 결과 숫자에 적용됩니다.  
  
 `~` 연산자는 식의 이진 값에 비트 부정 연산을 수행합니다.  
  
 식에서 1인 모든 숫자는 결과에서 0이 됩니다.  식에서 0인 모든 숫자는 결과에서 1이 됩니다.  
  
 다음 예제에서는 비트 NOT \(~\) 연산자의 사용법을 보여 줍니다.  
  
```  
var temp = ~5;  
```  
  
 다음 표에 표시된 대로 결과 값은 \-6입니다.  
  
|식|이진 값 \(2의 보수\)|10진 값|  
|-------|--------------------|-----------|  
|5|00000000 00000000 00000000 00000101|5|  
|~5|11111111 11111111 11111111 11111010|\-6|  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [논리 부정 연산자\(\!\)](../../javascript/reference/logical-not-operator-decrement-exclpt-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)