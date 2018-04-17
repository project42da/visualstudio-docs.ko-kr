---
title: 'CA2142: 투명 코드 보호 해서는 안 됩니다 LinkDemands로 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c598a6aff671f0ce3ce489a203805e77eda7183
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: 투명한 코드는 LinkDemands를 사용하여 보호해서는 안 됩니다.
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|  
|CheckId|CA2142|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 투명 한 메서드를 사용 하려면 한 <xref:System.Security.Permissions.SecurityAction> 또는 다른 보안 요청이 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙은 액세스하는 데 LinkDemands가 필요한 투명한 메서드에 적용됩니다. 보안 투명 코드는 작업 보안을 확인할 책임이 없으므로 권한을 요구해서는 안 됩니다. 투명 한 메서드는 보안 중립 것인지, 때문에 이러한 내려서는 안 보안 의사 결정 합니다. 또한가 이전에 이러한 결정을 위해 투명 코드는 보안 결정을 안전 하 게 보호 중요 한 코드를 내리는 해야 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 투명 메서드에 링크 요청을 제거 하거나 표시 된 메서드에서 <xref:System.Security.SecuritySafeCriticalAttribute> 보안 요청과 같이 보안으로 수행 하는 특성을 검사 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙이 실행 방법에는 메서드는 투명 하 고 한 LinkDemand로 표시 <xref:System.Security.PermissionSet> 를 포함 하는 <xref:System.Security.Permissions.SecurityAction>합니다.  
  
 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2142-transparent-code-should-not-be-protected-with-linkdemands_1.cs)]  
  
 이 규칙에서는 경고를 표시해야 합니다.