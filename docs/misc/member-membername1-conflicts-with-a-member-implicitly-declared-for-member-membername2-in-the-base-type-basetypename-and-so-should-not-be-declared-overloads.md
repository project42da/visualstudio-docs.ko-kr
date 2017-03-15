---
title: "멤버 &#39;&lt;membername1&gt;&#39;은 기본 형식 &#39;&lt;basetypename&gt;&#39;의 멤버 &#39;&lt;membername2&gt;&#39;에 대해 암시적으로 선언된 멤버와 충돌하므로 &#39;Overloads&#39;로 선언할 수 없습니다. | Microsoft Docs"
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
  - "vbc40023"
  - "bc40023"
helpviewer_keywords: 
  - "BC40023"
ms.assetid: 82bb29a6-8d49-47a4-8c19-b21e97dfc7de
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 멤버 &#39;&lt;membername1&gt;&#39;은 기본 형식 &#39;&lt;basetypename&gt;&#39;의 멤버 &#39;&lt;membername2&gt;&#39;에 대해 암시적으로 선언된 멤버와 충돌하므로 &#39;Overloads&#39;로 선언할 수 없습니다.
파생 클래스의 프로시저 또는 속성에서 기본 클래스의 암시적 멤버와 같은 이름을 사용하고 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads) 키워드를 지정합니다.  
  
 오버로드는 동일한 클래스에 있는 여러 버전의 속성 또는 프로시저 모두를 정의하는 데 사용됩니다. 기본 클래스 멤버가 이미 `Overloads`를 지정하지 않은 경우 기본 클래스 멤버의 추가 버전을 정의할 수 없습니다. 암시적 멤버는 `Overloads`를 지정하지 않으므로 컴파일러에서 이 속성 또는 프로시저가 암시적 기본 클래스 멤버를 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows) 처리한다고 간주합니다.  
  
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
  
 **오류 ID:** BC40023  
  
### 이 오류를 해결하려면  
  
-   위의 표에 나열된 이름과 충돌하지 않도록 속성 또는 프로시저의 이름을 변경합니다.  
  
## 참고 항목  
 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)