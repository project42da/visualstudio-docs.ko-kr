---
title: "쉼표 연산자(,)(JavaScript) | Microsoft Docs"
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
  - "%2C"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "쉼표 연산자"
ms.assetid: 699fa0bf-cd0a-45ee-a291-2fbed4ecd470
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# 쉼표 연산자(,)(JavaScript)
두 식을 순차적으로 실행합니다.  
  
## 구문  
  
```  
  
expression1, expression2  
```  
  
## 매개 변수  
 `expression1`  
 임의의 식입니다.  
  
 `expression2`  
 임의의 식입니다.  
  
## 설명  
 `,` 연산자는 식이 왼쪽에서 오른쪽 순서로 실행되게 합니다.  `,` 연산자는 `for` 루프의 증분 식에서 가장 일반적으로 사용됩니다.  예를 들면 다음과 같습니다.  
  
```javascript  
j=25;  
for (i = 0; i < 10; i++, j++)  
{  
   k = i + j;  
}  
```  
  
 `for` 문은 매번 루프를 통과하는 끝 부분에서 한 개의 식만 실행되도록 허용합니다.  `,` 연산자를 사용하면 여러 개의 식이 한 개의 식으로 처리되므로 두 변수 모두 증가할 수 있습니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)