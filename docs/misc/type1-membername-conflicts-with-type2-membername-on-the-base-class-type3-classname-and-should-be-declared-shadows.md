---
title: "&lt;type1&gt; &#39;&lt;membername&gt;&#39;이 &lt;type3&gt; &#39;&lt;classname&gt;&#39; 기본 클래스에서 &lt;type2&gt; &#39;&lt;membername&gt;&#39;과 충돌하므로 &#39;Shadows&#39;로 선언해야 합니다. | Microsoft Docs"
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
  - "bc40004"
  - "vbc40004"
helpviewer_keywords: 
  - "BC40004"
ms.assetid: 24d10f31-3b3d-448c-b928-fc937e1f4a92
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;type1&gt; &#39;&lt;membername&gt;&#39;이 &lt;type3&gt; &#39;&lt;classname&gt;&#39; 기본 클래스에서 &lt;type2&gt; &#39;&lt;membername&gt;&#39;과 충돌하므로 &#39;Shadows&#39;로 선언해야 합니다.
프로그래밍 요소가 기본 클래스에 정의된 요소와 동일한 이름으로 선언되었습니다. 이 상황에서 이 클래스의 요소는 기본 클래스 요소를 숨깁니다.  
  
 이 메시지는 경고입니다. 기본적으로 `Shadows`로 간주됩니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40004  
  
### 이 오류를 해결하려면  
  
-   `Shadows` 키워드를 선언에 추가하거나 선언하고 있는 요소의 이름을 변경합니다.  
  
## 참고 항목  
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)   
 [Shadowing in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/shadowing)