---
title: "&#39;&lt;eventname&gt;&#39;에 대해 암시적으로 선언된 &#39;&lt;member&gt;&#39;는 기본 &lt;class&gt; &#39;&lt;classname&gt;&#39;의 &#39;MustOverride&#39; 메서드를 숨길 수 없습니다. | Microsoft Docs"
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
  - "vbc31413"
  - "bc31413"
helpviewer_keywords: 
  - "BC31413"
ms.assetid: 071706ce-a394-48b6-9afa-751cb50b2576
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;eventname&gt;&#39;에 대해 암시적으로 선언된 &#39;&lt;member&gt;&#39;는 기본 &lt;class&gt; &#39;&lt;classname&gt;&#39;의 &#39;MustOverride&#39; 메서드를 숨길 수 없습니다.
지정된 이벤트는 `MustOverride` 한정자로 선언된 메서드와 동일한 이름을 가진 멤버를 암시적으로 선언합니다.  
  
 **오류 ID:** BC31413  
  
### 이 오류를 해결하려면  
  
-   기본 클래스의 메서드에서 `MustOverride` 한정자를 제거하거나 속성 또는 메서드에 고유한 이름을 지정합니다.  
  
## 참고 항목  
 [MustOverride](/dotnet/visual-basic/language-reference/modifiers/mustoverride)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)