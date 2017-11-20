---
title: "CA2136: 멤버 해야 합니다. 충돌 하는 투명도 주석을 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2127
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2136
helpviewer_keywords:
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2127
ms.assetid: ff5a1d18-7c52-4da5-8990-60be83a8ea81
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 350504d6e49351e96aa1c986ddf08893dc490d69
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136: 멤버는 충돌하는 투명도 주석을 가져서는 안 됩니다.
|||  
|-|-|  
|TypeName|TransparencyAnnotationsShouldNotConflict|  
|CheckId|CA2136|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 이 규칙은 형식 멤버도 표시 되는 <xref:System.Security> 는 다른 보안 특성 멤버의 컨테이너의 투명도 가진 보안 특성입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 투명성 특성은 큰 범위의 코드 요소에서 작은 범위의 요소에 적용됩니다. 범위가 큰 코드 요소의 투명성 특성은 첫 번째 요소에 포함된 코드 요소의 투명성 특성보다 우선합니다. 예를 들어로 표시 된 클래스는 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시 된 메서드를 포함할 수 없습니다는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 위반으로이 인해를 해결 하려면 코드를 가진 요소를 더 낮은 범위에서 보안 특성을 제거 하거나 포함 하는 코드 요소와 동일 하 게 특성을 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서 경고를 표시 하지 마십시오.  
  
## <a name="example"></a>예제  
 메서드를로 다음 예에서 <xref:System.Security.SecuritySafeCriticalAttribute> 특성 되며로 표시 된 클래스의 멤버는 <xref:System.Security.SecurityCriticalAttribute> 특성입니다. 보안 안전 특성을 제거 해야 합니다.  
  
 [!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../code-quality/codesnippet/CSharp/ca2136-members-should-not-have-conflicting-transparency-annotations_1.cs)]