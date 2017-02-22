---
title: "CA2149: 투명한 메서드는 네이티브 코드를 호출해서는 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2149"
ms.assetid: 28951bd7-f3db-4871-99aa-bad68d1ead80
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2149: 투명한 메서드는 네이티브 코드를 호출해서는 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TransparentMethodsMustNotCallNativeCode|  
|CheckId|CA2149|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 메서드는 P\/Invoke 같은 메서드 스텁을 통해 네이티브 함수를 호출합니다.  
  
## 규칙 설명  
 이 규칙은 P\/Invoke를 통해 네이티브 코드를 직접 호출하는 모든 투명 메서드에 적용됩니다.  이 규칙 위반으로 인해 수준 2 투명성 모델에서 <xref:System.MethodAccessException>이 발생하고 수준 1 투명성 모델에서 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A>에 대한 완전 요청이 발생합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙의 위반 문제를 해결하려면 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성으로 네이티브 코드를 호출하는 메서드를 표시하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 [!code-cs[FxCop.Security.CA2149.TransparentMethodsMustNotCallNativeCode#1](../code-quality/codesnippet/CSharp/ca2149-transparent-methods-must-not-call-into-native-code_1.cs)]