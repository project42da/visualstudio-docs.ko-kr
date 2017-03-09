---
title: "&#39;&lt;interfacename1&gt;.&lt;membername&gt;&#39; 구현이 일부 형식 인수에 대한 &#39;&lt;interfacename2&gt;.&lt;membername&gt;&#39; 구현과 충돌할 수 있으므로 이 인터페이스를 구현할 수 없습니다. | Microsoft Docs"
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
  - "bc32125"
  - "vbc32125"
helpviewer_keywords: 
  - "BC32125"
ms.assetid: 74321d27-4ff8-440c-b5de-d67e98fff274
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;interfacename1&gt;.&lt;membername&gt;&#39; 구현이 일부 형식 인수에 대한 &#39;&lt;interfacename2&gt;.&lt;membername&gt;&#39; 구현과 충돌할 수 있으므로 이 인터페이스를 구현할 수 없습니다.
클래스가 둘 이상의 제네릭 인터페이스를 구현하고 한 인터페이스가 다른 인터페이스에서 상속하므로 형식 인수의 특정 값에 대해 두 개의 인터페이스 멤버 구현이 충돌할 수 있습니다.  
  
 다음 문은 이 오류를 생성할 수 있습니다.  
  
```  
Public Interface iFace1(Of t) Sub testSub() End Interface Public Interface iFace2(Of u) Inherits iFace1(Of u) End Interface Public Class testClass(Of y, z) Implements iFace1(Of y), iFace2(Of z) Public Sub testSuby() Implements iFace1(Of y).testSub End Sub Public Sub testSubz() Implements iFace1(Of z).testSub End Sub End Class  
```  
  
 `iFace2`는 고유한 형식 매개 변수\(`u`\)를 사용하여 `iFace1`에서 상속하므로 동일한 형식 인수가 `y` 및 `z`에 전달된 경우 `testClass`는 동일한 서명으로 두 가지 버전의 `iFace1.testSub`를 구현합니다. 이 경우 액세스할 버전이 모호해집니다.  
  
 **오류 ID:** BC32125  
  
### 이 오류를 해결하려면  
  
-   두 개의 서로 다른 형식 인수로 `iFace1`을 구현할 수 없도록 인터페이스의 상속 구조를 변경합니다.  
  
     또는  
  
-   구현 충돌을 일으키는 인터페이스 중 하나를 `Implements` 문에서 제거합니다.  
  
## 참고 항목  
 [Class Statement](/dotnet/visual-basic/language-reference/statements/class-statement)   
 [Interface Statement](/dotnet/visual-basic/language-reference/statements/interface-statement)   
 [Implements Statement](/dotnet/visual-basic/language-reference/statements/implements-statement)   
 [빌드에 없음: Implements 키워드 및 Implements 문](http://msdn.microsoft.com/ko-kr/b96560f7-6413-480f-a1e2-f80253bab5be)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)