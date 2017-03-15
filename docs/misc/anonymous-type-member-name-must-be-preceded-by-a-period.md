---
title: "무명 형식 멤버 이름은 마침표 뒤에 와야 합니다. | Microsoft Docs"
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
  - "vbc36575"
  - "bc36575"
helpviewer_keywords: 
  - "BC36575"
ms.assetid: b87be29e-39f0-4830-9969-608d71137e3e
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 무명 형식 멤버 이름은 마침표 뒤에 와야 합니다.
무명 형식 선언에 대한 개체 이니셜라이저 목록에서 값이 할당된 새 멤버 이름은 마침표 뒤에 와야 합니다. 다음 예제는 올바른 선언과 잘못된 선언을 보여 줍니다.  
  
```vb#  
' Valid.  
Dim instanceName1 = New With {.memberName = 10}  
' Invalid declaration that causes this error.  
' Dim instanceName2 = New With {memberName = 10}  
```  
  
 **오류 ID:** BC36575  
  
### 이 오류를 해결하려면  
  
-   멤버 이름 앞에 마침표를 추가합니다.  
  
## 참고 항목  
 [Anonymous Types](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types)