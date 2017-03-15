---
title: "&#39;&lt;membername&gt;&#39; 멤버가 &#39;&lt;basetypename&gt;&#39; 기본 형식에서 &#39;&lt;membername&gt;&#39; 멤버와 충돌하므로 &#39;Overloads&#39;로 선언할 수 없습니다. | Microsoft Docs"
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
  - "bc40021"
  - "vbc40021"
helpviewer_keywords: 
  - "BC40021"
ms.assetid: 2ec72726-ab0e-4545-9c1e-2409eb54482e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;membername&gt;&#39; 멤버가 &#39;&lt;basetypename&gt;&#39; 기본 형식에서 &#39;&lt;membername&gt;&#39; 멤버와 충돌하므로 &#39;Overloads&#39;로 선언할 수 없습니다.
속성 또는 프로시저에서 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads) 키워드를 사용하여 동일한 이름의 기존 속성 또는 프로시저를 다시 선언하지만 기존 속성 또는 프로시저가 기본 클래스에 있습니다.  
  
 오버로드는 동일한 클래스에 있는 여러 버전의 속성 또는 프로시저 모두를 정의하는 데 사용됩니다. 기본 클래스 멤버가 이미 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)를 지정하지 않은 경우 기본 클래스 멤버의 추가 버전을 정의할 수 없습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40021  
  
### 이 오류를 해결하려면  
  
-   기본 클래스 멤버의 추가 버전을 정의하려고 하고 기본 클래스의 소스 코드에 액세스할 수 있는 경우 기본 클래스 정의에 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads) 키워드를 추가합니다.  
  
-   기본 클래스의 소스 코드에 액세스할 수 있는 권한이 없으면 파생 클래스에서 멤버를 오버로드할 수 없습니다.`Overloads` 키워드를 제거합니다.  
  
-   추가 버전을 정의하는 대신 기본 클래스 멤버를 바꾸려는 경우 `Overloads` 대신 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides) 키워드를 사용합니다.  
  
-   기본 클래스 멤버를 파생 클래스의 새 멤버로 숨기려면 `Overloads` 대신 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows) 키워드를 사용합니다.  
  
## 참고 항목  
 [Procedure Overloading](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)