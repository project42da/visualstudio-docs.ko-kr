---
title: "CA1411: COM 등록 메서드는 노출되면 안 됩니다. | Microsoft Docs"
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
  - "CA1411"
  - "ComRegistrationMethodsShouldNotBeVisible"
helpviewer_keywords: 
  - "ComRegistrationMethodsShouldNotBeVisible"
  - "CA1411"
ms.assetid: a59f96f1-1f38-4596-b656-947df5c55311
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1411: COM 등록 메서드는 노출되면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ComRegistrationMethodsShouldNotBeVisible|  
|CheckId|CA1411|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## 원인  
 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 또는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> 특성으로 표시된 메서드를 외부에서 볼 수 있습니다.  
  
## 규칙 설명  
 어셈블리가 COM\(Component Object Model\)에 등록될 때 레지스트리에 어셈블리의 각 COM 노출 형식에 대한 항목이 추가됩니다.  등록 및 등록 취소 프로세스 동안 각각 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 및 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> 특성으로 표시된 메서드가 호출되어 이들 형식의 등록\/등록 취소와 관련된 사용자 코드를 실행합니다.  이 코드는 이 프로세스 외부에서 호출되어서는 안 됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드의 액세스 가능성을 `private` 또는 `internal`\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `Friend`\)로 변경하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 두 메서드를 보여 줍니다.  
  
 [!code-cs[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/CSharp/ca1411-com-registration-methods-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/VisualBasic/ca1411-com-registration-methods-should-not-be-visible_1.vb)]  
  
## 관련 규칙  
 [CA1410: COM 등록 메서드는 일치해야 합니다.](../code-quality/ca1410-com-registration-methods-should-be-matched.md)  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [COM에 어셈블리 등록](../Topic/Registering%20Assemblies%20with%20COM.md)   
 [Regasm.exe\(어셈블리 등록 도구\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md)