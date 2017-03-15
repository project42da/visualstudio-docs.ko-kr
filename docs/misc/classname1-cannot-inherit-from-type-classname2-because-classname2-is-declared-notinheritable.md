---
title: "&#39;&lt;classname2&gt;&#39;가 &#39;NotInheritable&#39;로 선언되었으므로 &#39;&lt;classname1&gt;&#39;은 &lt;type&gt; &#39;&lt;classname2&gt;&#39;에서 상속할 수 없습니다. | Microsoft Docs"
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
  - "vbc30299"
  - "bc30299"
helpviewer_keywords: 
  - "BC30299"
ms.assetid: 627d50f5-9e75-495d-93f7-50096ba2ea08
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;classname2&gt;&#39;가 &#39;NotInheritable&#39;로 선언되었으므로 &#39;&lt;classname1&gt;&#39;은 &lt;type&gt; &#39;&lt;classname2&gt;&#39;에서 상속할 수 없습니다.
클래스가 다른 클래스에서 상속하려고 하지만 원하는 기본 클래스가 `NotInheritable`로 지정되어 있습니다.`NotInheritable` 클래스는 의도하지 않은 파생을 방지하는 데 주로 사용됩니다.  
  
 **오류 ID:** BC30299  
  
### 이 오류를 해결하려면  
  
-   원하는 기본 클래스의 정의에서 `NotInheritable` 키워드를 제거하거나 `Inherits` 문을 제거합니다.  
  
## 참고 항목  
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
 [NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)   
 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)