---
title: "&#39;ReDim&#39; 문은 더 이상 배열 변수를 선언하는 데 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30811"
  - "vbc30811"
helpviewer_keywords: 
  - "BC30811"
ms.assetid: 9227a06e-a997-4b16-9977-19e2bce9035b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReDim&#39; 문은 더 이상 배열 변수를 선언하는 데 사용할 수 없습니다.
`ReDim`는 기존 배열 크기를 변경하는 데에만 사용할 수 있습니다.  
  
 **오류 ID:** BC30811  
  
### 이 오류를 해결하려면  
  
-   선언된 경우 배열 크기를 지정합니다. 예를 들면 다음과 같습니다.  
  
    ```  
    Dim X(20) As Integer  
    ```  
  
## 참고 항목  
 [Arrays Summary](/dotnet/visual-basic/language-reference/keywords/arrays-summary)   
 [ReDim Statement](/dotnet/visual-basic/language-reference/statements/redim-statement)   
 [ReDim Statement Changes in Visual Basic](http://msdn.microsoft.com/ko-kr/b4da14db-ff23-490f-b3c6-d7ae1b649532)