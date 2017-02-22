---
title: "CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1000"
  - "DoNotDeclareStaticMembersOnGenericTypes"
helpviewer_keywords: 
  - "CA1000"
  - "DoNotDeclareStaticMembersOnGenericTypes"
ms.assetid: 5c0da594-f8d0-4f40-953d-56bf7fbd2087
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotDeclareStaticMembersOnGenericTypes|  
|CheckId|CA1000|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 제네릭 형식에 `static`\(Visual Basic의 경우 `Shared`\) 멤버가 포함되어 있습니다.  
  
## 규칙 설명  
 제네릭 형식의 `static` 멤버를 호출할 때는 형식에 형식 인수를 지정해야 합니다.  유추를 지원하지 않는 제네릭 인스턴스 멤버를 호출할 때는 멤버에 형식 인수를 지정해야 합니다.  다음 호출에서 볼 수 있듯이 이들 두 경우에서 형식 인수를 지정하기 위한 구문은 서로 다르며 혼동하기 쉽습니다.  
  
```vb  
' Shared method in a generic type.  
GenericType(Of Integer).SharedMethod()  
  
' Generic instance method that does not support inference.  
someObject.GenericMethod(Of Integer)()  
```  
  
```c#  
// Static method in a generic type.  
GenericType<int>.StaticMethod();  
  
// Generic instance method that does not support inference.  
someObject.GenericMethod<int>();  
```  
  
 일반적으로 앞의 두 선언은 피해야 합니다. 즉, 멤버를 호출할 때 형식 인수를 지정할 필요가 없도록 해야 합니다.  이렇게 하면 제네릭의 멤버를 호출하는 구문이 제네릭이 아닌 멤버를 호출하는 구문과 차이가 없게 됩니다.  자세한 내용은 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)을 참조하십시오.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 정적 멤버를 제거하거나 인스턴스 멤버로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  제네릭을 이해하고 사용하기 쉬운 구문으로 제공하면 학습에 걸리는 시간이 줄어들고 더 많은 사용자가 새로운 라이브러리를 선택하게 됩니다.  
  
## 관련 규칙  
 [CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1002: 제네릭 목록을 노출하지 마십시오.](../Topic/CA1002:%20Do%20not%20expose%20generic%20lists.md)  
  
 [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](../Topic/CA1003:%20Use%20generic%20event%20handler%20instances.md)  
  
 [CA1007: 적합한 제네릭을 사용하십시오.](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## 참고 항목  
 [제네릭](/dotnet/csharp/programming-guide/generics/index)