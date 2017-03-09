---
title: "선택적 매개 변수는 &#39;&lt;type&gt;&#39; 형식으로 선언할 수 없습니다. | Microsoft Docs"
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
  - "bc30423"
  - "vbc30423"
helpviewer_keywords: 
  - "BC30423"
ms.assetid: 972dab8b-d91e-4a89-b822-2b8e4aadd25f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 선택적 매개 변수는 &#39;&lt;type&gt;&#39; 형식으로 선언할 수 없습니다.
선택적 매개 변수는 구조체 데이터 형식이 될 수 없습니다.  
  
 **오류 ID:** BC30423  
  
### 이 오류를 해결하려면  
  
1.  선택적 매개 변수에 구조체를 전달하려면 매개 변수를 `Object`으로 선언합니다.  
  
2.  `CType`을 사용하여 프로시저 내에서 매개 변수를 해당 구조체 형식으로 캐스팅합니다.  
  
## 참고 항목  
 [Structures and Classes](/dotnet/visual-basic/programming-guide/language-features/data-types/structures-and-classes)   
 [CType 함수](/dotnet/visual-basic/language-reference/functions/ctype-function)