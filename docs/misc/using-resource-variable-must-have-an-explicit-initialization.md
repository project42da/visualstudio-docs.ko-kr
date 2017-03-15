---
title: "&#39;Using&#39; 리소스 변수에는 명시적 초기화를 사용해야 합니다. | Microsoft Docs"
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
  - "vbc36011"
  - "bc36011"
helpviewer_keywords: 
  - "BC36011"
ms.assetid: 5db996a6-0802-4b67-91f1-4aa9c3dd6b09
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Using&#39; 리소스 변수에는 명시적 초기화를 사용해야 합니다.
`Using` 문이 `New` 절로 초기화되지 않는 하나 이상의 리소스를 지정합니다.  
  
 `Using` 블록에 제어를 전달하기 전에 아직 리소스를 취득하지 않은 경우 `Using` 문이 해당 리소스를 취득해야 합니다. 그러려면 지정된 클래스에서 개체를 만들어야 하며 이를 위해 `New` 절이 필요합니다.  
  
 **오류 ID:** BC36011  
  
### 이 오류를 해결하려면  
  
-   이미 리소스를 취득한 경우 취득한 리소스로 평가되는 `Using` 문에서 참조 변수 또는 식을 사용합니다.  
  
     `Dim newFont As New System.Drawing.Font`  
  
     `Using newFont`  
  
-   아직 리소스를 취득하지 않은 경우 `New` 절을 `Using` 문에 추가합니다.  
  
     `Using newFont as`   `New`   `System.Drawing.Font`  
  
## 참고 항목  
 [Using Statement](/dotnet/visual-basic/language-reference/statements/using-statement)   
 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator)   
 [How to: Dispose of a System Resource](../Topic/How%20to:%20Dispose%20of%20a%20System%20Resource%20\(Visual%20Basic\).md)