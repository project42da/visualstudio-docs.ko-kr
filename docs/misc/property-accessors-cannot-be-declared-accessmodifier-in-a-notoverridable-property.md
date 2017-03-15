---
title: "&#39;NotOverridable&#39; 속성에서는 속성 접근자를 &#39;&lt;accessmodifier&gt;&#39;로 선언할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31106"
  - "bc31106"
helpviewer_keywords: 
  - "BC31106"
ms.assetid: 84bcb157-9c33-4e4f-89a9-c5e6cb73028b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;NotOverridable&#39; 속성에서는 속성 접근자를 &#39;&lt;accessmodifier&gt;&#39;로 선언할 수 없습니다.
`NotOverridable` 속성의 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement) 또는 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)에 `Private` 키워드가 포함되어 있습니다.  
  
 다음 이유 줄에서는 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)에서 `NotOverridable` 및 `Private`를 결합할 수 없는 이유에 대해 설명합니다.  
  
1.  기본 클래스 속성 또는 프로시저를 재정의하지 않는 속성 또는 프로시저는 기본적으로 [NotOverridable](/dotnet/visual-basic/language-reference/modifiers/notoverridable)로 설정됩니다.  
  
2.  그러나 기본 클래스 속성 또는 프로시저를 재정의하는 파생 클래스의 속성 또는 프로시저는 기본적으로 [Overridable](/dotnet/visual-basic/language-reference/modifiers/overridable)로 설정됩니다. 재정의 계층 구조를 종료하려면 `NotOverridable`로 선언할 수 있습니다. 이것이 `NotOverridable`을 사용할 수 있는 유일한 컨텍스트입니다. 즉, `NotOverridable`을 사용하려면 반드시 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides)도 함께 사용해야 합니다.  
  
3.  기본 클래스 속성 또는 프로시저가 [Private](/dotnet/visual-basic/language-reference/modifiers/private)로 선언된 경우 액세스할 수 없으므로 파생 클래스에서 해당 속성이나 프로시저를 재정의할 수 없습니다. 그러므로 `Private`를 `Overridable`과 함께 사용할 수 없습니다.  
  
4.  속성 또는 프로시저를 재정의하려면 재정의하는 속성 또는 프로시저의 서명뿐 아니라 액세스 수준도 동일해야 합니다. 즉, 재정의 가능한 속성이나 프로시저에서 `Private`를 지정할 수 없으므로 재정의하는 속성 또는 프로시저에서 `Private`를 지정할 수 없습니다.  
  
5.  재정의하는 속성 또는 프로시저에서만 `NotOverridable`을 지정할 수 있으므로 `Private`와 함께 사용할 수 없습니다.  
  
 같은 이유로 재정의하는 속성의 개별 속성 프로시저\(`Get` 및 `Set`\)는 `Private`가 될 수 없습니다.  
  
 **오류 ID:** BC31106  
  
### 이 오류를 해결하려면  
  
-   `Get` 또는 `Set` 문에서 `Private` 키워드를 제거하거나 `Property` 문에서 `Overrides` 및 `NotOverridable` 키워드를 제거합니다.  
  
## 참고 항목  
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [Differences Between Shadowing and Overriding](/dotnet/visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)