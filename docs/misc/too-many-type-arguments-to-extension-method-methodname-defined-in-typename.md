---
title: "&#39;&lt;typeName&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodName&gt;&#39;의 형식 인수가 너무 많습니다. | Microsoft Docs"
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
  - "bc36591"
  - "vbc36591"
helpviewer_keywords: 
  - "BC36591"
ms.assetid: 504c9b1f-f511-4198-8970-136d1a1bdafe
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typeName&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodName&gt;&#39;의 형식 인수가 너무 많습니다.
형식 매개 변수보다 더 많은 형식 인수로 제네릭 확장 메서드를 호출했습니다.  
  
 제네릭 메서드를 호출할 때 해당 메서드에서 정의한 각 형식 매개 변수에 대해 하나의 형식 인수를 제공해야 합니다.  
  
 **오류 ID:** BC36591  
  
### 이 오류를 해결하려면  
  
-   호출하는 제네릭 메서드에 의해 정의된 각 형식 매개 변수에 형식 인수가 하나만 있도록 형식 인수 목록에서 형식 인수를 제거합니다.  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)