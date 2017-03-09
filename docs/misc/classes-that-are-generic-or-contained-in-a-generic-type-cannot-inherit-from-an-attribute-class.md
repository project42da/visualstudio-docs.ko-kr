---
title: "제네릭 또는 제네릭 형식에 포함된 클래스는 특성 클래스에서 상속할 수 없습니다. | Microsoft Docs"
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
  - "vbc32074"
  - "BC32074"
helpviewer_keywords: 
  - "BC32074"
ms.assetid: 3552ac98-d86a-4962-9d51-b9a8acc38ea1
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제네릭 또는 제네릭 형식에 포함된 클래스는 특성 클래스에서 상속할 수 없습니다.
제네릭 또는 제네릭 형식 내에 중첩된 클래스는 특성 클래스에서 상속하도록 지정합니다.  
  
 Visual Basic 및 .NET Framework는 현재 특성과 제네릭 형식의 조합을 지원하지 않습니다. 즉, 다음 제한 사항이 적용됩니다.  
  
-   특성은 제네릭 형식이거나 제네릭 형식 내에서 선언될 수 없습니다.  
  
-   특성이 제네릭 클래스에서 상속할 수 없고 제네릭 클래스를 특성에서 상속할 수도 없습니다.  
  
-   특성을 적용하는 경우 다음 중 하나에 해당하는 인수를 제공할 수 없습니다.  
  
    -   제네릭 형식,  
  
    -   제네릭 형식에서 생성되는 형식,  
  
    -   포함 형식의 형식 매개 변수 또는  
  
    -   포함 형식의 형식 매개 변수에서 생성되는 형식  
  
 **오류 ID:** BC32074  
  
### 이 오류를 해결하려면  
  
-   기본 클래스를 특성 클래스 이외의 다른 값으로 변경하거나 `Inherits` 문을 완전히 제거합니다.  
  
## 참고 항목  
 <xref:System.Attribute>   
 [빌드에 없음: Visual Basic의 특성 개요](http://msdn.microsoft.com/ko-kr/0d0cff64-892d-4f57-83bd-bef388553d4f)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)