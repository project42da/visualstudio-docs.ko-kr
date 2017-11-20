---
title: "CA2205: 사용 하 여 관리 되는 Win32 API의 해당 항목 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
helpviewer_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
ms.assetid: 1c65ab59-3e50-4488-a727-3969c7f6cbe4
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cbdc02843d0a2982a129dafd5948a4c1ab287427
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2205-use-managed-equivalents-of-win32-api"></a>CA2205: Win32 API에 있는 동일한 기능의 관리되는 항목을 사용하십시오.
|||  
|-|-|  
|TypeName|UseManagedEquivalentsOfWin32Api|  
|CheckId|CA2205|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 플랫폼 호출 메서드가 정의 되었고 이와 동일한 기능을 사용 하 여 메서드에 존재는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 플랫폼 호출 메서드는 관리 되지 않는 DLL 함수를 호출 하는 데 사용 되 고 사용 하 여 정의 되는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 특성 또는 `Declare` Visual basic에서 키워드. 잘못 정의 된 플랫폼 호출 메서드 잘못 된 매개 변수 및 반환 값 데이터 형식 및 호출 규칙 및 문자 등의 잘못 된 필드 사양 매핑 이름이 잘못 지정 된 함수 등의 문제로 인해 런타임 예외가 발생할 수 있습니다 설정 합니다. 사용 가능한 경우 일반적으로 간단 하 고 덜 오류 정의 하 고 관리 되지 않는 메서드를 직접 호출 보다 관리 되는 해당 하는 메서드를 호출 하는 경향이입니다. 메서드를 호출 하는 플랫폼 호출 또한 해결 해야 하는 추가 보안 문제가 발생할 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 관리 되는 해당 하는 호출 하 여 관리 되지 않는 함수에 대 한 호출을 바꿉니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 제안된 된 대체 메서드가 필요한 기능을 제공 하지 않는 경우에이 규칙에서 경고를 표시 합니다.  
  
## <a name="example"></a>예제  
 플랫폼에는 다음 예제와 규칙을 위반 하는 메서드 정의 호출 합니다. 또한 플랫폼에 대 한 호출 메서드를 호출 하 고 해당 하는 관리 되는 메서드 표시 됩니다.  
  
 [!code-csharp[FxCop.Usage.ManagedEquivalents#1](../code-quality/codesnippet/CSharp/ca2205-use-managed-equivalents-of-win32-api_1.cs)]
 [!code-vb[FxCop.Usage.ManagedEquivalents#1](../code-quality/codesnippet/VisualBasic/ca2205-use-managed-equivalents-of-win32-api_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1404: P/Invoke 다음에 바로 GetLastError를 호출 합니다.](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)  
  
 [CA1060: 이동 P/Invoke를 NativeMethods 클래스로](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)  
  
 [P/Invoke 진입점 ca1400:](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)  
  
 [CA1401: P/Invoke는 노출 되지](../code-quality/ca1401-p-invokes-should-not-be-visible.md)  
  
 [CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정 하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)