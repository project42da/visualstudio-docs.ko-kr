---
title: "빼기 연산자(-)(JavaScript) | Microsoft Docs"
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
  - "-"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "- 연산자"
  - "- 연산자, - 연산자 정보"
  - "산술 연산자, 빼기"
  - "부정 연산자"
  - "연산자, 빼기"
  - "빼기 연산자, 구문"
ms.assetid: cd0681d3-15cd-49fe-b4dd-e087de55d778
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 빼기 연산자(-)(JavaScript)
하나의 식의 값에서 다른 식의 값을 빼거나 단일 식을 음수화합니다.  
  
## 구문  
  
```  
  
result = number1 - number2;  
  
```  
  
## 매개 변수  
 *결과*  
 임의의 숫자 변수입니다.  
  
 `number`  
 임의의 숫자 식입니다.  
  
 `number1`  
 임의의 숫자 식입니다.  
  
 `number2`  
 임의의 숫자 식입니다.  
  
## 설명  
 구문 1에서는 **\-** 연산자가 두 수의 차이를 구하는 산술 빼기 연산자로 사용되었고  구문 2에서는 **\-** 연산자가 식의 음수 값을 나타내는 단항 부정 연산자로 사용되었습니다.  
  
 구문 2는 다른 단항 연산자와 마찬가지로 다음과 같이 계산됩니다.  
  
-   undefined 또는 `null` 식에 적용되면 런타임 오류가 일어납니다.  
  
-   개체를 문자열로 변환합니다.  
  
-   가능한 경우 문자열이 숫자로 변환됩니다.  변환되지 않으면 런타임 오류가 발생합니다.  
  
-   부울 값은 숫자로 처리됩니다\(false인 경우 0, true인 경우 1\).  
  
 연산자는 결과 숫자에 적용됩니다.  구문 2에서 결과 값이 0이 아니면 *result*는 결과 값의 부호를 반대로 바꾼 것과 같습니다.  결과 값이 0이면 *result*도 0이 됩니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [빼기 할당 연산자\(\-\=\)](../../javascript/reference/subtraction-assignment-operator-decrement-equal-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)