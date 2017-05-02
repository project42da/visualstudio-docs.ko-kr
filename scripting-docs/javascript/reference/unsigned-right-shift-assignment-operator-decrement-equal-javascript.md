---
title: "부호 없는 오른쪽 시프트 할당 연산자(&gt;&gt;&gt;=)(JavaScript) | Microsoft Docs"
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
  - ">>>="
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - ">>>= 연산자"
  - "대입 연산자, JavaScript"
  - "부호 없는 오른쪽 시프트 할당 연산자(>>>=)"
ms.assetid: f67c3737-7d39-41ae-9c11-8b16d38f6179
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 부호 없는 오른쪽 시프트 할당 연산자(&gt;&gt;&gt;=)(JavaScript)
변수 값의 부호를 유지하지 않으면서 식의 값으로 지정된 비트 수만큼 오른쪽으로 옮기고 결과를 변수에 할당합니다.  
  
## 구문  
  
```  
  
result >>>= expression  
```  
  
## 매개 변수  
 *결과*  
 임의의 변수입니다.  
  
 *expression*  
 임의의 식입니다.  
  
## 설명  
 \>\>\>\= 연산자 사용은 다음 작업을 수행하는 것과 같습니다.  
  
```javascript  
result = result >>> expression  
```  
  
 **\>\>\>\=** 연산자는 *expression*에서 지정한 비트 수만큼 *result*를 오른쪽으로 옮깁니다.  왼쪽부터 0을 채웁니다.  오른쪽으로 밀려난 숫자는 버립니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var temp  
temp = -14  
temp >>>= 2  
```  
  
 *temp* 변수의 초기 값은 \-14\(2의 보수 이진값으로 111111111 11111111 11111111 11110010\)입니다.  오른쪽으로 두 비트를 옮기면 값은 1073741820\(이진수 00111111 11111111 11111111 11111100\)이 됩니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [부호 없는 오른쪽 시프트 연산자\(\>\>\>\)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [비트 왼쪽 시프트 연산자\(\<\<\)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [비트 오른쪽 시프트 연산자\(\>\>\)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)