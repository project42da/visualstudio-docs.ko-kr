---
title: "CA1410: COM 등록 메서드는 일치해야 합니다. | Microsoft Docs"
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
  - "CA1410"
  - "ComRegistrationMethodsShouldBeMatched"
helpviewer_keywords: 
  - "CA1410"
  - "ComRegistrationMethodsShouldBeMatched"
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1410: COM 등록 메서드는 일치해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ComRegistrationMethodsShouldBeMatched|  
|CheckId|CA1410|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 형식에서 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 특성으로 표시된 메서드를 정의하지만 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> 특성으로 표시된 메서드를 선언하지 않거나 그 반대의 경우입니다.  
  
## 규칙 설명  
 COM\(Component Object Model\) 클라이언트가 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 형식을 만들려면 해당 형식이 먼저 등록되어 있어야 합니다.  가능한 경우 등록 프로세스 동안 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 특성으로 표시된 메서드가 호출되어 사용자가 지정한 코드를 실행합니다.  등록 메서드의 작업을 되돌리려면 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> 특성으로 표시된 해당 메서드를 등록 프로세스 동안 호출합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 해당하는 등록 또는 등록 취소 메서드를 추가합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 형식을 보여 줍니다.  주석이 지정된 코드는 위반을 해결하는 방법을 나타냅니다.  
  
 [!code-cs[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]  
  
## 관련 규칙  
 [CA1411: COM 등록 메서드는 노출되면 안 됩니다.](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [COM에 어셈블리 등록](../Topic/Registering%20Assemblies%20with%20COM.md)   
 [Regasm.exe\(어셈블리 등록 도구\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md)