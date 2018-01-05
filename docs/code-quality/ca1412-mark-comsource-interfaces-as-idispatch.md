---
title: "CA1412: ComSource 인터페이스 표시 IDispatch로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MarkComSourceInterfacesAsIDispatch
- CA1412
helpviewer_keywords:
- CA1412
- MarkComSourceInterfacesAsIDispatch
ms.assetid: 131a7563-0410-443c-a8f5-52104250cfb4
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b2523397f59affa2d7e1e60e69e7ba2047438135
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1412-mark-comsource-interfaces-as-idispatch"></a>CA1412: ComSource 인터페이스를 IDispatch로 표시하십시오.
|||  
|-|-|  
|TypeName|MarkComSourceInterfacesAsIDispatch|  
|CheckId|CA1412|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 형식으로 표시 됩니다는 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> 로 특성 및 지정 된 인터페이스를 하나 이상 표시 되지 않으면는 <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> 특성이로 설정 된 `InterfaceIsDispatch` 값.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>구성 요소 개체 모델 (COM) 클라이언트에 클래스 노출 하는 이벤트 인터페이스를 식별 하는 데 사용 됩니다. 이러한 인터페이스는으로 노출 되어야 합니다 `InterfaceIsIDispatch` Visual Basic 6 COM 클라이언트에서 이벤트 알림을 받을 수 있도록 합니다. 인터페이스로 표시 되지 않으면 기본적으로는 <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> 특성을 인터페이스를 이중으로 노출 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 추가 하거나 수정는 <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> 특성 InterfaceIsIDispatch를 사용 하 여 지정한 모든 인터페이스에 대 한 해당 값이 설정의 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> 특성입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 규칙을 위반 하는 인터페이스 중 하나는 클래스를 보여 줍니다.  
  
 [!code-csharp[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/CSharp/ca1412-mark-comsource-interfaces-as-idispatch_1.cs)]
 [!code-vb[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/VisualBasic/ca1412-mark-comsource-interfaces-as-idispatch_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1408: AutoDual ClassInterfaceType을 사용하지 마십시오.](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)  
  
## <a name="see-also"></a>참고 항목  
 [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)