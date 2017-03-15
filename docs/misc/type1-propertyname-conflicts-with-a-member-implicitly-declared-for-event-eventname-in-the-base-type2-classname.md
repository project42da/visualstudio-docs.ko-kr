---
title: "&lt;type1&gt; &#39;&lt;propertyname&gt;&#39;은 기본 &lt;type2&gt; &#39;&lt;classname&gt;&#39;의 &#39;&lt;eventname&gt;&#39; 이벤트에 대해 암시적으로 선언된 멤버와 충돌합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40014"
  - "bc40014"
helpviewer_keywords: 
  - "BC40014"
ms.assetid: 100534b9-d533-4e94-a2a7-0ed26426965b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;type1&gt; &#39;&lt;propertyname&gt;&#39;은 기본 &lt;type2&gt; &#39;&lt;classname&gt;&#39;의 &#39;&lt;eventname&gt;&#39; 이벤트에 대해 암시적으로 선언된 멤버와 충돌합니다.
기본 클래스의 이벤트에서 형성된 암시적 멤버와 동일한 이름을 가진 속성이 선언되었습니다. 예를 들어 기본 클래스에서 `Event1`이라는 이벤트를 정의하는 경우 컴파일러는 암시적 프로시저 `add_Event1` 및 `remove_Event1`을 생성합니다. 이 클래스의 속성이 이러한 이름 중 하나이면 기본 클래스 멤버를 숨깁니다.  
  
 이 메시지는 경고입니다. 기본적으로 `Shadows`로 간주됩니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40014  
  
### 이 오류를 해결하려면  
  
1.  기본 클래스 멤버를 숨기려면 `Shadows` 키워드를 속성 선언에 추가합니다.  
  
2.  기본 클래스 멤버를 숨기지 않으려면 속성 이름을 변경합니다.  
  
## 참고 항목  
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)   
 [Shadowing in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/shadowing)