---
title: "&#39;&lt;membername&gt;&#39;을 여러 번 초기화했습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30989"
  - "bc30989"
helpviewer_keywords: 
  - "BC30989"
ms.assetid: 574b6398-1e9d-43e1-ac16-6fc8687f71d9
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;membername&gt;&#39;을 여러 번 초기화했습니다.
'\<membername\>'을 여러 번 초기화했습니다. 개체 이니셜라이저 식에서 필드와 속성은 한 번만 초기화할 수 있습니다.  
  
 개체 이니셜라이저 목록에서는 각 필드 및 속성에 대해 초기 값을 한 번만 할당할 수 있습니다. 다음 선언은 올바르지 않습니다.  
  
```  
' Dim cust = New Customer() With {.Name = "Bob", .Name = "Robert"}  
```  
  
> [!NOTE]
>  다음 선언에서처럼 한 필드 또는 속성을 다른 멤버에 대한 초기 값으로 사용할 수 있습니다.  
  
```  
Dim cust = New Customer() With {.First = "Mike", .Last = "Nash", _ .Full = .First & " " & .Last}  
```  
  
 **오류 ID:** BC30989  
  
### 이 오류를 해결하려면  
  
-   개체 이니셜라이저 목록에서 각 필드 또는 속성에 대한 초기화를 하나만 남기고 모두 제거합니다.  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [빌드에 없음: 속성 프로시저 및 필드](http://msdn.microsoft.com/ko-kr/da1c05c1-87c7-40fa-b92c-e9c7e4d170f7)