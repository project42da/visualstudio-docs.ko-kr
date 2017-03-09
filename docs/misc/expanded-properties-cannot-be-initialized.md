---
title: "확장된 속성은 초기화할 수 없습니다. | Microsoft Docs"
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
  - "vbc36714"
  - "bc36714"
helpviewer_keywords: 
  - "BC36714"
ms.assetid: ba9408f3-e606-4749-8372-987999f405f5
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 확장된 속성은 초기화할 수 없습니다.
자동 구현 속성을 해당 선언의 일부로 초기화할 수 있지만 확장 속성은 그렇게 할 수 없습니다.  
  
 **오류 ID:** BC36714  
  
### 이 오류를 해결하려면  
  
-   자동 구현 속성을 사용하거나 속성 선언에서 초기화를 제거합니다.  
  
## 예제  
 다음 예제에서는 자동 구현 및 확장 속성을 모두 보여 줍니다. 자동 구현 속성은 할당 또는 `New` 절을 사용하여 초기화할 수 있지만 확장 속성은 그렇게 할 수 없습니다.  
  
```vb#  
Class AutoImplementedExample ' An auto-implemented property can be assigned an initial value. Property IDNum As Integer = 33542 ' An auto-implemented property can be initialized with New. Property Name As New String("Don Hall") End Class Class ExpandedExample ' Attempting to expand an initialized auto-implemented property ' causes this error. 'Property IDNum As Integer = 33542 '    Get '    End Get '    Set(ByVal value As Integer) '    End Set 'End Property ' Instead, you can assign the initial value to the backing field. Private _IDNum As Integer = 33542 Property IDNum As Integer Get End Get Set(ByVal value As Integer) End Set End Property End Class  
```  
  
## 참고 항목  
 [Auto\-Implemented Properties](/dotnet/visual-basic/programming-guide/language-features/procedures/auto-implemented-properties)   
 [How to: Create a Property](../Topic/How%20to:%20Create%20a%20Property%20\(Visual%20Basic\).md)   
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)