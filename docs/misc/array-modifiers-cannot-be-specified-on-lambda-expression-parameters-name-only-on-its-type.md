---
title: "람다 식 매개 변수 이름에는 배열 한정자를 지정할 수 없습니다. 해당 형식에만 지정할 수 있습니다. | Microsoft Docs"
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
  - "vbc36643"
  - "bc36643"
helpviewer_keywords: 
  - "BC36643"
ms.assetid: 34b6141b-6eab-4641-a3f4-53ef28c1792b
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 람다 식 매개 변수 이름에는 배열 한정자를 지정할 수 없습니다. 해당 형식에만 지정할 수 있습니다.
배열 인수를 람다 식으로 보낼 수 있지만 매개 변수 선언에 요소 형식이 포함되어야 합니다.  
  
```vb#  
' Not valid.  
' Dim arrayExample1 = Function(arrayPara()) 2  
  
' Valid.  
Dim arrayExample2 = Function(arrayPara() As Integer) arrayPara.Length > 0  
Dim arrayexample3 = Function(arrayPara As Integer()) arrayPara.Length > 0  
```  
  
 **오류 ID:** BC36643  
  
### 이 오류를 해결하려면  
  
-   배열 매개 변수에 요소의 형식을 지정합니다.  
  
## 참고 항목  
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)