---
title: "부분 메서드(Partial Method)는 &#39;Private&#39;으로 선언해야 합니다. | Microsoft Docs"
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
  - "vbc31432"
  - "bc31432"
helpviewer_keywords: 
  - "BC31432"
ms.assetid: 3a4474d9-661e-4793-9624-30cf81faddcf
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 부분 메서드(Partial Method)는 &#39;Private&#39;으로 선언해야 합니다.
액세스 한정자 `Private`이 부분 메서드\(Partial method\) 선언에 필요합니다. 다음 예제에서는 메서드 서명 및 해당 구현에서 `Private`을 사용하는 방법을 보여 줍니다.  
  
```vb#  
' Definition of the partial method signature. Partial Private Sub OnNameChanged() ' The body of the signature is empty. End Sub  
```  
  
```vb#  
' Implementation of the partial method. Private Sub OnNameChanged() MsgBox("Name was changed to " & Me.Name) End Sub  
```  
  
 **오류 ID:** BC31432  
  
### 이 오류를 해결하려면  
  
-   서명 및 구현 선언에서 `Private` 키워드를 `Sub` 앞에 추가합니다.  
  
## 참고 항목  
 [Partial Methods](/dotnet/visual-basic/programming-guide/language-features/procedures/partial-methods)