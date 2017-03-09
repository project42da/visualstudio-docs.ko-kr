---
title: "&#39;methodname&#39;이 부분 메서드(Partial Method)이므로 &#39;AddressOf&#39;를 &#39;methodname&#39;에 적용할 수 없습니다. | Microsoft Docs"
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
  - "vbc31440"
  - "bc31440"
helpviewer_keywords: 
  - "BC31440"
ms.assetid: 924dbada-3e0a-4004-a3ae-a209b7c3d1fa
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;methodname&#39;이 부분 메서드(Partial Method)이므로 &#39;AddressOf&#39;를 &#39;methodname&#39;에 적용할 수 없습니다.
부분 메서드\(Partial Method\)가 `AddressOf` 연산자에 전달되었습니다. 부분 메서드\(Partial Method\)가 `AddressOf` 연산자에 대해 잘못된 값입니다.  
  
 **오류 ID:** BC31440  
  
### 이 오류를 해결하려면  
  
1.  부분 메서드\(Partial Method\)에 대한 구현 메서드를 추가합니다. 구현 메서드는 `AddressOf` 연산자에 대해 유효한 값입니다. 다음 예제에서는 부분 메서드\(Partial Method\) 서명 및 해당 구현을 보여 줍니다.  
  
    ```vb#  
    ' Definition of the partial method signature.  
    Partial Private Sub OnNameChanged()  
        ' The body of the signature is empty.  
    End Sub  
  
    ' Implementation of the partial method.  
    Private Sub OnNameChanged()  
        MsgBox("Name was changed to " & Me.Name)  
    End Sub  
    ```  
  
## 참고 항목  
 [AddressOf Operator](/dotnet/visual-basic/language-reference/operators/addressof-operator)   
 [Partial Methods](/dotnet/visual-basic/programming-guide/language-features/procedures/partial-methods)