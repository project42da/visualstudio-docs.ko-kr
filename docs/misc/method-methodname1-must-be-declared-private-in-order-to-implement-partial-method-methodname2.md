---
title: "부분 메서드(Partial Method) &#39;&lt;methodname2&gt;&#39;를 구현하려면 &#39;&lt;methodname1&gt;&#39; 메서드를 &#39;Private&#39;으로 선언해야 합니다. | Microsoft Docs"
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
  - "vbc31441"
  - "bc31441"
helpviewer_keywords: 
  - "BC31441"
ms.assetid: 4d8d19ad-0c3b-4eba-ada8-2cfa6ae795c4
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 부분 메서드(Partial Method) &#39;&lt;methodname2&gt;&#39;를 구현하려면 &#39;&lt;methodname1&gt;&#39; 메서드를 &#39;Private&#39;으로 선언해야 합니다.
부분 메서드\(Partial Method\)의 구현을 `Private`으로 선언해야 합니다. 예를 들어 다음 코드에서는 이 오류를 생성합니다.  
  
```vb#  
Partial Class Product ' Declaration of the partial method. Partial Private Sub valueChanged() End Sub End Class  
```  
  
```vb#  
Partial Class Product ' Implementation of the partial method, with Private missing, ' causes this error. 'Sub valueChanged() '    MsgBox(Value was changed to " & Me.Quantity) 'End Sub End Class  
```  
  
 **오류 ID:** BC31441  
  
### 이 오류를 해결하려면  
  
1.  다음 예제와 같이 부분 메서드\(Partial Method\)의 구현에서 `Private` 액세스 한정자를 사용합니다.  
  
    ```vb#  
    Private Sub valueChanged() MsgBox(Value was changed to " & Me.Quantity) End Sub  
    ```  
  
## 참고 항목  
 [Partial Methods](/dotnet/visual-basic/programming-guide/language-features/procedures/partial-methods)   
 [Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)