---
title: "CA1412: ComSource 인터페이스를 IDispatch로 표시하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MarkComSourceInterfacesAsIDispatch"
  - "CA1412"
helpviewer_keywords: 
  - "CA1412"
  - "MarkComSourceInterfacesAsIDispatch"
ms.assetid: 131a7563-0410-443c-a8f5-52104250cfb4
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1412: ComSource 인터페이스를 IDispatch로 표시하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MarkComSourceInterfacesAsIDispatch|  
|CheckId|CA1412|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## 원인  
 형식이 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> 특성으로 표시되어 있으며 하나 이상의 지정된 인터페이스가 <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> 특성이 `InterfaceIsDispatch` 값으로 설정된 것으로 표시되어 있지 않습니다.  
  
## 규칙 설명  
 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>는 클래스가 COM\(Component Object Model\) 클라이언트에 노출시키는 이벤트 인터페이스를 식별하는 데 사용됩니다.  이들 인터페이스가 `InterfaceIsIDispatch`로 노출되어야 Visual Basic 6 COM 클라이언트가 이벤트 알림을 받을 수 있습니다.  기본적으로 인터페이스가 <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> 특성으로 표시되어 있지 않으면 이중 인터페이스로 노출됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> 특성을 추가하거나 수정하여 해당 특성의 값이 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> 특성으로 지정된 모든 인터페이스에 대해 InterfaceIsIDispatch로 설정되도록 합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 인터페이스 중 하나가 규칙을 위반하는 클래스를 보여 줍니다.  
  
 [!code-cs[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/CSharp/ca1412-mark-comsource-interfaces-as-idispatch_1.cs)]
 [!code-vb[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/VisualBasic/ca1412-mark-comsource-interfaces-as-idispatch_1.vb)]  
  
## 관련 규칙  
 [CA1408: AutoDual ClassInterfaceType을 사용하지 마십시오.](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)  
  
## 참고 항목  
 [How to: Raise Events Handled by a COM Sink](http://msdn.microsoft.com/ko-kr/7c9944b2-e951-4c3e-a0a1-59b2ae37d7fd)   
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)