---
title: "&lt;type1&gt; &#39;&lt;membername&gt;&#39;은 기본 &lt;type2&gt; &#39;&lt;classname&gt;&#39;에 선언된 오버로드 가능한 멤버를 숨깁니다. | Microsoft Docs"
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
  - "bc40003"
  - "vbc40003"
helpviewer_keywords: 
  - "BC40003"
ms.assetid: 1e0d2061-0ad9-4915-b946-d55cb5d5ee80
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;type1&gt; &#39;&lt;membername&gt;&#39;은 기본 &lt;type2&gt; &#39;&lt;classname&gt;&#39;에 선언된 오버로드 가능한 멤버를 숨깁니다.
\<type1\> '\<membername\>'은 기본 \<type2\> '\<classname\>'에 선언된 오버로드 가능한 멤버를 숨깁니다. 기본 메서드를 오버로드하려면 이 메서드를 'Overloads'로 선언해야 합니다.  
  
 파생 클래스가 기본 클래스에서 정의된 프로시저 또는 속성과 동일한 이름을 사용하여 `Function` 또는 `Sub` 프로시저 또는 `Property`을 정의합니다. 프로시저 및 속성이 오버로드 가능한 멤버이기 때문에 파생 클래스가 기본 클래스 멤버를 오버로드하거나 숨길 수 있습니다. 그러나 파생 클래스 코드는 선언에서 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads) 또는 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)를 지정하지 않습니다. 키워드가 없는 경우 컴파일러는 `Shadows`를 가정합니다.  
  
 `Overloads` 또는 `Shadows`를 지정하는 것이 좋은 프로그래밍 습관입니다. 그러면 코드를 더 쉽게 읽고 이해할 수 있습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40003  
  
### 이 오류를 해결하려면  
  
-   기본 클래스 메서드 또는 속성을 오버로드하려면 `Overloads` 키워드를 선언에 포함합니다.  
  
-   기본 클래스 메서드 또는 속성을 숨기려면 `Overloads` 대신 `Shadows` 키워드를 포함합니다.  
  
-   기본 클래스 멤버를 오버로드하거나 숨기지 않으려면 파생 클래스 멤버의 이름을 변경합니다.  
  
## 참고 항목  
 [Procedure Overloading](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)   
 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)   
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)   
 [Shadowing in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/shadowing)   
 [Function Statement](/dotnet/visual-basic/language-reference/statements/function-statement)   
 [Sub Statement](/dotnet/visual-basic/language-reference/statements/sub-statement)   
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)