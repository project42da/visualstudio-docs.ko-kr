---
title: "CA2111: 포인터는 노출되면 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PointersShouldNotBeVisible"
  - "CA2111"
helpviewer_keywords: 
  - "CA2111"
  - "PointersShouldNotBeVisible"
ms.assetid: b3a8d466-895b-43bc-a2df-5d7058fe915f
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 14
---
# CA2111: 포인터는 노출되면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|PointersShouldNotBeVisible|  
|CheckId|CA2111|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected <xref:System.IntPtr?displayProperty=fullName> 또는 <xref:System.UIntPtr?displayProperty=fullName> 필드가 읽기 전용이 아닙니다.  
  
## 규칙 설명  
 <xref:System.IntPtr> 및 <xref:System.UIntPtr>는 관리되지 않는 메모리에 액세스하는 데 사용되는 포인터 형식입니다.  포인터가 전용, 내부 또는 읽기 전용이 아니면 악의적인 코드에서 포인터 값을 변경할 수 있습니다. 이렇게 되면 메모리 내 임의의 위치에 액세스할 수 있게 되거나 응용 프로그램 또는 시스템 오류를 발생시킬 수 있습니다.  
  
 포인터 필드가 들어 있는 형식에 대한 액세스에 보안을 적용하려면 [CA2112: 보안 형식은 필드를 노출하면 안 됩니다.](../code-quality/ca2112-secured-types-should-not-expose-fields.md)를 참조하십시오.  
  
## 위반 문제를 해결하는 방법  
 포인터를 읽기 전용, 내부 또는 전용으로 만들어 보호합니다.  
  
## 경고를 표시하지 않는 경우  
 포인터 값을 사용하지 않을 경우 이 규칙에서 경고를 표시하지 않습니다.  
  
## 예제  
 다음 코드에서는 규칙을 위반하는 포인터와 규칙을 만족하는 포인터를 보여 줍니다.  전용이 아닌 포인터도 [CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오.](../code-quality/ca1051-do-not-declare-visible-instance-fields.md) 규칙을 위반합니다.  
  
 [!code-cs[FxCop.Security.PointersArePrivate#1](../code-quality/codesnippet/CSharp/ca2111-pointers-should-not-be-visible_1.cs)]  
  
## 관련 규칙  
 [CA2112: 보안 형식은 필드를 노출하면 안 됩니다.](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
 [CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오.](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## 참고 항목  
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>