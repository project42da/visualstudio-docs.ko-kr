---
title: "CA2205: Win32 API에 있는 동일한 기능의 관리되는 항목을 사용하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "UseManagedEquivalentsOfWin32Api"
  - "CA2205"
helpviewer_keywords: 
  - "CA2205"
  - "UseManagedEquivalentsOfWin32Api"
ms.assetid: 1c65ab59-3e50-4488-a727-3969c7f6cbe4
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2205: Win32 API에 있는 동일한 기능의 관리되는 항목을 사용하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UseManagedEquivalentsOfWin32Api|  
|CheckId|CA2205|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 플랫폼 호출 메서드가 정의되었고 이와 동일한 기능을 수행하는 메서드가 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리에 있습니다.  
  
## 규칙 설명  
 플랫폼 호출 메서드는 모든 관리되지 않는 DLL 함수의 호출에 사용되며 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 특성이나 Visual Basic의 `Declare` 키워드를 통해 정의됩니다.  잘못 정의된 플랫폼 호출 메서드는 이름이 잘못 지정된 함수, 매개 변수와 반환 값 데이터 형식의 잘못된 매핑, 올바르지 않은 필드 사양\(예: 호출 규칙 및 문자 집합\) 등의 문제로 인해 런타임 예외를 발생시킬 수 있습니다.  가능한 경우 관리되지 않는 메서드를 직접 정의하고 호출하는 것보다 동일한 기능의 관리되는 메서드를 호출하는 것이 일반적으로 더 간단하고 오류 발생 가능성도 더 낮습니다.  또한 플랫폼 호출 메서드를 호출하면 처리해야 할 추가적인 보안 문제가 발생할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 관리되지 않는 함수에 대한 호출을 동일한 기능의 해당 관리 항목에 대한 호출로 바꾸십시오.  
  
## 경고를 표시하지 않는 경우  
 제안된 대체 메서드가 필요한 기능을 제공하지 않을 경우에는 이 규칙에서 경고를 표시하지 마십시오.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 플랫폼 호출 메서드 정의를 보여 줍니다.  또한 플랫폼 호출 메서드와 함께 동일한 기능의 관리되는 메서드에 대한 호출을 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.ManagedEquivalents#1](../code-quality/codesnippet/CSharp/ca2205-use-managed-equivalents-of-win32-api_1.cs)]
 [!code-vb[FxCop.Usage.ManagedEquivalents#1](../code-quality/codesnippet/VisualBasic/ca2205-use-managed-equivalents-of-win32-api_1.vb)]  
  
## 관련 규칙  
 [CA1404: P\/Invoke 다음에 바로 GetLastError를 호출하십시오.](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)  
  
 [CA1060: P\/Invoke를 NativeMethods 클래스로 이동](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)  
  
 [CA1400: P\/Invoke 진입점이 있어야 합니다.](../Topic/CA1400:%20P-Invoke%20entry%20points%20should%20exist.md)  
  
 [CA1401: P\/Invoke는 노출되지 않아야 합니다.](../Topic/CA1401:%20P-Invokes%20should%20not%20be%20visible.md)  
  
 [CA2101: P\/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)