---
title: "&#39;&lt;membername&gt;&#39; 멤버는 형식 매개 변수와 이름이 같은 &#39;&lt;implicitmembername&gt;&#39; 멤버를 암시적으로 정의합니다. | Microsoft Docs"
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
  - "BC32070"
  - "vbc32070"
helpviewer_keywords: 
  - "BC32070"
ms.assetid: cc0b3fcf-c141-47e2-9b33-d2b91c8bf2d6
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;membername&gt;&#39; 멤버는 형식 매개 변수와 이름이 같은 &#39;&lt;implicitmembername&gt;&#39; 멤버를 암시적으로 정의합니다.
제네릭 클래스의 멤버는 클래스에 대한 형식 매개 변수와 이름이 같은 암시적 멤버를 생성합니다.  
  
 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러는 선언한 특정 프로그래밍 요소에 해당하는 암시적 멤버를 만듭니다. 다음 표에서 이러한 암시적 또는 *가상* 멤버를 요약합니다.  
  
|선언 요소|암시적으로 만든 멤버|  
|-----------|-----------------|  
|열거형|`value__` 멤버|  
|이벤트|`add_<eventname>` 프로시저<br /><br /> `remove_<eventname>` 프로시저<br /><br /> `<eventname>Event` 필드<br /><br /> `<eventname>EventHandler` 대리자|  
|속성|`get_<propertyname>` 프로시저<br /><br /> `set_<propertyname>` 프로시저|  
|`My.` 컬렉션 변수|`m_<variablename>` `Static` 변수<br /><br /> `<variablename>` 속성<br /><br /> `get_<variablename>` 프로시저<br /><br /> `set_<variablename>` 프로시저|  
|`WithEvents` 변수|`_<variablename>` 변수<br /><br /> `<variablename>` 속성<br /><br /> `get_<variablename>` 프로시저<br /><br /> `set_<variablename>` 프로시저|  
  
 이름 충돌 가능성이 있으므로 선언된 프로그래밍 요소의 이름을 이러한 암시적 멤버 중 하나와 같은 형식을 사용하여 지정하지 않아야 합니다. 예를 들어 요소 이름이 `get_` 또는 `set_`로 시작하지 않아야 합니다.  
  
 **오류 ID:** BC32070  
  
### 이 오류를 해결하려면  
  
-   형식 매개 변수의 이름이 유연한 경우 앞의 표에 나열된 이름과 충돌하지 않도록 변경합니다.  
  
-   형식 매개 변수의 이름을 유지해야 하는 경우 앞의 표에 나열된 이름과 충돌하지 않도록 클래스 멤버의 이름을 변경합니다.  
  
## 참고 항목  
 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)