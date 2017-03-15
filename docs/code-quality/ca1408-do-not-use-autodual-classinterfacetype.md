---
title: "CA1408: AutoDual ClassInterfaceType을 사용하지 마십시오. | Microsoft Docs"
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
  - "DoNotUseAutoDualClassInterfaceType"
  - "CA1408"
helpviewer_keywords: 
  - "CA1408"
  - "DoNotUseAutoDualClassInterfaceType"
ms.assetid: 60ca5e02-3c51-42dd-942b-4f950eecfa0f
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1408: AutoDual ClassInterfaceType을 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotUseAutoDualClassInterfaceType|  
|CheckId|CA1408|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## 원인  
 COM\(Component Object Model\) 노출 형식은 <xref:System.Runtime.InteropServices.ClassInterfaceType>의 `AutoDual` 값으로 설정한 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> 특성으로 표시되어 있습니다.  
  
## 규칙 설명  
 이중 인터페이스를 사용하는 형식에서는 클라이언트가 특정 인터페이스 레이아웃에 바인딩할 수 있습니다.  이후 버전에서 해당 형식이나 기본 형식의 레이아웃이 변경되면 인터페이스에 바인딩된 COM 클라이언트의 바인딩이 해제될 수 있습니다.  기본적으로 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> 특성이 지정되어 있지 않으면 디스패치 전용 인터페이스가 사용됩니다.  
  
 따로 표시되지 않은 경우 제네릭이 아닌 모든 public 형식은 COM에서 볼 수 있으며 public이 아닌 모든 제네릭 형식은 COM에서 볼 수 없습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> 특성의 값을 <xref:System.Runtime.InteropServices.ClassInterfaceType>의 `None` 값으로 변경하고 인터페이스를 명시적으로 정의합니다.  
  
## 경고를 표시하지 않는 경우  
 해당 형식과 기본 형식의 레이아웃이 이후 버전에서 확실하게 변경되지 않을 경우에만 이 규칙에서 경고를 표시하지 마십시오.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 클래스와 명시적 인터페이스를 사용하도록 클래스를 다시 선언하는 방법을 보여 줍니다.  
  
 [!code-cs[FxCop.Interoperability.AutoDual#1](../code-quality/codesnippet/CSharp/ca1408-do-not-use-autodual-classinterfacetype_1.cs)]
 [!code-vb[FxCop.Interoperability.AutoDual#1](../code-quality/codesnippet/VisualBasic/ca1408-do-not-use-autodual-classinterfacetype_1.vb)]  
  
## 관련 규칙  
 [CA1403: 자동 레이아웃 형식은 COM 노출이면 안 됩니다.](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)  
  
 [CA1412: ComSource 인터페이스를 IDispatch로 표시하십시오.](../code-quality/ca1412-mark-comsource-interfaces-as-idispatch.md)  
  
## 참고 항목  
 [Introducing the Class Interface](http://msdn.microsoft.com/ko-kr/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [상호 운용할 .NET 형식의 정규화](../Topic/Qualifying%20.NET%20Types%20for%20Interoperation.md)   
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)