---
title: "CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2118
- ReviewSuppressUnmanagedCodeSecurityUsage
helpviewer_keywords:
- ReviewSuppressUnmanagedCodeSecurityUsage
- CA2118
ms.assetid: 4cb8d2fc-4e44-4dc3-9b74-7f5838827d41
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 92728eae21d4a3035f0396957fa643d14ef06e1c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2118-review-suppressunmanagedcodesecurityattribute-usage"></a>CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토하십시오.
|||  
|-|-|  
|TypeName|ReviewSuppressUnmanagedCodeSecurityUsage|  
|CheckId|CA2118|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 Public 또는 protected 형식이 나 멤버에는 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> 특성입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>COM interop 또는 플랫폼 호출을 사용 하 여 관리 되지 않는 코드를 실행 하는 멤버에 대 한 기본 보안 시스템 동작을 변경 합니다. 시스템에서는 일반적으로 [데이터 및 모델링](/dotnet/framework/data/index) 비관리 코드 권한이 대 한 합니다. 이 요청 된 멤버를 호출할 때마다 런타임 시 발생 하 고 권한에 대 한 호출 스택의 모든 호출자를 확인 합니다. 특성이 있는 경우 시스템에서는 한 [링크 요청](/dotnet/framework/misc/link-demands) 권한에 대 한: JIT 컴파일된 호출자가 직접 실행 호출자의 권한이 확인 됩니다.  
  
 이 특성은 기본적으로 성능 향상을 위해 사용되지만 성능이 향상되는 대신 중대한 보안 위험이 발생합니다. 네이티브 메서드를 호출 하는 공용 멤버에 특성을 배치 하는 경우 직접 실행 호출자) (제외 호출 스택의 호출자에 게 비관리 코드를 실행 하려면 비관리 코드 권한이 않아도 됩니다. Public 멤버의 작업 및 입력된 처리에 따라 해당 액세스 기능을 일반적으로 신뢰할 수 있는 코드 제한에 신뢰할 수 없는 호출자를 통합할 수 있습니다.  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 에서는 보안 검사를 호출자가 현재 프로세스의 주소 공간에 직접 액세스 하지 못하도록 합니다. 이 특성이 무시 일반적인 보안, 하 게 되므로 코드를 읽기 또는 쓰기 프로세스의 메모리를 사용할 수 있는 경우 심각한 위협을 발생 합니다. Note 위험 의도적으로 프로세스 메모리;에 대 한 액세스를 제공 하는 메서드가 제한 되지 않습니다 여기서 악성 코드가 액세스를 획득할 수 어떤 방법으로 예를 들어 놀라운 형식이 잘못 되거나 잘못 된 입력을 제공 하 여 모든 시나리오에 이기도 합니다.  
  
 기본 보안 정책은 로컬 컴퓨터에서 실행 하거나 다음 그룹 중 하나의 구성원 어셈블리에 비관리 코드 권한을 부여 하지 않습니다.  
  
-   내 컴퓨터 영역 코드 그룹이  
  
-   Microsoft 강력한 이름 코드 그룹  
  
-   ECMA 강력한 이름 코드 그룹  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 특성은 반드시 필요한 경우가 아니면 되도록 코드를 주의 깊게 검토 합니다. 관리 되는 코드 보안에 익숙하지 않은 하거나이 특성을 사용 하 여의 보안 의미를 이해 하지 않는 경우 사용자 코드에서 제거 합니다. 특성이 필요한 경우 호출자가 코드를 악의적으로 사용할 수 없는 확인 해야 합니다. 코드에 비관리 코드를 실행할 수 있는 권한이 없는 경우이 특성이 아무 효과가 없으며 제거 해야 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를에서 표시 하지 않으려면, 있는지 코드에서는 호출자 작업이 나 악용에서 사용할 수 있는 리소스에 대 한 액세스를 확인 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙을 위반 합니다.  
  
 [!code-csharp[FxCop.Security.TypesDoNotSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_1.cs)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `DoWork` 플랫폼 호출 메서드를 공개적으로 액세스할 수 있는 코드 경로 제공 하는 메서드 `FormatHardDisk`합니다.  
  
 [!code-csharp[FxCop.Security.PInvokeAndSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_2.cs)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 공용 메서드 `DoDangerousThing` 위반을 발생 합니다. 위반을 해결 하려면 `DoDangerousThing` private, 및 표시 된 것 처럼 보안 요청으로 보안 되는 공용 메서드를 통해 액세스할 수 있어야는 `DoWork` 메서드.  
  
 [!code-csharp[FxCop.Security.TypeInvokeAndSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_3.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName>   
 [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)   
 [보안 최적화](http://msdn.microsoft.com/en-us/cf255069-d85d-4de3-914a-e4625215a7c0)   
 [데이터 및 모델링](/dotnet/framework/data/index)  
 [링크 요구](/dotnet/framework/misc/link-demands)  
  