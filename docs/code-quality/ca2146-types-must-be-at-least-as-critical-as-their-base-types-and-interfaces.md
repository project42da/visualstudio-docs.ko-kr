---
title: "CA2146: 형식은 최소한 기본 형식 및 인터페이스 만큼 중요 이어야 합니다 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2146
ms.assetid: 241fb784-1f6b-46e5-8ceb-c438e341d38e
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8e4cd4eb0d6313986316f01428179e73006fc449
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces"></a>CA2146: 형식은 최소한 기본 형식 및 인터페이스만큼 중요해야 합니다.
|||  
|-|-|  
|TypeName|TypesMustBeAtLeastAsCriticalAsBaseTypes|  
|CheckId|CA2146|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 투명 형식으로 표시 되는 형식에서 파생 되는 <xref:System.Security.SecuritySafeCriticalAttribute> 또는 <xref:System.Security.SecurityCriticalAttribute>, 또는 형식으로 표시 된는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 표시 되는 형식에서 파생 되는 <xref:System.Security.SecurityCriticalAttribute> 특성.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙은 파생 형식에 기본 형식 또는 구현된 인터페이스만큼 중요하지 않은 보안 투명성 특성이 있을 때 적용됩니다. 중요한 기본 형식에서 파생되거나 중요한 인터페이스를 구현할 수 있는 것은 중요한 형식뿐이고, 안전에 중요한 기본 형식에서 파생되거나 안전에 중요한 인터페이스를 구현할 수 있는 것은 중요하거나 안전에 중요한 형식뿐입니다. 수준 2 투명도에이 규칙의 위반 사항이 발생 한 <xref:System.TypeLoadException> 파생된 형식에 대 한 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 위반으로이 인해를 해결 하려면 최소한 기본 형식이 나 인터페이스 만큼 중요 한 투명도 특성 구현 또는 파생 형식을 표시 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[FxCop.Security.CA2146.TypesMustBeAtLeastAsCriticalAsBaseTypes#1](../code-quality/codesnippet/CSharp/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces_1.cs)]