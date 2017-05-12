---
title: "비트 배타적 OR 할당 연산자(^=)(JavaScript) | Microsoft Docs"
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
  - "^="
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "^= 연산자"
  - "^= 연산자, ^= 연산자 정보"
  - "대입 연산자, 비트[JavaScript]"
  - "비트 연산자, XOR 연산자"
  - "XOR 연산자"
ms.assetid: a6ded216-27b6-4fc4-a51b-7d10cc6f820c
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 비트 배타적 OR 할당 연산자(^=)(JavaScript)
변수 값과 식의 값에 대한 비트 배타적 OR을 수행하고 결과를 변수에 할당합니다.  
  
## 구문  
  
```  
  
result ^= expression  
```  
  
## 매개 변수  
 *결과*  
 임의의 변수입니다.  
  
 *expression*  
 임의의 식입니다.  
  
## 설명  
 **^\=** 연산자를 사용하는 것은 다음을 지정하는 것과 동일합니다.  
  
```javascript  
result = result ^ expression  
```  
  
 **^\=** 연산자는 두 식의 이진 값에 대한 비트 배타적 OR 연산을 수행합니다.  이 연산의 결과는 다음과 같습니다.  
  
```javascript  
0101    (result)  
1100    (expression)  
----  
1001    (result)  
```  
  
 두 식의 특정 자릿수 중 하나만 1이면 해당 자릿수의 결과 값은 1이 되고,  그렇지 않으면 해당 자릿수의 결과 값은 0이 됩니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [비트 배타적 OR 연산자\(^\)](../../javascript/reference/bitwise-xor-operator-decrement-hat-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)