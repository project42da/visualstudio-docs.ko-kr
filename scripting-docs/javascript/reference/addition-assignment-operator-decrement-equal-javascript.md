---
title: "더하기 할당 연산자(+=)(JavaScript) | Microsoft Docs"
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
  - "+="
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "더하기 할당 연산자(+=)"
  - "+= 연산자"
  - "대입 연산자, JavaScript"
ms.assetid: 8517d05c-38b0-4107-bea4-253eb420f438
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 더하기 할당 연산자(+=)(JavaScript)
변수 값에 식의 값을 더하고 결과를 변수에 할당합니다.  
  
## 구문  
  
```  
  
result += expression   
```  
  
## 매개 변수  
 `result`  
 임의의 변수입니다.  
  
 `expression`  
 임의의 식입니다.  
  
## 설명  
 이 연산자를 사용하는 것은 `result = result + expression`을 지정하는 것과 동일합니다.  
  
 두 식의 형식에 따라 `+=` 연산자의 동작이 결정됩니다.  
  
|상태|결과|  
|--------|--------|  
|두 식이 숫자 또는 부울인 경우|더하기|  
|두 식이 모두 문자열인 경우|연결|  
|하나는 숫자이고 다른 하나는 문자열인 경우|연결|  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [더하기 연산자\(\+\)](../../javascript/reference/addition-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)