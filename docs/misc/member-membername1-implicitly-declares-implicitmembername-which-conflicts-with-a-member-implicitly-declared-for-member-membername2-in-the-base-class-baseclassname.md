---
title: "&#39;&lt;membername1&gt;&#39; 멤버가 &#39;&lt;baseclassname&gt;&#39; 기본 클래스에서 &#39;&lt;membername2&gt;&#39; 멤버에 대해 암시적으로 선언된 멤버와 충돌하는 &#39;&lt;implicitmembername&gt;&#39;을 암시적으로 선언합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40018"
  - "bc40018"
helpviewer_keywords: 
  - "BC40018"
ms.assetid: 43844e55-9ce1-4b88-9aa8-839b37f30e5a
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;membername1&gt;&#39; 멤버가 &#39;&lt;baseclassname&gt;&#39; 기본 클래스에서 &#39;&lt;membername2&gt;&#39; 멤버에 대해 암시적으로 선언된 멤버와 충돌하는 &#39;&lt;implicitmembername&gt;&#39;을 암시적으로 선언합니다.
'\<membername1\>' 멤버가 '\<baseclassname\>' 기본 클래스에서 '\<membername2\>' 멤버에 대해 암시적으로 선언된 멤버와 충돌하는 '\<implicitmembername\>'을 암시적으로 선언합니다. 따라서 멤버를 'Shadows'로 선언해야 합니다.  
  
 파생 클래스의 멤버에서 기본 클래스의 암시적 멤버와 같은 이름을 사용하는 암시적 멤버를 생성합니다. 암시적 멤버는 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)를 지정하지 않으므로 컴파일러는 이 멤버가 암시적 기본 클래스 멤버를 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows) 처리한다고 간주합니다. 이 멤버에 대해 `Shadows` 키워드를 명시적으로 지정하면 코드를 읽기 더 쉬워지며 오류 발생 가능성이 줄어듭니다.  
  
 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러는 선언한 특정 프로그래밍 요소에 해당하는 암시적 멤버를 만듭니다. 다음 표에서 이러한 암시적 또는 *가상* 멤버를 요약합니다.  
  
|선언 요소|암시적으로 만든 멤버|  
|-----------|-----------------|  
|열거형|`value__` 멤버|  
|이벤트|`add_<eventname>` 프로시저<br /><br /> `remove_<eventname>` 프로시저<br /><br /> `<eventname>Event` 필드<br /><br /> `<eventname>EventHandler` 대리자|  
|속성|`get_<propertyname>` 프로시저<br /><br /> `set_<propertyname>` 프로시저|  
|`My.Form` 멤버, `My.WebService` 멤버 또는 <xref:Microsoft.VisualBasic.MyGroupCollectionAttribute> 특성으로 표시된 클래스의 멤버|`m_<variablename>` `Static` 변수<br /><br /> `<variablename>` 속성<br /><br /> `get_<variablename>` 프로시저<br /><br /> `set_<variablename>` 프로시저|  
|`WithEvents` 변수|`_<variablename>` 변수<br /><br /> `<variablename>` 속성<br /><br /> `get_<variablename>` 프로시저<br /><br /> `set_<variablename>` 프로시저|  
  
 이름 충돌의 위험이 있으므로 이러한 암시적 멤버 중 하나와 같은 형식을 사용하여 선언된 프로그래밍 요소의 이름을 지정하지 않아야 합니다. 예를 들어 요소 이름이 `get_` 또는 `set_`로 시작하지 않아야 합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40018  
  
### 이 오류를 해결하려면  
  
-   암시적 기본 클래스 멤버를 숨기려면 파생 클래스 멤버를 선언할 때 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows) 키워드를 포함합니다.  
  
-   암시적 기본 클래스 멤버를 숨기지 않으려면 위의 표에 나열된 이름과의 충돌을 피하기 위해 파생 클래스 멤버의 이름을 변경합니다.  
  
## 참고 항목  
 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)