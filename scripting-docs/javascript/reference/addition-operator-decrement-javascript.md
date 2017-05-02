---
title: "더하기 연산자(+)(JavaScript) | Microsoft Docs"
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
  - "+"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "산술 연산자, 추가"
  - "문자열[Visual Studio], 연결"
  - "연결 연산자, 더하기 연산자 비교"
  - "더하기 연산자"
  - "+ 연산자"
ms.assetid: ec1237d3-e78b-4e77-bd7d-c0204cf03acd
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 더하기 연산자(+)(JavaScript)
두 숫자 식의 값을 더하거나 두 개의 문자열을 연결합니다.  
  
## 구문  
  
```  
  
result = expression1 + expression2  
```  
  
## 매개 변수  
 `result`  
 임의의 변수입니다.  
  
 `expression1`  
 임의의 식입니다.  
  
 `expression2`  
 임의의 식입니다.  
  
## 설명  
 두 식의 형식에 따라 **\+** 연산자의 동작이 결정됩니다.  
  
|상태|결과|  
|--------|--------|  
|두 식이 숫자 또는 부울인 경우|더하기|  
|두 식이 모두 문자열인 경우|연결|  
|하나는 숫자이고 다른 하나는 문자열인 경우|연결|  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [더하기 할당 연산자\(\+\=\)](../../javascript/reference/addition-assignment-operator-decrement-equal-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)