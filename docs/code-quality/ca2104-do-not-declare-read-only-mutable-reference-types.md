---
title: "CA2104: 변경 가능한 읽기 전용 참조 형식을 선언하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DoNotDeclareReadOnlyMutableReferenceTypes"
  - "CA2104"
helpviewer_keywords: 
  - "CA2104"
  - "DoNotDeclareReadOnlyMutableReferenceTypes"
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 18
---
# CA2104: 변경 가능한 읽기 전용 참조 형식을 선언하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|  
|CheckId|CA2104|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 외부에서 볼 수 있는 형식에 변경 가능한 참조 형식인, 외부에서 볼 수 있는 읽기 전용 필드가 포함되었습니다.  
  
## 규칙 설명  
 변경 가능한 형식은 해당 인스턴스 데이터를 수정할 수 있는 형식을 말합니다.  변경 가능한 참조 형식으로는 <xref:System.Text.StringBuilder?displayProperty=fullName> 클래스를 예로 들 수 있습니다.  여기에는 클래스의 인스턴스 값을 변경할 수 있는 멤버가 들어 있습니다.  변경할 수 없는 참조 형식으로는 <xref:System.String?displayProperty=fullName> 클래스를 예로 들 수 있습니다.  이 참조 형식이 인스턴스화된 이후에는 해당 값을 변경할 수 없습니다.  
  
 참조 형식 필드\(C\+\+에서는 포인터\)에 대한 읽기 전용 한정자\(C\#에서는 [readonly](/dotnet/csharp/language-reference/keywords/readonly), [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 [ReadOnly](/dotnet/visual-basic/language-reference/modifiers/readonly), C\+\+에서는 [const](/visual-cpp/cpp/const-cpp)\)는 필드가 참조 형식의 다른 인스턴스로 바뀌지 못하게 합니다.  그러나 한정자는 필드의 인스턴스 데이터가 참조 형식을 통해 수정되는 것을 금지하지 않습니다.  
  
 읽기 전용 배열 필드는 이 규칙에서 제외되지만 대신 [CA2105: 배열 필드는 읽기 전용이면 안 됩니다.](../code-quality/ca2105-array-fields-should-not-be-read-only.md) 규칙 위반을 발생시킵니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 읽기 전용 한정자를 제거하거나, 주요 변경이 허용되는 경우 필드를 변경할 수 없는 형식으로 바꿉니다.  
  
## 경고를 표시하지 않는 경우  
 필드 형식이 변경할 수 없는 형식인 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 이 규칙의 위반을 발생시키는 필드 선언을 보여 줍니다.  
  
 [!code-cpp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CPP/ca2104-do-not-declare-read-only-mutable-reference-types_1.cpp)]
 [!code-cs[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CSharp/ca2104-do-not-declare-read-only-mutable-reference-types_1.cs)]
 [!code-vb[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/VisualBasic/ca2104-do-not-declare-read-only-mutable-reference-types_1.vb)]