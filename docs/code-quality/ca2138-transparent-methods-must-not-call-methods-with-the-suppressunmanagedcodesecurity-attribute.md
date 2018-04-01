---
title: 'CA2138: 투명 한 메서드는 SuppressUnmanagedCodeSecurity 특성으로 메서드를 호출 하지 해야 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2138
ms.assetid: a14c4d32-f079-4f3a-956c-a1657cde0f66
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0cef17ce232582cd23f961850bd52c048479e849
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute"></a>CA2138: 투명한 메서드는 SuppressUnmanagedCodeSecurity 특성을 가진 메서드를 호출해서는 안 됩니다.
|||  
|-|-|  
|TypeName|TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods|  
|CheckId|CA2138|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 로 표시 된 메서드를 호출 하는 보안 투명 메서드는 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙은 사용 하 여 예를 들어, 네이티브 코드를 직접 호출 하는 모든 투명 메서드에 P/Invoke를 통해 (플랫폼 호출)를 호출 합니다. 로 표시 된 P/Invoke 및 COM interop 메서드는 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> linkdemand 호출 하는 메서드의 대해 수행 되 고 결과 특성입니다. 보안 투명 코드는 LinkDemands를 충족할 수 없는, 때문에 코드 또한 호출할 수 없습니다 SuppressUnmanagedCodeSecurity 특성으로 표시 된 메서드나 SuppressUnmanagedCodeSecurity 특성으로 표시 되는 클래스의 메서드. 메서드는 실패 하거나 요구 한 완전 요청이 발생으로 변환 됩니다.  
  
 이 규칙 위반을 <xref:System.MethodAccessException> 수준 2 보안 투명도 모델에 대 한 완전 요청이 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> 수준 1 투명도 모델에 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 제거의 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성으로 메서드를 표시 하 고는 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[FxCop.Security.CA2138.TransparentMethodsMustNotCallSuppressUnmanagedCodeSecurityMethods#1](../code-quality/codesnippet/CSharp/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute_1.cs)]