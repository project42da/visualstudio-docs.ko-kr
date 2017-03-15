---
title: "CA1415: P/Invoke를 올바르게 선언하십시오. | Microsoft Docs"
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
  - "CA1415"
  - "DeclarePInvokesCorrectly"
helpviewer_keywords: 
  - "CA1415"
  - "DeclarePInvokesCorrectly"
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1415: P/Invoke를 올바르게 선언하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DeclarePInvokesCorrectly|  
|CheckId|CA1415|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경 아님 \- 매개 변수를 선언하는 P\/Invoke를 어셈블리 외부에서 볼 수 없는 경우  주요 변경 \- 매개 변수를 선언하는 P\/Invoke를 어셈블리 외부에서 볼 수 있는 경우|  
  
## 원인  
 플랫폼 호출 메서드가 잘못 선언되었습니다.  
  
## 규칙 설명  
 플랫폼 호출 메서드가 비관리 코드에 액세스하고 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 `Declare` 키워드 또는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>를 사용하여 선언되었습니다.  현재 이 규칙에서는 OVERLAPPED 구조체 매개 변수에 대한 포인터가 있는 Win32 함수를 대상으로 하는 플랫폼 호출 메서드 선언을 찾는데 해당 관리 매개 변수가 <xref:System.Threading.NativeOverlapped?displayProperty=fullName> 구조체에 대한 포인터가 아닙니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 플랫폼 호출 메서드를 올바르게 선언합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 플랫폼 호출 메서드와 이 규칙을 충족하는 플랫폼 호출 메서드를 보여 줍니다.  
  
 [!code-cs[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]  
  
## 참고 항목  
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)