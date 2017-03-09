---
title: "&#39;MustOverride&#39; 메서드 &#39;&lt;methodname&gt;&#39;은 &#39;MyClass&#39;로 호출할 수 없습니다. | Microsoft Docs"
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
  - "bc30614"
  - "vbc30614"
helpviewer_keywords: 
  - "BC30614"
ms.assetid: fc57af41-1552-46d1-9727-341f1835e661
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;MustOverride&#39; 메서드 &#39;&lt;methodname&gt;&#39;은 &#39;MyClass&#39;로 호출할 수 없습니다.
`MyClass`는 `Me`와 일치하지만 이에 대한 모든 메서드를 호출하면 호출되는 메서드가 `NotOverridable`인 것으로 처리됩니다.  
  
 **오류 ID:** BC30614  
  
### 이 오류를 해결하려면  
  
-   `MustOverride` 한정자를 제거하거나 기본 클래스에서 메서드를 선언하고 해당 클래스를 상속하고 재정의합니다.  
  
## 참고 항목  
 [MustOverride](/dotnet/visual-basic/language-reference/modifiers/mustoverride)   
 [MustInherit](/dotnet/visual-basic/language-reference/modifiers/mustinherit)   
 [NotOverridable](/dotnet/visual-basic/language-reference/modifiers/notoverridable)