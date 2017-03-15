---
title: "캐스트 연산자에 구문 오류가 있습니다. 쉼표로 구분된 인수 두 개가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30944"
  - "bc30944"
helpviewer_keywords: 
  - "BC30944"
ms.assetid: 1f7ed4a1-6ff5-4836-8424-21618c68ff45
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 캐스트 연산자에 구문 오류가 있습니다. 쉼표로 구분된 인수 두 개가 필요합니다.
식이 `CType` 변환 함수 또는 `DirectCast`나 `TryCast` 변환 키워드를 사용하지만 인수를 하나만 제공합니다.  
  
 `CType`, `DirectCast` 및 `TryCast` 모두 두 개의 인수가 필요합니다. 첫 번째는 변환할 식이고 두 번째는 변환할 데이터 형식 또는 클래스 형식입니다.  
  
 **오류 ID:** BC30944  
  
### 이 오류를 해결하려면  
  
-   변환에 필요한 두 개의 인수를 제공합니다.  
  
-   `CString`과 같은 특정 [Type Conversion Functions](/dotnet/visual-basic/language-reference/functions/type-conversion-functions) 중 하나를 사용하려면 `CType` 대신 해당 함수 이름을 사용해야 합니다. 그러면 인수가 하나만 필요합니다.  
  
## 참고 항목  
 [CType 함수](/dotnet/visual-basic/language-reference/functions/ctype-function)   
 [DirectCast Operator](/dotnet/visual-basic/language-reference/operators/directcast-operator)   
 [TryCast Operator](/dotnet/visual-basic/language-reference/operators/trycast-operator)   
 [Type Conversion Functions](/dotnet/visual-basic/language-reference/functions/type-conversion-functions)