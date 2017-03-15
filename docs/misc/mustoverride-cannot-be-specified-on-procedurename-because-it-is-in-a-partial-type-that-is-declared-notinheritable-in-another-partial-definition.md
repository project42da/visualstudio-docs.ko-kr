---
title: "&#39;MustOverride&#39;는 다른 부분 정의에서 &#39;NotInheritable&#39;로 선언된 부분 형식(Partial Type)에 속하므로 &lt;procedurename&gt;에 지정할 수 없습니다. | Microsoft Docs"
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
  - "vbc30927"
  - "BC30927"
helpviewer_keywords: 
  - "BC30927"
ms.assetid: 5798dfda-3d7b-4f30-9715-40cbf52d6dc4
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;MustOverride&#39;는 다른 부분 정의에서 &#39;NotInheritable&#39;로 선언된 부분 형식(Partial Type)에 속하므로 &lt;procedurename&gt;에 지정할 수 없습니다.
프로시저 또는 속성이 여러 partial 선언에서 정의된 클래스 내의 `MustOverride`로 선언되었지만 partial 선언 중 하나가 클래스에 대해 `NotInheritable`를 지정합니다.  
  
 여러 partial 선언에서 클래스의 정의를 나눌 때 컴파일러는 클래스를 모든 partial 선언의 공용 구조체로 처리합니다. 이는 멤버뿐만 아니라 구현, 상속 및 액세스 수준에도 적용됩니다.  
  
 프로시저 또는 속성은 클래스가 기본 클래스에서 상속해야 재정의할 수 있습니다. 따라서 기본 클래스의 프로시저 또는 속성에 대해 `MustOverride`를 지정하려면 클래스에 대해 `MustInherit`를 지정해야 합니다.`MustInherit`과 `NotInheritable`는 서로 모순되므로 동일한 클래스에 대해 둘 다 지정할 수 없습니다.  
  
 **오류 ID:** BC30927  
  
### 이 오류를 해결하려면  
  
-   속성이나 프로시저를 재정의해야 하는 경우에는 나타나는 partial 선언에서 `NotInheritable` 키워드를 제거합니다.  
  
-   클래스가 `NotInheritable`이어야 하는 경우에는 프로시저 또는 속성에서 `MustOverride` 키워드를 제거합니다. 클래스를 상속할 수 없으므로 재정의할 수 없습니다.  
  
## 참고 항목  
 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)   
 [MustOverride](/dotnet/visual-basic/language-reference/modifiers/mustoverride)   
 [MustInherit](/dotnet/visual-basic/language-reference/modifiers/mustinherit)   
 [NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)