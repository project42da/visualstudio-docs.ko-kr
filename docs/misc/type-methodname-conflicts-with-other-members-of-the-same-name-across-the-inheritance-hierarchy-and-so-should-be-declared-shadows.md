---
title: "&lt;type&gt; &#39;&lt;methodname&gt;&#39;은 상속 계층 구조에서 이름이 같은 다른 멤버와 충돌하므로 &#39;Shadows&#39;로 선언해야 합니다. | Microsoft Docs"
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
  - "vbc42000"
  - "bc42000"
helpviewer_keywords: 
  - "BC42000"
ms.assetid: 3081635f-99a9-4e90-997f-82251144d80f
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;type&gt; &#39;&lt;methodname&gt;&#39;은 상속 계층 구조에서 이름이 같은 다른 멤버와 충돌하므로 &#39;Shadows&#39;로 선언해야 합니다.
두 개 이상의 인터페이스에서 상속하는 인터페이스는 둘 이상의 기본 인터페이스에 이미 정의된 프로시저와 같은 이름의 프로시저를 정의합니다. 이 인터페이스의 프로시저는 기본 인터페이스 프로시저 중 하나를 숨깁니다.  
  
 이 메시지는 경고입니다. 기본적으로 `Shadows`로 간주됩니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42000  
  
### 이 오류를 해결하려면  
  
-   기본 인터페이스 프로시저 중 하나를 숨기려면 새 프로시저 선언에 `Shadows` 키워드를 추가합니다.  
  
-   기본 인터페이스 프로시저 중 아무것도 숨기지 않으려면 새 프로시저의 이름을 변경합니다.  
  
## 참고 항목  
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)   
 [Shadowing in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/shadowing)