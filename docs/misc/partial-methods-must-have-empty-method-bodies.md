---
title: "부분 메서드(Partial Method)의 본문은 비어 있어야 합니다. | Microsoft Docs"
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
  - "bc31435"
  - "vbc31435"
helpviewer_keywords: 
  - "BC31435"
ms.assetid: 279f283d-ce40-401c-8494-4bf06394fdd3
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 부분 메서드(Partial Method)의 본문은 비어 있어야 합니다.
부분 메서드\(Partial Method\) 서명 선언의 본문은 코드를 포함할 수 없습니다. 다음 예제에서는 부분 메서드\(Partial Method\) 서명 및 해당 구현을 보여 줍니다.  
  
```  
' Definition of the partial method signature. Partial Private Sub OnNameChanged() ' The body of the signature is empty. End Sub  
```  
  
```  
' Implementation of the partial method. Private Sub OnNameChanged() MsgBox("Name was changed to " & Me.Name) End Sub  
```  
  
 **오류 ID:** 31435  
  
### 이 오류를 해결하려면  
  
-   부분 메서드\(Partial Method\) 선언에서 코드를 제거합니다.  
  
## 참고 항목  
 [Partial Methods](/dotnet/visual-basic/programming-guide/language-features/procedures/partial-methods)