---
title: "논리합 연산자(||)(JavaScript) | Microsoft Docs"
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
  - "||"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "|| 연산자"
  - "논리합 연산자"
ms.assetid: 95295331-6269-4311-8391-dc1c68e116ab
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# 논리합 연산자(||)(JavaScript)
두 식에 논리합 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = expression1 || expression2  
```  
  
## 매개 변수  
 *결과*  
 임의의 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## 설명  
 두 식 중 하나가 **True**이면 *result*는 **True**가 됩니다.  다음 표는 *result*가 결정되는 방법을 보여 줍니다.  
  
|`expression1`의 값|`expression2`의 값|`result`\(결과\)|  
|----------------------|----------------------|--------------------|  
|True|True|True|  
|True|False|True|  
|False|True|True|  
|False|False|False|  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 다음 규칙을 사용하여 부울 값이 아닌 값을 부울 값으로 변환합니다.  
  
-   모든 개체는 true인 것으로 간주합니다.  
  
-   문자열은 비어 있는 경우에만 false로 간주합니다.  
  
-   `null` 및 undefined는 false로 간주합니다.  
  
-   숫자는 0인 경우에만 false로 간주합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)