---
title: "CA2144: 투명 코드 어셈블리를 로드 해서는 바이트 배열에서 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6eb3b2ade52f0870240db1fac24f0ab3f6c6de17
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144: 투명 코드는 바이트 배열에서 어셈블리를 로드해서는 안 됩니다.
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|  
|CheckId|CA2144|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 투명 메서드는 다음 방법 중 하나를 사용 하는 바이트 배열에서 어셈블리를 로드:  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
## <a name="rule-description"></a>규칙 설명  
 투명 코드는 보안에 중요한 동작을 수행할 수 없기 때문에 투명 코드의 보안 검토는 중요 코드에 대한 보안 검토만큼 완벽하지 않습니다. 바이트 배열에서 로드된 어셈블리는 투명 코드에서 발견되지 않을 수 있으며 해당 바이트 배열은 감사할 필요가 없는 중요하거나 특히 안전에 중요한 코드를 포함할 수 있습니다. 따라서 투명 코드는 바이트 배열에서 어셈블리를 로드 해야 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 사용 하 여 어셈블리를 로드 하는 메서드를 표시는 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 투명 메서드는 바이트 배열에서 어셈블리를 로드 하기 때문에 다음 코드는 규칙은 됩니다.  
  
 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../code-quality/codesnippet/CSharp/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays_1.cs)]