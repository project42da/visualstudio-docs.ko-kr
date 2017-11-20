---
title: "CA2135: 수준 2 어셈블리 포함 되 면 안 LinkDemands | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2374b8de7e3d4f915f836f718b32dee028bee9ff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135: 수준 2 어셈블리는 LinkDemands를 포함해서는 안 됩니다.
|||  
|-|-|  
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|  
|CheckId|CA2135|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 클래스 또는 클래스 멤버를 사용 하는 한 <xref:System.Security.Permissions.SecurityAction> 수준 2 보안을 사용 하는 응용 프로그램에서 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 LinkDemands는 수준 2 보안 규칙 집합에서 사용되지 않습니다. LinkDemands를 사용 하 여 적시에 (JIT) 컴파일 시 보안을 적용를 하는 대신 메서드, 형식 및 필드와 표시는 <xref:System.Security.SecurityCriticalAttribute> 특성입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 제거의 <xref:System.Security.Permissions.SecurityAction> 형식 또는 멤버를 표시 하 고는 <xref:System.Security.SecurityCriticalAttribute> 특성입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Security.Permissions.SecurityAction> 제거 되어야 하며으로 표시 된 메서드는 <xref:System.Security.SecurityCriticalAttribute> 특성입니다.  
  
 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2135-level-2-assemblies-should-not-contain-linkdemands_1.cs)]