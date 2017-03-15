---
title: "&#39;&lt;interfacename1&gt;&#39; 인터페이스를 상속할 수 없습니다. 이 인터페이스가 일부 형식 인수에 대해 &#39;&lt;interfacename2&gt;&#39; 인터페이스와 동일할 수 있습니다. | Microsoft Docs"
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
  - "vbc32120"
  - "bc32120"
helpviewer_keywords: 
  - "BC32120"
ms.assetid: c91f84a1-e61d-4b5f-8028-221e64ac044c
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;interfacename1&gt;&#39; 인터페이스를 상속할 수 없습니다. 이 인터페이스가 일부 형식 인수에 대해 &#39;&lt;interfacename2&gt;&#39; 인터페이스와 동일할 수 있습니다.
제네릭 인터페이스가 다른 제네릭 인터페이스에서 두 번 이상 상속하며, 형식 인수의 특정 값에 대해 두 상속이 충돌할 수 있습니다.  
  
 다음 문은 이 오류를 생성할 수 있습니다.  
  
 `Public Interface interfaceA(Of u)`  
  
 `End Interface`  
  
 `Public Interface derivedInterface(Of t1, t2)`  
  
 `Inherits interfaceA(Of t1), interfaceA(Of t2)`  
  
 `End Interface`  
  
 `derivedInterface`가 `t1` 및 `t2` 둘 다에 동일한 형식을 제공하여 생성 또는 구현된 경우 동일한 형식 인수를 사용하여 `interfaceA`의 두 버전을 상속해야 합니다. 이렇게 하면 액세스할 버전이 모호해집니다.  
  
 **오류 ID:** BC32120  
  
### 이 오류를 해결하려면  
  
-   충돌이 발생하지 않도록 파생된 인터페이스에 제공되는 형식 인수 중 하나를 변경합니다.  
  
     또는  
  
-   상속 또는 구현 충돌을 일으키는 인터페이스 중 하나를 `Inherits` 문에서 제거합니다.  
  
## 참고 항목  
 [빌드에 없음: 인터페이스 개요](http://msdn.microsoft.com/ko-kr/f96bb470-c1b8-4c73-89bc-6f536b798da1)   
 [Interface Statement](/dotnet/visual-basic/language-reference/statements/interface-statement)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)