---
title: "부분 메서드(Partial Method)는 &#39;&lt;accessModifier&gt;&#39; 대신 &#39;Private&#39;으로 선언해야 합니다. | Microsoft Docs"
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
  - "vbc31431"
  - "bc31431"
helpviewer_keywords: 
  - "BC31431"
ms.assetid: bbd757f3-7281-4488-8a06-f3b4bcc820dc
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 부분 메서드(Partial Method)는 &#39;&lt;accessModifier&gt;&#39; 대신 &#39;Private&#39;으로 선언해야 합니다.
액세스 한정자 `Private`이 부분 메서드\(Partial method\) 선언에 필요합니다. 다음 예제에서는 메서드 서명 및 해당 구현에서 `Private`을 사용하는 방법을 보여 줍니다.  
  
```vb#  
' Definition of the partial method signature. Partial Private Sub OnNameChanged() ' The body of the signature is empty. End Sub  
```  
  
```vb#  
' Implementation of the partial method. Private Sub OnNameChanged() MsgBox("Name was changed to " & Me.Name) End Sub  
```  
  
 **오류 ID:** BC31431  
  
### 이 오류를 해결하려면  
  
-   서명 및 구현 선언에서 액세스 한정자를 `Private`으로 변경합니다.  
  
## 참고 항목  
 [Partial Methods](/dotnet/visual-basic/programming-guide/language-features/procedures/partial-methods)