---
title: "인수가 필요하므로 개체 이니셜라이저 식에서 &#39;&lt;propertyname&gt;&#39; 속성을 초기화할 수 없습니다. | Microsoft Docs"
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
  - "bc30992"
  - "vbc30992"
helpviewer_keywords: 
  - "BC30992"
ms.assetid: a4d050b2-7366-457a-a852-8eb490c97573
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 인수가 필요하므로 개체 이니셜라이저 식에서 &#39;&lt;propertyname&gt;&#39; 속성을 초기화할 수 없습니다.
개체 이니셜라이저 목록에서 초기화된 멤버는 필드 또는 속성이어야 하며, 속성 멤버에는 매개 변수를 사용할 수 없습니다. 예를 들어 기본 속성에는 인수가 필요하므로 개체 이니셜라이저 목록에서 초기화할 수 없습니다. 자세한 내용은 [빌드에 없음: 기본 속성](http://msdn.microsoft.com/ko-kr/a70f2a27-8176-4858-935e-f25afdd43ab5)을 참조하세요.  
  
 **오류 ID:** BC30992  
  
### 이 오류를 해결하려면  
  
-   인수를 포함하는 모든 속성을 초기화 목록에서 제거합니다.  
  
## 예제  
 다음 클래스에는 정수 인수가 필요한 기본 속성 `defaultProp`가 포함되어 있습니다.  
  
```  
Public Class SomeStrings Private myStrings() As String Sub New(ByVal size As Integer) ReDim myStrings(size) End Sub Default Property defaultProp(ByVal index As Integer) As String Get Return myStrings(index) End Get Set(ByVal Value As String) myStrings(index) = Value End Set End Property End Class  
```  
  
 기본 속성에 인수가 필요하기 때문에 다음 선언에서 오류가 발생합니다.  
  
```  
' Dim strs As New SomeStrings(2) With { .defaultProp = "One" }  
```  
  
## 참고 항목  
 [빌드에 없음: 기본 속성](http://msdn.microsoft.com/ko-kr/a70f2a27-8176-4858-935e-f25afdd43ab5)   
 [빌드에 없음: 속성 및 속성 프로시저](http://msdn.microsoft.com/ko-kr/23e2a1ec-7e9d-4109-8940-c703d981077b)   
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)