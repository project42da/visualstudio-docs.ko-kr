---
title: "&#39;&lt;type1&gt;&#39;은 &#39;Overridable&#39;로 선언되지 않았으므로 &#39;&lt;type2&gt;&#39;를 재정의할 수 없습니다. | Microsoft Docs"
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
  - "bc31086"
  - "vbc31086"
helpviewer_keywords: 
  - "BC31086"
ms.assetid: ce071994-2e32-4460-a65d-f48f914386c6
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;type1&gt;&#39;은 &#39;Overridable&#39;로 선언되지 않았으므로 &#39;&lt;type2&gt;&#39;를 재정의할 수 없습니다.
파생 클래스의 멤버가 `Overridable` 한정자로 표시되지 않은 기본 클래스 멤버를 재정의합니다.  
  
 **오류 ID:** BC31086  
  
### 이 오류를 해결하려면  
  
1.  기본 클래스에서 재정의된 멤버에 `Overridable` 한정자를 추가합니다.  
  
2.  `Shadows` 키워드를 사용하여 기본 클래스의 항목을 숨깁니다.  
  
## 참고 항목  
 [Overridable](/dotnet/visual-basic/language-reference/modifiers/overridable)   
 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides)   
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)