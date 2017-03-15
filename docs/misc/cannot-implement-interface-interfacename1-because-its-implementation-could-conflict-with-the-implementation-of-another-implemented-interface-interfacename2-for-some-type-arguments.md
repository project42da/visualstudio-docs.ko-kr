---
title: "&#39;&lt;interfacename1&gt;&#39; 인터페이스 구현이 일부 형식 인수에 대해 구현된 다른 인터페이스 &#39;&lt;interfacename2&gt;&#39;의 구현과 충돌할 수 있으므로 이 인터페이스를 구현할 수 없습니다. | Microsoft Docs"
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
  - "BC32072"
  - "vbc32072"
helpviewer_keywords: 
  - "BC32072"
ms.assetid: af1cc688-c8cf-4cb2-a8a9-310f5139fe7b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;interfacename1&gt;&#39; 인터페이스 구현이 일부 형식 인수에 대해 구현된 다른 인터페이스 &#39;&lt;interfacename2&gt;&#39;의 구현과 충돌할 수 있으므로 이 인터페이스를 구현할 수 없습니다.
클래스 선언에 두 개 이상의 인터페이스를 지정하는 `Implements` 문이 포함되어 있지만 하나 이상의 인터페이스가 제네릭이며 둘 이상의 구현이 형식 인수의 특정 값에 대해 충돌할 수 있습니다.  
  
 다음 문은 이 오류를 생성할 수 있습니다.  
  
```  
Public Interface iFace1 Sub testSub(ByVal arg As String) End Interface Public Interface iFace2(Of t) Sub testSub(ByVal arg As t) End Interface Public Class testClass Implements iFace1, iFace2(Of String) End Class  
```  
  
 `iFace2`가 `String`를 사용하여 생성되므로 `testClass`에서 서명이 동일한 두 버전의 `testSub`를 구현해야 합니다. 이렇게 하면 액세스할 버전이 모호해집니다.  
  
 **오류 ID:** BC32072  
  
### 이 오류를 해결하려면  
  
-   충돌이 발생하지 않도록 제네릭 인터페이스에 제공된 형식 인수를 변경합니다.  
  
     또는  
  
-   구현 충돌을 일으키는 인터페이스 중 하나를 `Implements` 문에서 제거합니다.  
  
## 참고 항목  
 [Class Statement](/dotnet/visual-basic/language-reference/statements/class-statement)   
 [Interface Statement](/dotnet/visual-basic/language-reference/statements/interface-statement)   
 [Implements Statement](/dotnet/visual-basic/language-reference/statements/implements-statement)   
 [빌드에 없음: Implements 키워드 및 Implements 문](http://msdn.microsoft.com/ko-kr/b96560f7-6413-480f-a1e2-f80253bab5be)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)