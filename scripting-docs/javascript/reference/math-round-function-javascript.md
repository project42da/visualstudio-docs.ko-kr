---
title: "Math.round 함수(JavaScript) | Microsoft Docs"
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
  - "round"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Math 개체"
  - "Round 메서드"
ms.assetid: 51008df3-5d0c-4951-84cb-4f41000db0be
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# Math.round 함수(JavaScript)
제공된 수식을 반올림하여 가장 가까운 정수를 반환합니다.  
  
## 구문  
  
```  
  
Math.round(  
number  
)   
```  
  
## 설명  
 필수 `number` 인수는 가장 가까운 정수로 반올림되는 값입니다.  
  
 양수의 경우 `number`의 소수 부분이 0.5 이상이면 반환 값은 `number`보다 큰 가장 작은 정수와 같습니다.  소수 부분이 0.5 미만이면 반환 값은 `number`보다 작거나 같은 가장 큰 정수와 같습니다.  
  
 음수의 경우 소수 부분이 정확하게 \-0.5이면 반환 값은 number보다 큰 가장 작은 정수와 같습니다.  
  
 예를 들어 `Math.round(8.5)`는 9를 반환하지만 `Math.round(-8.5)`는 \-8을 반환합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## 참고 항목  
 [Math.random 함수](../../javascript/reference/math-random-function-javascript.md)