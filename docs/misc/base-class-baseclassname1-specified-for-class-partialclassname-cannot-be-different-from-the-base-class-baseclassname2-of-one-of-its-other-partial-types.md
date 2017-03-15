---
title: "&#39;&lt;partialclassname&gt;&#39; 클래스에 지정된 기본 클래스 &#39;&lt;baseclassname1&gt;&#39;은 다른 부분 형식(Partial Type) 중 하나의 기본 클래스 &#39;&lt;baseclassname2&gt;&#39;와 다르면 안 됩니다. | Microsoft Docs"
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
  - "BC30928"
  - "vbc30928"
helpviewer_keywords: 
  - "BC30928"
ms.assetid: da464f09-1016-4dec-beb7-3202cacd8e1e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;partialclassname&gt;&#39; 클래스에 지정된 기본 클래스 &#39;&lt;baseclassname1&gt;&#39;은 다른 부분 형식(Partial Type) 중 하나의 기본 클래스 &#39;&lt;baseclassname2&gt;&#39;와 다르면 안 됩니다.
둘 이상의 partial 선언에서 정의된 클래스에 둘 이상의 기본 클래스를 지정하는 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)이 둘 이상 있습니다.  
  
 여러 partial 선언에서 클래스의 정의를 나눌 때 컴파일러는 클래스를 모든 partial 선언의 공용 구조체로 처리합니다. 이는 멤버뿐만 아니라 구현, 상속 및 액세스 수준에도 적용됩니다.  
  
 클래스는 둘 이상의 인터페이스를 구현할 수 있지만 둘 이상의 기본 클래스에서 상속할 수 없습니다. 따라서 모든 `Inherits` 문은 동일한 기본 클래스를 지정해야 합니다.  
  
 **오류 ID:** BC30928  
  
### 이 오류를 해결하려면  
  
-   partial 클래스의 기본 클래스를 결정하고 다른 기본 클래스를 지정하는 `Inherits` 문을 해당 partial 선언에서 모두 제거합니다.  
  
## 참고 항목  
 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)   
 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)