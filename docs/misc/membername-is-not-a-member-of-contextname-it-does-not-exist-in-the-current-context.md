---
title: "&#39;&lt;membername&gt;&#39;은 &#39;&lt;contextname&gt;&#39;의 멤버가 아닙니다. 현재 컨텍스트에 없습니다. | Microsoft Docs"
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
  - "vbc36557"
  - "bc36557"
helpviewer_keywords: 
  - "BC36557"
ms.assetid: d8671f1c-d545-44da-89b3-7d892e01e8be
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;membername&gt;&#39;은 &#39;&lt;contextname&gt;&#39;의 멤버가 아닙니다. 현재 컨텍스트에 없습니다.
무명 형식 선언에서 존재하지 않는 멤버 이름이 속성에 할당되었습니다. 다음 예제에서 무명 형식의 속성은 `.Prop1` 및 `.Prop2`입니다.`.Prop3`을 `.Prop2`에 할당하려고 하면 오류가 발생합니다.  
  
```vb#  
' Not valid.  
Dim anon1 = New With {.Prop1 = 27, .Prop2 = .Prop3}  
  
' The assignment is valid if the assigned property has been declared   
' and initialized.  
Dim anon2 = New With {.Prop1 = 27, .Prop2 = .Prop1}  
```  
  
 **오류 ID:** BC36657  
  
### 이 오류를 해결하려면  
  
-   코드에서 할당하려는 항목을 확인합니다. 변수 이름의 철자가 잘못되었거나 다른 개체의 특성인 경우 한정자가 필요할 수 있습니다.  
  
## 참고 항목  
 [Anonymous Types](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types)   
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../Topic/How%20to:%20Infer%20Property%20Names%20and%20Types%20in%20Anonymous%20Type%20Declarations%20\(Visual%20Basic\).md)