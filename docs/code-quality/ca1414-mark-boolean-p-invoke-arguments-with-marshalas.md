---
title: "CA1414: 부울 P/Invoke 인수를 MarshalAs로 표시하십시오. | Microsoft Docs"
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
  - "CA1414"
  - "MarkBooleanPInvokeArgumentsWithMarshalAs"
helpviewer_keywords: 
  - "CA1414"
  - "MarkBooleanPInvokeArgumentsWithMarshalAs"
ms.assetid: c0c84cf5-7701-4897-9114-66fc4b895699
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1414: 부울 P/Invoke 인수를 MarshalAs로 표시하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MarkBooleanPInvokeArgumentsWithMarshalAs|  
|CheckId|CA1414|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## 원인  
 플랫폼 호출 메서드 선언에 <xref:System.Boolean?displayProperty=fullName> 매개 변수나 반환 값이 포함되어 있지만 <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName> 특성이 매개 변수나 반환 값에 적용되지 않았습니다.  
  
## 규칙 설명  
 플랫폼 호출 메서드가 비관리 코드에 액세스하고 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 `Declare` 키워드 또는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>를 사용하여 선언되었습니다.  <xref:System.Runtime.InteropServices.MarshalAsAttribute>는 관리 코드와 관리되지 않는 코드 간에 데이터 형식을 변환하는 데 사용되는 마샬링 동작을 지정합니다.  <xref:System.Byte?displayProperty=fullName> 및 <xref:System.Int32?displayProperty=fullName>와 같은 여러 간단한 데이터 형식은 비관리 코드에서 한 가지로 표현되므로 해당 데이터 형식의 마샬링 동작을 지정할 필요가 없습니다. 즉, 공용 언어 런타임에서 자동으로 올바른 동작을 제공합니다.  
  
 <xref:System.Boolean> 데이터 형식은 비관리 코드에서 여러 가지로 표현됩니다.  <xref:System.Runtime.InteropServices.MarshalAsAttribute>를 지정하지 않은 경우 <xref:System.Boolean> 데이터 형식에 대한 기본 마샬링 동작은 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>입니다.  이것은 32비트 정수이며 일부 경우에는 적합하지 않습니다.  관리되지 않는 메서드에 필요한 부울 표현은 적절한 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>에 맞도록 결정해야 합니다.  UnmanagedType.Bool은 항상 4바이트인 Win32 BOOL 형식입니다.  C\+\+ `bool` 또는 기타 1바이트 형식에는 UnmanagedType.U1을 사용해야 합니다.  자세한 내용은 [Default Marshaling for Boolean Types](http://msdn.microsoft.com/ko-kr/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)을 참조하십시오.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Boolean> 매개 변수 또는 반환 값에 <xref:System.Runtime.InteropServices.MarshalAsAttribute>를 적용합니다.  특성의 값을 적절한 <xref:System.Runtime.InteropServices.UnmanagedType>으로 설정합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  기본 마샬링 동작이 적절하더라도 동작을 명시적으로 지정하면 코드 관리가 더 쉬워집니다.  
  
## 예제  
 다음 예제에서는 적절한 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성으로 표시된 두 개의 플랫폼 호출 메서드를 보여 줍니다.  
  
 [!code-cs[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CSharp/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cs)]
 [!code-vb[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/VisualBasic/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.vb)]
 [!code-cpp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CPP/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cpp)]  
  
## 관련 규칙  
 [CA1901: P\/Invoke 선언은 이식 가능해야 합니다.](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)  
  
 [CA2101: P\/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>   
 [Default Marshaling for Boolean Types](http://msdn.microsoft.com/ko-kr/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)   
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)