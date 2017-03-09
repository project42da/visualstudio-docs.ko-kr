---
title: "&#39;&lt;membername&gt;&#39; 멤버를 공유하고 있으므로 개체 이니셜라이저 식에서 초기화할 수 없습니다. | Microsoft Docs"
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
  - "bc30991"
  - "vbc30991"
helpviewer_keywords: 
  - "BC30991"
ms.assetid: 47e832b4-47e3-426e-b88c-5d5568102fde
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;membername&gt;&#39; 멤버를 공유하고 있으므로 개체 이니셜라이저 식에서 초기화할 수 없습니다.
개체 이니셜라이저를 사용하여 공유로 선언된 클래스의 멤버를 초기화할 수 없습니다. 자세한 내용은 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)을 참조하세요.  
  
 **오류 ID:** BC30991  
  
### 이 오류를 해결하려면  
  
1.  클래스 정의를 검사하여 공유할 멤버를 확인합니다.  
  
2.  개체 이니셜라이저 목록에서 해당 멤버의 초기화를 제거합니다.  
  
## 예제  
 다음 예제에서 `totalCustomers`는 공유 멤버입니다.  
  
```  
Public Class Customer Public Shared totalCustomers As Integer ' Other declarations and method definitions. End Class  
```  
  
 `totalCustomers`가 공유되기 때문에 개체 이니셜라이저 목록에서 해당 초기 값을 설정하려고 하면 이 오류가 발생합니다.  
  
```  
' This declaration is not valid. ' Dim cust As New Customer With { .Name = "Coho Winery", _ '                                 .totalCustomers = 21 }  
```  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)   
 [빌드에 없음: Visual Basic의 공유 멤버](http://msdn.microsoft.com/ko-kr/dbc3783f-83a2-4225-995d-c2d6d025663d)