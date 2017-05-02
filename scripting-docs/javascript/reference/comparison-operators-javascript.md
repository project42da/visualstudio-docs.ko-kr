---
title: "비교 연산자(JavaScript) | Microsoft Docs"
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
  - "Comparison"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "비교 연산자, 스크립트"
  - "보다 큼 연산자"
  - "비교 연산자"
  - "크거나 같음 연산자"
  - "같지 않음 연산자"
  - "항등 연산자"
ms.assetid: 084f90f0-d010-47cf-96dd-13d637fc9b68
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 비교 연산자(JavaScript)
비교 결과를 나타내는 부울 값을 반환합니다.  
  
## 구문  
  
```  
  
expression1 comparisonoperator expression2  
```  
  
## 매개 변수  
 `expression1`  
 임의의 식입니다.  
  
 `comparisonoperator`  
 임의의 비교 연산자입니다.  
  
 `expression2`  
 임의의 식입니다.  
  
## 설명  
 문자열을 비교할 때 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 문자열 식의 유니코드 문자 값을 사용합니다.  
  
 아래에서는 `expression1` 및 `expression2`의 형식과 값에 따라 서로 다른 연산자 그룹이 동작하는 방식을 설명합니다.  
  
 관계형 연산자: `<`, `>`, `<=`, `>=`  
  
-   `expression1` 및 `expression2`를 모두 숫자로 변환하려고 시도합니다.  
  
-   두 식이 모두 문자열이면 문자열을 비교합니다.  
  
-   두 식 중 하나가 `NaN`이면 `false`를 반환합니다.  
  
-   음의 0은 양의 0과 같습니다.  
  
-   음의 무한대는 자신을 포함한 모든 숫자보다 작습니다.  
  
-   양의 무한대는 자신을 포함한 모든 숫자보다 큽니다.  
  
 같음 연산자: `==`, `!=`  
  
-   두 식의 형식이 다르면 문자열, 숫자 또는 부울 값으로 변환하려고 시도합니다.  
  
-   `NaN`은 자신을 포함한 모든 것과 같지 않습니다.  
  
-   음의 0은 양의 0과 같습니다.  
  
-   `null`은 `null` 및 `undefined`와 같습니다.  
  
-   문자열, 숫자, 개체 또는 부울 값이 동일한 경우 두 값은 동일하게 간주되며 형식이 다른 경우에는 이 형식 중의 하나로 강제 변환될 수 있습니다.  
  
-   그 외의 다른 경우에는 두 값이 다른 것으로 간주합니다.  
  
 항등 연산자: `===`, `!==`  
  
 이러한 연산자는 같음 연산자와 동일하게 동작하지만 형식 변환이 수행되지 않습니다.  두 식의 형식이 같지 않으면 이러한 식은 항상 `false`를 반환합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)