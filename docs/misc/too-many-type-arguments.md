---
title: "형식 인수가 너무 많습니다. | Microsoft Docs"
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
  - "vbc36579"
  - "bc36579"
helpviewer_keywords: 
  - "BC36579"
ms.assetid: f59617b2-ca66-45c6-baaa-3c8bdf7f9a55
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 인수가 너무 많습니다.
형식 매개 변수보다 더 많은 형식 인수로 제네릭 메서드를 호출했습니다.  
  
 제네릭 메서드를 호출할 때 해당 메서드에서 정의한 각 형식 매개 변수에 대해 하나의 형식 인수를 제공해야 합니다.  
  
 **오류 ID:** BC36579  
  
### 이 오류를 해결하려면  
  
-   호출하는 제네릭 메서드의 각 형식 매개 변수에 형식 인수가 하나만 있도록 형식 인수 목록에서 형식 인수를 제거합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)