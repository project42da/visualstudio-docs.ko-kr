---
title: "&#39;&lt;parametername&gt;&#39; 매개 변수에 일치하는 생략된 인수가 이미 있습니다. | Microsoft Docs"
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
  - "vbc36566"
  - "bc36566"
helpviewer_keywords: 
  - "BC36566"
ms.assetid: b37af6bc-abd0-4436-bf8a-a467e3603342
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;parametername&gt;&#39; 매개 변수에 일치하는 생략된 인수가 이미 있습니다.
프로시저 호출에서 위치에 따른 동일한 인수를 생략한 후 이름으로 인수를 제공합니다. 예를 들면 다음과 같습니다.  
  
```vb#  
Public Sub ABC(ByVal X As Byte, Optional ByVal Y As Byte = 0, _ Optional ByVal Z As Byte = 0) ' ... ' Argument Y is omitted by position, but supplied by name. Call ABC(6, , Y:=3)     
```  
  
 **오류 ID:** BC36566  
  
### 이 오류를 해결하려면  
  
-   위치로 인수를 제공하거나 인수를 생략하는 쉼표를 제거합니다.  
  
## 참고 항목  
 [Passing Arguments by Position and by Name](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name)