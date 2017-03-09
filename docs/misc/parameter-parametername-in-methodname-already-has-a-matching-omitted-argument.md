---
title: "&#39;&lt;methodname&gt;&#39;의 &#39;&lt;parametername&gt;&#39; 매개 변수에 일치하는 생략된 인수가 이미 있습니다. | Microsoft Docs"
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
  - "vbc32021"
  - "bc32021"
helpviewer_keywords: 
  - "BC32021"
ms.assetid: f51d29ba-c5b3-4731-a426-4c5ba11b4e1f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;methodname&gt;&#39;의 &#39;&lt;parametername&gt;&#39; 매개 변수에 일치하는 생략된 인수가 이미 있습니다.
프로시저 호출이 위치를 따라 동일한 인수를 생략한 후 인수를 이름으로 제공합니다. 예를 들면 다음과 같습니다.  
  
```  
Public Sub ABC(ByVal X As Byte, Optional ByVal Y As Byte = 0, _ Optional ByVal Z As Byte = 0) ' ... Call ABC(6, , Y:=3)   ' Argument Y omitted by position, supplied by name.  
```  
  
 **오류 ID:** BC32021  
  
### 이 오류를 해결하려면  
  
-   위치로 인수를 제공하거나 인수를 생략하는 쉼표를 제거합니다.  
  
## 참고 항목  
 [Passing Arguments by Position and by Name](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name)