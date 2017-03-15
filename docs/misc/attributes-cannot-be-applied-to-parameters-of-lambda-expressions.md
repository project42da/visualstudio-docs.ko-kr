---
title: "람다 식의 매개 변수에는 특성을 적용할 수 없습니다. | Microsoft Docs"
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
  - "vbc36634"
  - "bc36634"
helpviewer_keywords: 
  - "BC36634"
ms.assetid: ed751d8d-11b7-4210-97e0-0319edff8c34
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 람다 식의 매개 변수에는 특성을 적용할 수 없습니다.
특성을 람다 식 정의의 매개 변수에 적용했습니다. 이는 지원되지 않습니다. 다음 코드는 이 오류를 생성합니다.  
  
```vb#  
Sub LambaAttribute()  
    ' Not valid.  
    Dim add1 = _  
    Function(<System.Runtime.InteropServices.InAttribute()> m As Integer) _  
                   m + 1  
End Sub  
```  
  
 **오류 ID:** BC36634  
  
### 이 오류를 해결하려면  
  
-   특성을 제거하거나 람다 식을 일반 함수로 변경하여 코드를 수정하는 것이 좋습니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.InAttribute>   
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)   
 [빌드에 없음: Visual Basic의 특성](http://msdn.microsoft.com/ko-kr/620bfc0e-4582-4c8b-8432-ebc5c3dccc22)