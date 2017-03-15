---
title: "CA1404: P/Invoke 다음에 바로 GetLastError를 호출하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CallGetLastErrorImmediatelyAfterPInvoke"
  - "CA1404"
helpviewer_keywords: 
  - "CallGetLastErrorImmediatelyAfterPInvoke"
  - "CA1404"
ms.assetid: 52ae9eff-50f9-4b2f-8039-ca7e49fba88e
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 18
---
# CA1404: P/Invoke 다음에 바로 GetLastError를 호출하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|CallGetLastErrorImmediatelyAfterPInvoke|  
|CheckId|CA1404|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A?displayProperty=fullName> 메서드 또는 이와 동일한 기능의 Win32 `GetLastError` 함수를 호출하였으며 직전의 호출이 플랫폼 호출 메서드에 대한 호출이 아닙니다.  
  
## 규칙 설명  
 플랫폼 호출 메서드가 비관리 코드에 액세스하고 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 `Declare` 키워드 또는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 특성을 사용하여 선언되었습니다.  일반적으로 실패가 발생하면 관리되지 않는 함수는 Win32 `SetLastError` 함수를 호출하여 실패와 연관된 오류 코드를 설정합니다.  실패한 함수의 호출자는 Win32 `GetLastError` 함수를 호출하여 오류 코드를 검색하고 실패의 원인을 확인합니다.  오류 코드는 스레드 단위로 유지되며 다음에 `SetLastError`가 호출되면 이 오류 코드가 덮어쓰여집니다.  실패한 플랫폼 호출 메서드를 호출한 후에는 관리 코드에서 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 메서드를 호출하여 오류 코드를 검색할 수 있습니다.  다른 관리되는 클래스 라이브러리 메서드의 내부 호출이 오류 코드를 덮어쓸 수 있기 때문에 플랫폼 호출 메서드를 호출한 직후 `GetLastError` 또는 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 메서드를 호출해야 합니다.  
  
 이 규칙에서는 다음 관리되는 멤버에 대한 호출이 플랫폼 호출 메서드에 대한 호출과 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>에 대한 호출 사이에 발생한 경우 이들 관리되는 멤버에 대한 호출을 무시합니다.  이들 멤버는 오류 코드를 변경하지 않으며 일부 플랫폼 호출 메서드 호출의 성공을 확인하는 데 유용합니다.  
  
-   <xref:System.IntPtr.Zero?displayProperty=fullName>  
  
-   <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>  
  
-   <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>  
  
-   <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>에 대한 호출을 플랫폼 호출 메서드에 대한 호출의 바로 뒤로 이동합니다.  
  
## 경고를 표시하지 않는 경우  
 플랫폼 호출 메서드 호출과 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 메서드 호출 사이의 코드가 명시적이나 암시적으로 오류 코드를 변경할 수 없는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 메서드와 규칙을 충족하는 메서드를 보여 줍니다.  
  
 [!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/VisualBasic/ca1404-call-getlasterror-immediately-after-p-invoke_1.vb)]
 [!code-cs[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/CSharp/ca1404-call-getlasterror-immediately-after-p-invoke_1.cs)]  
  
## 관련 규칙  
 [CA1060: P\/Invoke를 NativeMethods 클래스로 이동](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)  
  
 [CA1400: P\/Invoke 진입점이 있어야 합니다.](../Topic/CA1400:%20P-Invoke%20entry%20points%20should%20exist.md)  
  
 [CA1401: P\/Invoke는 노출되지 않아야 합니다.](../Topic/CA1401:%20P-Invokes%20should%20not%20be%20visible.md)  
  
 [CA2101: P\/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)  
  
 [CA2205: Win32 API에 있는 동일한 기능의 관리되는 항목을 사용하십시오.](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)