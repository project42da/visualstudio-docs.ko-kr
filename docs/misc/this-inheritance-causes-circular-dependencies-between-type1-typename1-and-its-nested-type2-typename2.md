---
title: "이 상속 때문에 &lt;type1&gt; &#39;&lt;typename1&gt;&#39; 및 그 안에 중첩된 &lt;type2&gt; &#39;&lt;typename2&gt;&#39; 사이에서 순환 종속성이 발생합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30907"
  - "bc30907"
helpviewer_keywords: 
  - "BC30907"
ms.assetid: 17d4f938-5895-4d33-943e-8abf0ceacdc9
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 상속 때문에 &lt;type1&gt; &#39;&lt;typename1&gt;&#39; 및 그 안에 중첩된 &lt;type2&gt; &#39;&lt;typename2&gt;&#39; 사이에서 순환 종속성이 발생합니다.
상속 구조에서 중첩되는 클래스 간에 순환 종속성, 즉 두 개의 클래스가 상호 상속하는 결과가 발생합니다.  
  
 다음 코드에서는 이 오류 메시지를 생성할 수 있습니다.  
  
```  
Public Class c1 Inherits c3.c4 Public Class c2 End Class End Class Public Class c3 Inherits c1.c2 Public Class c4 End Class End Class  
```  
  
 앞의 코드에서 `c1` 클래스는 `c4` 클래스에서 상속하지만 `c4`가 `c3` 내에 중첩되어 있어 `c1`에 중첩된 `c2`에서 상속합니다.  
  
 **오류 ID:** BC30907  
  
### 이 오류를 해결하려면  
  
-   순환 종속성이 없도록 상속 구조를 변경합니다.  
  
## 참고 항목  
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)