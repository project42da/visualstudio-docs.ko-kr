---
title: "비트 왼쪽 시프트 연산자(&lt;&lt;)(JavaScript) | Microsoft Docs"
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
  - "<<"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "<< 연산자"
  - "<< 연산자, << 연산자 정보"
  - "비트 연산자, 왼쪽 시프트 연산자"
  - "왼쪽 시프트 연산자"
ms.assetid: 18148596-7b86-4add-aeef-106991c69435
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 비트 왼쪽 시프트 연산자(&lt;&lt;)(JavaScript)
식의 비트 단위로 왼쪽으로 이동합니다.  
  
## 구문  
  
```  
  
result = expression1 << expression2  
```  
  
## 매개 변수  
 *결과*  
 임의의 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## 설명  
 **\<\<** 연산자는 *expression1*의 비트를 *expression2*에 지정된 비트 수만큼 왼쪽으로 이동합니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var temp  
temp = 14 << 2  
```  
  
 14\(이진수 00001110\)를 왼쪽으로 두 비트 옮기면 56\(이진수 00111000\)이 되므로 변수 *temp*의 값은 56이 됩니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [왼쪽 시프트 할당 연산자\(\<\<\=\)](../../javascript/reference/left-shift-assignment-operator-decrement-equal-javascript.md)   
 [비트 오른쪽 시프트 연산자\(\>\>\)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [부호 없는 오른쪽 시프트 연산자\(\>\>\>\)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)