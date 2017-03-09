---
title: "액세스 가능한 모든 오버로드에 인수가 필요하므로 개체 이니셜라이저 식에서 &#39;&lt;propertyname&gt;&#39; 속성을 초기화할 수 없습니다. | Microsoft Docs"
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
  - "bc30993"
  - "vbc30993"
helpviewer_keywords: 
  - "BC30993"
ms.assetid: d4476065-2ca2-4c9e-a571-c08917a6387f
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 액세스 가능한 모든 오버로드에 인수가 필요하므로 개체 이니셜라이저 식에서 &#39;&lt;propertyname&gt;&#39; 속성을 초기화할 수 없습니다.
개체 이니셜라이저 목록에서 초기화된 멤버는 필드 또는 속성 중 하나여야 합니다. 또한 이니셜라이저 목록의 속성은 매개 변수를 가질 수 없습니다. 이 오류를 발생시키는 속성은 오버로드되며 해당하는 각 버전에 인수가 필요합니다. 따라서 개체 이니셜라이저 목록의 속성을 초기화할 수 없습니다.  
  
 **오류 ID:** BC30993  
  
### 이 오류를 해결하려면  
  
-   이니셜라이저 목록에서 인수를 필요로 하는 속성을 제거합니다.  
  
## 예제  
 다음 클래스에는 `TotalItems`에 대해 1개, `Item`\(오버로드됨\)에 대해 2개 등 총 3개의 속성 정의가 포함되어 있습니다.  
  
```  
Class CollectionOfItems Property TotalItems() As Integer Get End Get Set(ByVal value As Integer) End Set End Property Property Item(ByVal Key As String) As Object Get End Get Set(ByVal value As Object) End Set End Property Property Item(ByVal Index As Integer) As Object Get End Get Set(ByVal value As Object) End Set End Property End Class  
```  
  
 `TotalItems` 속성에는 인수가 필요하지 않으며 다음 선언과 같이 개체 초기화 목록에서 초기화될 수 있습니다.  
  
```  
Dim coinCollection As New CollectionOfItems With { .TotalItems = 0 }  
```  
  
 `Item` 속성은 오버로드되며 각 오버로드에는 인수가 필요합니다. 따라서 `Item`은 개체 이니셜라이저 목록에 나타날 수 없습니다.  
  
```  
' The following declaration is not valid. ' Dim coinCollection As New CollectionOfItems With { .TotalItems = 0, _ '    .Item = aCoinObject }  
```  
  
 이 오류를 방지하려면 개체 이니셜라이저 밖에서 `Item` 속성을 초기화합니다.  
  
```  
Dim coinCollection As New CollectionOfItems With { .TotalItems = 0 } coinCollection.Item(1) = aCoinObject  
```  
  
## 참고 항목  
 [빌드에 없음: 속성 및 속성 프로시저](http://msdn.microsoft.com/ko-kr/23e2a1ec-7e9d-4109-8940-c703d981077b)   
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [How to: Call a Property Procedure](../Topic/How%20to:%20Call%20a%20Property%20Procedure%20\(Visual%20Basic\).md)   
 [빌드에 없음: 기본 속성](http://msdn.microsoft.com/ko-kr/a70f2a27-8176-4858-935e-f25afdd43ab5)   
 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)   
 [Procedure Overloading](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)