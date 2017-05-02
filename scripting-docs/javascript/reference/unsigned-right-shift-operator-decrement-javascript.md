---
title: "부호 없는 오른쪽 시프트 연산자(&gt;&gt;&gt;)(JavaScript) | Microsoft Docs"
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
  - ">>>"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - ">>> 연산자"
  - "부호 없는 오른쪽 시프트 연산자(>>>)"
ms.assetid: df48bdfc-8741-46ab-b681-449da57ac95c
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 부호 없는 오른쪽 시프트 연산자(&gt;&gt;&gt;)(JavaScript)
부호 없이 식을 비트 단위로 오른쪽으로 이동합니다.  
  
## 구문  
  
```  
  
result = expression1 >>> expression2  
```  
  
## 매개 변수  
 *결과*  
 임의의 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## 설명  
 **\>\>\>** 연산자는 *expression1*의 비트를 *expression2*에 지정된 비트 수만큼 오른쪽으로 이동합니다.  왼쪽부터 0을 채웁니다.  오른쪽으로 밀려난 숫자는 버립니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var temp  
temp = -14 >>> 2  
```  
  
 *temp* 변수의 초기 값은 \-14\(2의 보수 이진값으로 11111111 11111111 11111111 11110010\)입니다.  두 비트 오른쪽으로 이동하면 값은 1073741820\(이진수 00111111 11111111 11111111 11111100\)이 됩니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [부호 없는 오른쪽 시프트 할당 연산자\(\>\>\>\=\)](../../javascript/reference/unsigned-right-shift-assignment-operator-decrement-equal-javascript.md)   
 [비트 왼쪽 시프트 연산자\(\<\<\)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [비트 오른쪽 시프트 연산자\(\>\>\)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)