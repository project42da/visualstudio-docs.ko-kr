---
title: "&#39;&lt;derivedtypename&gt;&#39;은 형식 &#39;&lt;internaltypename&gt;&#39;의 액세스를 &lt;region&gt; &#39;&lt;regionname&gt;&#39;으로 확장하므로 &lt;type&gt; &#39;&lt;constructedbasetypename&gt;&#39;에서 상속할 수 없습니다. | Microsoft Docs"
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
  - "vbc30921"
  - "BC30921"
helpviewer_keywords: 
  - "BC30921"
ms.assetid: b0dd971a-80e2-4d37-925b-854d17411546
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;derivedtypename&gt;&#39;은 형식 &#39;&lt;internaltypename&gt;&#39;의 액세스를 &lt;region&gt; &#39;&lt;regionname&gt;&#39;으로 확장하므로 &lt;type&gt; &#39;&lt;constructedbasetypename&gt;&#39;에서 상속할 수 없습니다.
파생 클래스 또는 인터페이스가 내부 형식을 기본 클래스 또는 인터페이스에 대한 형식 인수로 사용하여 내부 형식의 액세스 수준을 확장하려고 시도합니다.  
  
 다음 코드에서는 이 오류를 생성할 수 있습니다.  
  
```  
Public Class containingClass Public Class baseClass(Of t) End Class Friend Class derivedClass Inherits baseClass(Of internalStructure) End Class Private Structure internalStructure Dim firstMember As Integer End Structure End Class  
```  
  
 `containingClass` 외부의 코드는 `internalStructure`에 액세스할 수 없습니다. 그러나 `derivedClass`는 동일한 어셈블리의 코드에서 액세스될 수 있습니다. 따라서 `derivedClass`가 형식 인수로 `internalStructure`를 사용하는 경우 정의하는 코드 영역을 통해 `internalStructure`를 노출할 수 있기 때문에 `baseClass`를 상속할 수 없습니다.  
  
 **오류 ID:** BC30921  
  
### 이 오류를 해결하려면  
  
-   파생된 형식이 내부 형식의 액세스 수준을 확장하지 않도록 클래스 또는 인터페이스의 액세스 수준을 조정합니다.  
  
     또는  
  
-   액세스 수준을 조정할 수 없는 경우 기본 클래스 또는 인터페이스를 생성할 때 내부 형식을 형식 인수로 사용하지 마세요.  
  
## 참고 항목  
 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
 [Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)