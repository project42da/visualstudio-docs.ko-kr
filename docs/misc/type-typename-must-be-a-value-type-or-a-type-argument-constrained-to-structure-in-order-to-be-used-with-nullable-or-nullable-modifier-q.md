---
title: "&#39;&lt;typeName&gt;&#39; 형식을 &#39;Nullable&#39; 또는 null 허용 한정자 &#39;?&#39;와 함께 사용하려면 해당 형식이 &#39;Structure&#39;의 제약을 받는 형식 인수이거나 값 형식이어야 합니다. | Microsoft Docs"
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
  - "vbc33101"
  - "bc33101"
helpviewer_keywords: 
  - "BC33101"
ms.assetid: b3e0e4e4-87b8-4a38-a450-15233497acaa
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typeName&gt;&#39; 형식을 &#39;Nullable&#39; 또는 null 허용 한정자 &#39;?&#39;와 함께 사용하려면 해당 형식이 &#39;Structure&#39;의 제약을 받는 형식 인수이거나 값 형식이어야 합니다.
구조체가 포함된 값 형식만 nullable로 선언할 수 있습니다.  
  
```vb#  
' Valid. Dim n? As Integer Dim m As Integer? ' Not valid. ' Dim p? As Object ' Dim q As Nullable(Of Object)  
```  
  
 **오류 ID:** BC33101  
  
### 이 오류를 해결하려면  
  
-   '?' 또는 `Nullable`을 제거합니다.  
  
-   값 데이터 형식을 사용합니다.  
  
## 참고 항목  
 [Nullable Value Types](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)