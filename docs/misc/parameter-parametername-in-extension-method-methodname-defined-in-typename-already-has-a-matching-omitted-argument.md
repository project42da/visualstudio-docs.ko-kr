---
title: "&#39;&lt;typename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;의 &#39;&lt;parametername&gt;&#39; 매개 변수에 일치하는 생략된 인수가 이미 있습니다. | Microsoft Docs"
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
  - "bc36583"
  - "vbc36583"
helpviewer_keywords: 
  - "BC36583"
ms.assetid: 662072fa-abb8-43c3-8ca2-aefb20f2e902
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;의 &#39;&lt;parametername&gt;&#39; 매개 변수에 일치하는 생략된 인수가 이미 있습니다.
확장 메서드에 대한 프로시저 호출에서 위치로 인수를 생략하고 이름으로 해당 인수를 제공합니다. 예를 들어 확장 메서드 `ABC`에 대한 다음 호출은 먼저 `Y` 매개 변수에 대한 인수를 생략한 다음 이름으로 해당 인수를 제공합니다.  
  
```  
<Extension()> _ Public Sub ABC(ByVal X As Integer, Optional ByVal Y As Byte = 0, _ Optional ByVal Z As Byte = 0) End Sub ' . . . ' Calling extension method ABC. Dim number As Integer ' Not valid. ' number.ABC(, 4, Y:=5)  
```  
  
 **오류 ID:** BC36583  
  
### 이 오류를 해결하려면  
  
-   위치로 인수를 제공하거나 인수를 생략하는 쉼표를 제거합니다.  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Passing Arguments by Position and by Name](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name)