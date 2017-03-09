---
title: "&#39;&lt;genericMethodName&gt;&#39;에 형식 인수가 너무 많습니다. | Microsoft Docs"
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
  - "bc32043"
  - "vbc32043"
helpviewer_keywords: 
  - "BC32043"
ms.assetid: c4d8f67a-4317-461a-9446-6717cfa1d888
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;genericMethodName&gt;&#39;에 형식 인수가 너무 많습니다.
형식 매개 변수보다 더 많은 형식 인수로 제네릭 메서드를 호출했습니다.  
  
 제네릭 메서드를 호출할 때 해당 메서드에서 정의한 각 형식 매개 변수에 대해 하나의 형식 인수를 제공해야 합니다.  
  
 **오류 ID:** BC32043  
  
### 이 오류를 해결하려면  
  
-   호출하는 제네릭 메서드의 각 형식 매개 변수마다 하나의 형식 인수가 있도록 형식 인수 목록에서 형식 인수를 제거합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)