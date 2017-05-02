---
title: "오른쪽 시프트 할당 연산자(&gt;&gt;=)(JavaScript) | Microsoft Docs"
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
  - ">>="
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - ">>= 연산자[JavaScript]"
  - "대입 연산자, JavaScript"
  - "오른쪽 시프트 연산자[JavaScript]"
ms.assetid: 8c1f7f90-e3ac-42ee-94f2-5ccc47d7aef6
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 오른쪽 시프트 할당 연산자(&gt;&gt;=)(JavaScript)
변수 값의 부호를 유지하면서 식의 값으로 지정된 비트 수만큼 오른쪽으로 옮기고 결과를 변수에 할당합니다.  
  
## 구문  
  
```  
  
result >>= expression  
```  
  
## 매개 변수  
 *결과*  
 임의의 변수입니다.  
  
 *expression*  
 임의의 식입니다.  
  
## 설명  
 **\>\>\=** 연산자를 사용하는 것은 다음을 지정하는 것과 동일합니다.  
  
```javascript  
result = result >> expression  
```  
  
 **\>\>\=** 연산자는 *expression*에 지정한 비트 수만큼 *result*를 오른쪽으로 옮깁니다.  왼쪽에 생긴 공간은 *result*의 부호 비트로 채우고  오른쪽으로 밀려난 숫자는 버립니다.  예를 들어 다음 코드를 계산하면 14\(이진수 11110010\)를 오른쪽으로 두 비트 옮겨 \-4\(이진수 11111100\)가 되므로 *temp*의 값은 \-4가 됩니다.  
  
```javascript  
var temp  
temp = -14  
temp >>= 2  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [비트 왼쪽 시프트 연산자\(\<\<\)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [비트 오른쪽 시프트 연산자\(\>\>\)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [부호 없는 오른쪽 시프트 연산자\(\>\>\>\)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)