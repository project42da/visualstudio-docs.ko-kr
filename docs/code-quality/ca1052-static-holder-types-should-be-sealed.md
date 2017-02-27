---
title: "CA1052: 정적 소유자 형식은 sealed여야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StaticHolderTypesShouldBeSealed"
  - "CA1052"
helpviewer_keywords: 
  - "CA1052"
  - "StaticHolderTypesShouldBeSealed"
ms.assetid: 51a3165d-781e-4a55-aa0d-ea25fee7d4f2
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 19
---
# CA1052: 정적 소유자 형식은 sealed여야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|StaticHolderTypesShouldBeSealed|  
|CheckId|CA1052|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 형식이 정적 멤버만 포함하며 [sealed](/dotnet/csharp/language-reference/keywords/sealed)\([NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)\) 한정자로 선언되지 않았습니다.  
  
## 규칙 설명  
 이 규칙에서는 정적 멤버만 포함하는 형식은 파생된 형식에서 재정의할 수 있는 기능을 제공하지 않기 때문에 상속될 수 없다고 가정합니다.  상속을 고려하지 않은 형식은 `sealed` 한정자로 표시하여 기본 형식으로 사용되지 않도록 해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 형식을 `sealed`로 표시합니다.  [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0 이하를 대상으로 하는 경우에는 형식을 `static`으로 표시하는 방법이 더 좋습니다.  이 방법을 사용하면 클래스가 만들어지지 않도록 하기 위해 private 생성자를 선언하지 않아도 됩니다.  
  
## 경고를 표시하지 않는 경우  
 형식을 상속 가능하도록 디자인한 경우에는 이 규칙에서 경고를 표시하지 않도록 설정합니다.  `sealed` 한정자가 없다는 것은 해당 형식을 기본 형식으로 사용할 수 있다는 의미합니다.  
  
## 규칙 위반 예  
  
### 설명  
 다음 예제에서는 규칙을 위반하는 형식을 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
 [!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
 [!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]  
  
## static 한정자를 사용한 해결 방법  
  
### 설명  
 다음 예제에서는 형식을 `static` 한정자로 표시하여 이 규칙 위반 문제를 해결하는 방법을 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Design.StaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_2.cs)]  
  
## 관련 규칙  
 [CA1053: 정적 소유자 형식에는 생성자를 사용하면 안 됩니다.](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)