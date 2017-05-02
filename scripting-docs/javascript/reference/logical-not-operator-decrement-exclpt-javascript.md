---
title: "논리 부정 연산자(!)(JavaScript) | Microsoft Docs"
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
  - "!"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "! operator"
  - "! operator, ! 연산자 정보"
  - "논리 부정 연산자"
ms.assetid: 68c3dc71-ae95-4293-9155-67405846d71d
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# 논리 부정 연산자(!)(JavaScript)
식에 논리 부정 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = !expression  
```  
  
## 매개 변수  
 *결과*  
 임의의 변수입니다.  
  
 *expression*  
 임의의 식입니다.  
  
## 설명  
 다음 표는 *result*가 결정되는 방법을 보여 줍니다.  
  
|`expression`의 값|`result`\(결과\)|  
|---------------------|--------------------|  
|True|False|  
|False|True|  
  
 **\!** 연산자와 같은 모든 단일 연산자는 다음과 같이 식을 계산합니다.  
  
-   undefined 또는 `null` 식에 적용되면 런타임 오류가 일어납니다.  
  
-   개체를 문자열로 변환합니다.  
  
-   가능한 경우 문자열이 숫자로 변환됩니다.  변환되지 않으면 런타임 오류가 발생합니다.  
  
-   부울 값은 숫자로 처리됩니다\(false인 경우 0, true인 경우 1\).  
  
 연산자는 결과 숫자에 적용됩니다.  
  
 **\!** 연산자의 경우 *expression*이 0이 아니면 *result*는 0이 됩니다.  *expression*이 0이면 *result*는 1이 됩니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [비트 논리 부정 연산자\(~\)](../../javascript/reference/bitwise-not-operator-decrement-tilde-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)