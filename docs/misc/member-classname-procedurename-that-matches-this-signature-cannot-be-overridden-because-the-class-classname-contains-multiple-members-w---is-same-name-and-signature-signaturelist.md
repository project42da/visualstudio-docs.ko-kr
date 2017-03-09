---
title: "&#39;&lt;classname&gt;&#39;클래스에 이름과 서명이 같은 여러 멤버가 포함되어 있으므로 이 서명과 일치하는 &#39;&lt;classname&gt;.&lt;procedurename&gt;&#39; 멤버를 재정의할 수 없습니다. &lt;signaturelist&gt; | Microsoft Docs"
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
  - "bc30935"
  - "vbc30935"
helpviewer_keywords: 
  - "BC30935"
ms.assetid: 1165b630-668d-417d-9e18-9b8ffe7f6980
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;classname&gt;&#39;클래스에 이름과 서명이 같은 여러 멤버가 포함되어 있으므로 이 서명과 일치하는 &#39;&lt;classname&gt;.&lt;procedurename&gt;&#39; 멤버를 재정의할 수 없습니다. &lt;signaturelist&gt;
프로시저 또는 속성이 상속된 프로시저 또는 속성을 재정의하려고 하지만, 컴파일러가 이름과 서명이 같은 기본 프로시저 또는 속성 버전을 둘 이상 찾았습니다.  
  
 다음 기본 선언이 보여 주는 것처럼 이 오류는 생성된 제네릭 형식이 있는 경우에 발생할 수 있습니다.  
  
```  
Public Class baseClass(Of t) Public Overridable Sub doSomething(ByVal inputValue As String) End Sub Public Overridable Sub doSomething(ByVal inputValue As t) End Sub End Class Public Class derivedClass Inherits baseClass(Of String) Overrides Sub doSomething(ByVal inputValue As String) End Sub End Class  
```  
  
 `derivedClass`는 해당 형식 매개 변수 `t`에 `String`을 제공하는 `baseClass`를 상속하기 때문에 `derivedClass`에 관한 한 `baseClass`에 있는 두 버전의 `doSomething`은 동일한 서명을 사용합니다. 결과적으로 컴파일러가 어떤 버전을 재정의할지 확인할 수 없습니다.  
  
 **오류 ID:** BC30935  
  
### 이 오류를 해결하려면  
  
-   동일한 서명을 가진 멤버 프로시저 또는 속성이 하나 이상 발생하지 않도록 기본 클래스에 제공하는 형식 인수를 변경합니다.  
  
     또는  
  
-   사용하는 형식 인수 집합이 포함된 기본 클래스를 상속해야 하는 경우 이 오류 메시지에 언급된 프로시저 또는 속성을 재정의하지 마세요.  
  
## 참고 항목  
 [Overridable](/dotnet/visual-basic/language-reference/modifiers/overridable)   
 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides)   
 [빌드에 없음: 속성 및 메서드 재정의](http://msdn.microsoft.com/ko-kr/2167e8f5-1225-4b13-9ebd-02591ba90213)