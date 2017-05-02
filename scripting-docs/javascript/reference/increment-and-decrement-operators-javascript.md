---
title: "증가(++) 및 감소(--) 연산자(JavaScript) | Microsoft Docs"
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
  - "--"
  - "++"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "증가 연산자, 구문"
  - "++ 연산자"
  - "++ 연산자, ++ 연산자 정보"
  - "감소 연산자, 구문"
  - "-- 연산자"
ms.assetid: 49eaf4cf-8818-478d-a429-cdd2ece20811
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 증가(++) 및 감소(--) 연산자(JavaScript)
증가 연산자는 변수 값을 1씩 증가시키고 감소 연산자는 변수 값을 1씩 감소시킵니다.  
  
## 구문  
  
```  
  
      result = ++variable  
result = --variable  
result = variable++  
result = variable--  
```  
  
## 매개 변수  
 `result`  
 임의의 변수입니다.  
  
 `variable`  
 임의의 변수입니다.  
  
## 설명  
 연산자가 변수 앞에 나타나는 경우 식이 계산되기 전에 값이 수정됩니다.  연산자가 변수 뒤에 나타나는 경우 식이 계산된 후에 값이 수정됩니다.  즉, `j = ++k;`의 경우 `j` 값은 `k`의 원래 값에 1을 더한 값입니다. `j = k++;`의 경우 `j` 값은 `k`의 원래 값이며 k 값은 `j`에 할당된 후 증가합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)