---
title: "CA2111: 포인터 표시 되지 않음을 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PointersShouldNotBeVisible
- CA2111
helpviewer_keywords:
- CA2111
- PointersShouldNotBeVisible
ms.assetid: b3a8d466-895b-43bc-a2df-5d7058fe915f
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 31ae25892b6b5a153a0a4d1e52047eb5be2368d1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2111-pointers-should-not-be-visible"></a>CA2111: 포인터는 노출되면 안 됩니다.
|||  
|-|-|  
|TypeName|PointersShouldNotBeVisible|  
|CheckId|CA2111|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 Public 또는 protected A <xref:System.IntPtr?displayProperty=fullName> 또는 <xref:System.UIntPtr?displayProperty=fullName> 필드는 읽기 전용입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.IntPtr>및 <xref:System.UIntPtr> 관리 되지 않는 메모리에 액세스 하는 데 사용 되는 포인터 형식이 있습니다. 대 한 포인터를 없는 경우 private, internal 또는 읽기 전용 악성 코드가 메모리 내에서 임의의 위치에 액세스할 수 있게 되거나 응용 프로그램 또는 시스템 오류를 발생 포인터의 값을 변경할 수 있습니다.  
  
 참조 포인터 필드를 포함 하는 형식에 대 한 보안 액세스 하려는 경우 [CA2112: 보안된 형식은 필드를 노출 해야](../code-quality/ca2112-secured-types-should-not-expose-fields.md)합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 읽기 전용, 내부 또는 개인 하 여 포인터를 보호 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 포인터의 값에 의존 하지 않는 경우에이 규칙에서 경고를 표시 합니다.  
  
## <a name="example"></a>예  
 다음 코드를 위반 하 고 다음 규칙을 충족 하는 포인터를 보여 줍니다. Private이 아닌 포인터에 규칙을 위반할 수 공지 [CA1051: 표시 되는 인스턴스 필드를 선언 하지 마십시오](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)합니다.  
  
 [!code-csharp[FxCop.Security.PointersArePrivate#1](../code-quality/codesnippet/CSharp/ca2111-pointers-should-not-be-visible_1.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2112: 보안 형식은 필드를 노출하면 안 됩니다.](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
 [CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오.](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>