---
title: "비트 오른쪽 시프트 연산자(&gt;&gt;)(JavaScript) | Microsoft Docs"
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
  - ">>"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - ">> 연산자"
  - ">> 연산자, >> 연산자 정보"
  - ">> 연산자, 비트 세트"
  - "비트 연산자, 오른쪽 시프트 연산자"
ms.assetid: 89dc57e0-0b0d-49a4-a8ed-56d8bb20f3e3
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 비트 오른쪽 시프트 연산자(&gt;&gt;)(JavaScript)
부호를 유지하면서 식을 비트 단위로 오른쪽으로 이동합니다.  
  
## 구문  
  
```  
  
result = expression1 >> expression2  
```  
  
## 매개 변수  
 *결과*  
 임의의 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## 설명  
 \>\> 연산자는 *expression1*의 비트를 *expression2*에 지정된 비트 수만큼 오른쪽으로 이동합니다.  왼쪽에 생긴 공간은 *expression1*의 부호 비트로 채우고  오른쪽으로 밀려난 숫자는 버립니다.  예를 들어 다음 코드를 계산하면 \-14\(2의 보수 이진수 11110010\)를 오른쪽으로 두 비트 옮겨 \-4\(2의 보수 이진수 11111100\)가 되므로 *temp*의 값은 \-4가 됩니다.  
  
```javascript  
var temp  
temp = -14 >> 2  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [비트 왼쪽 시프트 연산자\(\<\<\)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [오른쪽 시프트 할당 연산자\(\>\>\=\)](../../javascript/reference/right-shift-assignment-operator-decrement-equal-javascript.md)   
 [부호 없는 오른쪽 시프트 연산자\(\>\>\>\)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)