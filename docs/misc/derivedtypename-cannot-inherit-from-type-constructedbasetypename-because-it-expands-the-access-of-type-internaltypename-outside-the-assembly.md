---
title: "&#39;&lt;derivedtypename&gt;&#39;은 형식 &#39;&lt;internaltypename&gt;&#39;의 액세스를 어셈블리 외부로 확장하므로 &lt;type&gt; &#39;&lt;constructedbasetypename&gt;&#39;에서 상속할 수 없습니다. | Microsoft Docs"
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
  - "BC30922"
  - "vbc30922"
helpviewer_keywords: 
  - "BC30922"
ms.assetid: 81909654-7e67-4b89-81a3-25ae57f678f7
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;derivedtypename&gt;&#39;은 형식 &#39;&lt;internaltypename&gt;&#39;의 액세스를 어셈블리 외부로 확장하므로 &lt;type&gt; &#39;&lt;constructedbasetypename&gt;&#39;에서 상속할 수 없습니다.
파생 클래스 또는 인터페이스가 제한된 형식을 기본 클래스 또는 인터페이스에 대한 형식 인수로 사용하여 내부 형식의 액세스 수준을 확장하려고 시도합니다.  
  
 다음 코드에서는 이 오류를 생성할 수 있습니다.  
  
```  
Public Class baseClass(Of t)  
End Class  
Public Class derivedClass  
    Inherits baseClass(Of restrictedStructure)  
End Class  
Friend Structure restrictedStructure  
    Dim firstMember As Integer  
End Structure  
```  
  
 어셈블리 외부의 코드는 `restrictedStructure`에 액세스할 수 없습니다. 그러나 `derivedClass`는 참조할 수 있는 모든 코드에서 액세스될 수 있습니다. 따라서 `derivedClass`가 형식 인수로 `restrictedStructure`를 사용하는 경우 모든 어셈블리의 코드에 `restrictedStructure`를 노출할 수 있기 때문에 `baseClass`를 상속할 수 없습니다.  
  
 **오류 ID:** BC30922  
  
### 이 오류를 해결하려면  
  
-   파생 형식이 제한된 형식의 액세스 수준을 확장하지 않도록 클래스 또는 인터페이스의 액세스 수준을 조정합니다.  
  
     또는  
  
-   액세스 수준을 조정할 수 없는 경우 기본 클래스 또는 인터페이스를 생성할 때 제한된 형식을 형식 인수로 사용하지 마세요.  
  
## 참고 항목  
 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
 [Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)