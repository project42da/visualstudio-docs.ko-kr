---
title: "무명 형식에는 적어도 한 멤버가 있어야 합니다. | Microsoft Docs"
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
  - "bc36574"
  - "vbc36574"
helpviewer_keywords: 
  - "BC36574"
ms.assetid: fdc8dd47-ea38-49e8-8dd5-676f726cd101
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 무명 형식에는 적어도 한 멤버가 있어야 합니다.
무명 형식 선언에서 이니셜라이저 목록은 비워둘 수 없습니다.  
  
```  
' Not valid. ' Dim anonInstance = New With {}  
```  
  
 **오류 ID:** BC36574  
  
### 이 오류를 해결하려면  
  
-   다음 코드에 표시된 것처럼 중괄호 내에 있는 멤버를 선언합니다.  
  
    ```  
    Dim anonInstance = New With {.MemberName = "value"}  
    ```  
  
## 참고 항목  
 [Anonymous Types](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types)