---
title: "&#39;As New&#39;를 사용하는 변수 선언에는 null 허용 한정자를 지정할 수 없습니다. | Microsoft Docs"
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
  - "bc33109"
  - "vbc33109"
helpviewer_keywords: 
  - "BC33109"
ms.assetid: 135def20-3535-4239-bffb-43208d1b3f63
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;As New&#39;를 사용하는 변수 선언에는 null 허용 한정자를 지정할 수 없습니다.
nullable 형식 한정자\(?\)가 `As New`가 지정된 변수 선언에 포함되어 있습니다. 다음 예제는 이 오류를 생성합니다.  
  
```vb#  
Dim num? As New ExampleStructure  
```  
  
 **오류 ID:** BC33109  
  
### 이 오류를 해결하려면  
  
1.  다음 예제와 같이 null 허용 변수 선언에서 `New` 키워드를 제거합니다.  
  
    ```vb#  
    Dim num? As ExampleStructure  
    ```  
  
## 참고 항목  
 [Nullable Value Types](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)