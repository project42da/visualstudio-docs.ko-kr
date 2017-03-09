---
title: "null 허용 한정자는 암시적 형식이 &#39;Object&#39;인 변수와 함께 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc33112"
  - "vbc33112"
helpviewer_keywords: 
  - "BC33112"
ms.assetid: 50b2a2ad-248d-4faa-820d-bcdf0e8b4aad
caps.latest.revision: 3
caps.handback.revision: 3
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# null 허용 한정자는 암시적 형식이 &#39;Object&#39;인 변수와 함께 사용할 수 없습니다.
변수 선언에 nullable 형식 한정자\(?\)가 포함되었지만 선언된 변수에 값을 할당하여 형식을 유추하거나 지정하지 않습니다.  
  
 **오류 ID:** BC33112  
  
### 이 오류를 해결하려면  
  
-   nullable 변수를 선언할 때 형식을 지정합니다. 형식은 <xref:System.Object>일 수 없습니다.  
  
-   nullable 변수를 선언할 때 값을 할당합니다. nullable 변수의 형식은 할당된 값에서 유추됩니다. 값의 형식은 <xref:System.Object>가 될 수 없습니다.  
  
## 참고 항목  
 [Nullable Value Types](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)