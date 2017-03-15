---
title: "&#39;&lt;methodname&gt;&#39;은 &#39;MustOverride&#39;로 선언된 메서드를 숨길 수 없습니다. | Microsoft Docs"
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
  - "vbc31404"
  - "bc31404"
helpviewer_keywords: 
  - "BC31404"
ms.assetid: 3e7bb4a0-14af-46ba-bc62-2234c16f1827
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;methodname&gt;&#39;은 &#39;MustOverride&#39;로 선언된 메서드를 숨길 수 없습니다.
`MustOverride` 한정자와 동일한 이름을 가진 속성 또는 메서드가 파생 클래스에서 선언되었습니다.  
  
 **오류 ID:** BC31404  
  
### 이 오류를 해결하려면  
  
1.  파생 클래스의 재정의 속성 또는 메서드에 `Overrides` 한정자를 추가합니다.  
  
2.  기본 클래스의 속성 또는 메서드에서 `MustOverride` 한정자를 제거합니다.  
  
## 참고 항목  
 [MustOverride](/dotnet/visual-basic/language-reference/modifiers/mustoverride)