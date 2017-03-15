---
title: "Event &#39;&lt;eventname&gt;&#39;은 기본 &lt;type&gt; &#39;&lt;classname&gt;&#39;의 멤버와 충돌하는 &#39;&lt;membername&gt;&#39;을 암시적으로 선언하므로 event를 &#39;Shadows&#39;로 선언해야 합니다. | Microsoft Docs"
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
  - "bc40012"
  - "vbc40012"
helpviewer_keywords: 
  - "BC40012"
ms.assetid: 5f14e8bd-a227-4115-af99-cd2b6fe4dc0e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Event &#39;&lt;eventname&gt;&#39;은 기본 &lt;type&gt; &#39;&lt;classname&gt;&#39;의 멤버와 충돌하는 &#39;&lt;membername&gt;&#39;을 암시적으로 선언하므로 event를 &#39;Shadows&#39;로 선언해야 합니다.
이벤트는 기본 클래스의 멤버와 이름이 동일한 암시적 멤버를 형성하기 위해 결합하는 이름으로 선언됩니다. 예를 들어 `Event1`이라는 이벤트를 선언한 경우 컴파일러는 암시적 프로시저 `add_Event1` 및 `remove_Event1`을 생성합니다. 기본 클래스에 이 이름 중 하나를 사용하는 멤버가 있는 경우 이 클래스의 이벤트는 기본 클래스 멤버를 숨깁니다.  
  
 이 메시지는 경고입니다. 기본적으로 `Shadows`로 간주됩니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40012  
  
### 이 오류를 해결하려면  
  
1.  기본 클래스 멤버를 숨기려면 `Shadows` 키워드를 이벤트 선언에 추가합니다.  
  
2.  기본 클래스 멤버를 숨기지 않으려면 이벤트 이름을 변경합니다.  
  
## 참고 항목  
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)   
 [Shadowing in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/shadowing)