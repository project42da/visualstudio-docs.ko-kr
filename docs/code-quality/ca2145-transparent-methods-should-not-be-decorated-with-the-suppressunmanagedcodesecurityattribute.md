---
title: 'CA2145: 투명 한 메서드에 적용 데코레이팅 해서는 안 됩니다는 SuppressUnmanagedCodeSecurityAttribute로 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c6fcfc32dc8ab8a90ea555f43c253a5d93e72a3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145: 투명한 메서드는 SuppressUnmanagedCodeSecurityAttribute로 데코레이팅해서는 안 됩니다.
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|  
|CheckId|CA2145|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 투명 한 메서드로 표시 된 메서드는 <xref:System.Security.SecuritySafeCriticalAttribute> 메서드 또는 메서드를 포함 하는 형식으로 표시 됩니다는 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 메서드에 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 암시적 LinkDemand가 호출 하는 메서드에 배치를 가져야 합니다. 이 LinkDemand는 호출 코드가 보안을 중요시 하도록 요구합니다. SuppressUnmanagedCodeSecurity를 사용 하는 메서드 표시는 <xref:System.Security.SecurityCriticalAttribute> 특성 하면이 요구 사항이 더욱 명확 하 게 메서드의 호출자입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면이 메서드를 표시 하거나와 입력는 <xref:System.Security.SecurityCriticalAttribute> 특성입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute_1.cs)]  
  
### <a name="comments"></a>설명