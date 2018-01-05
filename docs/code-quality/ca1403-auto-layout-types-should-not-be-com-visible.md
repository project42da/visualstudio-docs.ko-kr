---
title: "CA1403: 자동 레이아웃 형식은 COM 안 표시 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AutoLayoutTypesShouldNotBeComVisible
- CA1403
helpviewer_keywords:
- CA1403
- AutoLayoutTypesShouldNotBeComVisible
ms.assetid: a7007714-f9b4-4730-94e0-67d3dc68991f
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7da04d7ecda3e47239bd865812c6fbd05428ac09
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1403-auto-layout-types-should-not-be-com-visible"></a>CA1403: 자동 레이아웃 형식은 COM 노출이면 안 됩니다.
|||  
|-|-|  
|TypeName|AutoLayoutTypesShouldNotBeComVisible|  
|CheckId|CA1403|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 구성 요소 개체 모델 (COM) 표시 값 형식으로 표시 됩니다는 <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=fullName> 특성이로 설정 <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=fullName>합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.Runtime.InteropServices.LayoutKind>레이아웃 형식은 공용 언어 런타임에 의해 관리 됩니다. 이러한 형식의 레이아웃 COM 클라이언트를 특정 레이아웃을 예상 하는.NET Framework의 버전 간에 변경할 수 있습니다. 되는 경우는 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 지정 하지 않으면 C#, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], c + + 컴파일러를 지정 하 고는 <xref:System.Runtime.InteropServices.LayoutKind> 값 형식에 대 한 레이아웃 합니다.  
  
 그렇지 않으면으로 표시 되지 않으면 모든 공용 제네릭이 아닌 형식은 COM에 표시 되지만; 모든 public이 아닌 및 제네릭 형식은 COM에 표시 됩니다. 그러나 거짓 긍정을 줄이기 위해이 규칙을 사용 하려면 명시적으로 지정 되어야; 형식의 COM 노출 여부 포함 하는 어셈블리 표시 되어야 합니다는 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 로 설정 `false` 형식으로 표시 해야 하 고는 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 로 설정 `true`합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 값의 변경 된 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 <xref:System.Runtime.InteropServices.LayoutKind> 또는 <xref:System.Runtime.InteropServices.LayoutKind>, 하거나 형식을 보이지 않는 com  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 규칙을 위반 하는 형식 및 규칙을 충족 하는 형식을 보여 줍니다.  
  
 [!code-csharp[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/CSharp/ca1403-auto-layout-types-should-not-be-com-visible_1.cs)]
 [!code-vb[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/VisualBasic/ca1403-auto-layout-types-should-not-be-com-visible_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1408: AutoDual ClassInterfaceType을 사용하지 마십시오.](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)  
  
## <a name="see-also"></a>참고 항목  
 [상호 운용할 .NET 형식의 정규화](/dotnet/framework/interop/qualifying-net-types-for-interoperation)   
 [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)