---
title: "&#39;System.Void&#39;는 GetType 식에서만 사용할 수 있습니다. | Microsoft Docs"
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
  - "bc31422"
  - "vbc31422"
helpviewer_keywords: 
  - "BC31422"
ms.assetid: 84e45194-cb46-41f6-8420-a1498baeaaba
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;System.Void&#39;는 GetType 식에서만 사용할 수 있습니다.
대입문 또는 선언의 식에서 <xref:System.Void>를 변수, 프로시저 매개 변수, 함수 반환 또는 형식 인수의 형식으로 사용합니다.  
  
 <xref:System.Void> 구조체는 .NET Framework에서 내부적으로, 그리고 Visual C\# 및 Visual C\+\+에서 특별하게 사용되는 특수화된 형식입니다. 값을 반환하지 않는 메서드에 대한 반환 값 형식을 나타냅니다. Visual Basic에서는 값이 반환되지 않을 때 `Sub` 프로시저를 사용하고 값이 반환될 때 `Function` 프로시저를 사용합니다.  
  
 [GetType Operator](/dotnet/visual-basic/language-reference/operators/gettype-operator) 연산자를 사용하여 참조 변수를 테스트하여 해당 런타임 형식이 <xref:System.Void>인지 확인할 수 있지만 다른 컨텍스트에서는 <xref:System.Void>를 사용할 수 없습니다.  
  
 **오류 ID:** BC31422  
  
### 이 오류를 해결하려면  
  
1.  변수의 런타임 형식을 <xref:System.Void>와 비교하려면 `GetType` 연산자를 사용합니다.  
  
2.  런타임 형식을 <xref:System.Void>와 비교할 특별한 이유가 없다면 이에 대한 참조도 함께 제거합니다.  
  
## 참고 항목  
 <xref:System.Void>   
 [GetType Operator](/dotnet/visual-basic/language-reference/operators/gettype-operator)