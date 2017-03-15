---
title: "모듈에 올바르지 않은 &lt;keyword&gt; 키워드가 사용되었습니다. | Microsoft Docs"
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
  - "vbc42028"
  - "BC42028"
helpviewer_keywords: 
  - "BC42028"
ms.assetid: a9bc1e9d-ba2c-4a71-b147-0fb66f670316
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 모듈에 올바르지 않은 &lt;keyword&gt; 키워드가 사용되었습니다.
모듈에 인스턴스가 없거나, 상속을 지원하지 않거나, 인터페이스를 구현하지 않습니다. 따라서 다음 키워드가 모듈 선언에 적용되지 않습니다.  
  
-   [MustInherit](/dotnet/visual-basic/language-reference/modifiers/mustinherit)  
  
-   [NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)  
  
-   [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)  
  
-   [Private](/dotnet/visual-basic/language-reference/modifiers/private)  
  
-   [Protected](/dotnet/visual-basic/language-reference/modifiers/protected)  
  
-   [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)  
  
-   [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)  
  
-   [Static](/dotnet/visual-basic/language-reference/modifiers/static)  
  
 [Module Statement](/dotnet/visual-basic/language-reference/statements/module-statement)에서는 [Public](/dotnet/visual-basic/language-reference/modifiers/public) 및 [Friend](/dotnet/visual-basic/language-reference/modifiers/friend) 키워드만 지원됩니다.  
  
 또한 모듈의 문 블록에서 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause) 문 또는 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)을 사용할 수 없습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42028  
  
### 이 오류를 해결하려면  
  
-   이 프로그래밍 요소를 모듈로 사용하려면 해당 선언에서 `Public` 또는 `Friend` 키워드만 사용합니다. 해당 액세스 수준을 지정하지 않은 경우 모듈에서는 기본적으로 `Friend`를 사용합니다.  
  
-   이 프로그래밍 요소의 인스턴스를 만들려는 경우 클래스로 선언합니다. 그런 다음 클래스 선언에 적용되는 키워드를 사용할 수 있습니다.  
  
## 참고 항목  
 [Class Statement](/dotnet/visual-basic/language-reference/statements/class-statement)