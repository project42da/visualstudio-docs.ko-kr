---
title: "&#39;&lt;interfacename&gt;&#39; 인터페이스에 이름과 서명이 같은 여러 멤버가 포함되어 있으므로 이 서명과 일치하는 &#39;&lt;interfacename&gt;.&lt;procedurename&gt;&#39; 멤버를 구현할 수 없습니다. &lt;signaturelist&gt; | Microsoft Docs"
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
  - "vbc30937"
  - "bc30937"
helpviewer_keywords: 
  - "BC30937"
ms.assetid: e917d85e-95e0-431a-9d09-39ce5d4fc894
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;interfacename&gt;&#39; 인터페이스에 이름과 서명이 같은 여러 멤버가 포함되어 있으므로 이 서명과 일치하는 &#39;&lt;interfacename&gt;.&lt;procedurename&gt;&#39; 멤버를 구현할 수 없습니다. &lt;signaturelist&gt;
프로시저 또는 속성이 구현된 인터페이스에 정의된 프로시저 또는 속성을 구현하려고 시도하지만, 컴파일러가 이름과 서명이 같은 인터페이스 프로시저 또는 속성 버전을 둘 이상 찾았습니다.  
  
 다음 기본 선언이 보여 주는 것처럼 이 오류는 생성된 제네릭 형식이 있는 경우에 발생할 수 있습니다.  
  
```  
Public Interface baseInterface(Of t) Sub doSomething(ByVal inputValue As String) Sub doSomething(ByVal inputValue As t) End Class Public Class implementingClass Implements baseInterface(Of String) Sub doSomething(ByVal inputValue As String) _ Implements baseInterface(Of String).doSomething End Sub End Class  
```  
  
 `implementingClass`는 해당 형식 매개 변수 `t`에 `String`을 제공하는 `baseInterface`를 구현하기 때문에 `implementingClass`에 관한 한 `baseInterface`에 있는 두 버전의 `doSomething`은 동일한 서명을 사용합니다. 결과적으로 컴파일러가 어떤 버전을 구현할지 결정할 수 없습니다.  
  
 **오류 ID:** BC30937  
  
### 이 오류를 해결하려면  
  
-   동일한 서명을 가진 멤버 프로시저 또는 속성이 하나 이상 발생하지 않도록 기본 클래스에 제공하는 형식 인수를 변경합니다.  
  
     또는  
  
-   이 기본 클래스를 구현하지 마세요. 해당 멤버의 모든 항목을 구현해야 하기 때문에 현재 사용 중인 형식 인수 집합으로 기본 클래스를 구현할 수 없습니다.  
  
## 참고 항목  
 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause)   
 [Implements Statement](/dotnet/visual-basic/language-reference/statements/implements-statement)   
 [빌드에 없음: Implements 키워드 및 Implements 문](http://msdn.microsoft.com/ko-kr/b96560f7-6413-480f-a1e2-f80253bab5be)