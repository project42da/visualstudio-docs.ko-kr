---
title: 'CA2232: Windows Forms 진입점 STAThread | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- MarkWindowsFormsEntryPointsWithStaThread
- CA2232
helpviewer_keywords:
- CA2232
- MarkWindowsFormsEntryPointsWithStaThread
ms.assetid: a3c95130-8e7f-4419-9fcd-b67d077e8efb
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2d28300d33d02fa4ca11ee1b7110a10a677b64bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2232-mark-windows-forms-entry-points-with-stathread"></a>CA2232: Windows Forms 진입점을 STAThread를 사용하여 표시하십시오.
|||  
|-|-|  
|TypeName|MarkWindowsFormsEntryPointsWithStaThread|  
|CheckId|CA2232|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 어셈블리 참조는 <xref:System.Windows.Forms> 네임 스페이스 및 해당 진입점으로 표시 되지 않은 <xref:System.STAThreadAttribute?displayProperty=fullName> 특성입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.STAThreadAttribute> COM 스레딩 모델이 응용 프로그램에 대 한 단일 스레드 아파트 임을 나타냅니다. 이 특성은 Windows Forms을 사용하는 응용 프로그램의 진입점에 있어야 합니다. 이 특성을 생략하면 Windows 구성 요소가 제대로 작동하지 않을 수 있습니다. 특성이 없으면 응용 프로그램에 Windows Forms에 대 한 지원 되지 않는 다중 스레드 아파트 모델을 사용 합니다.  
  
> [!NOTE]
>  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 응용 프로그램 프레임 워크를 사용 하는 프로젝트를 표시할 필요가 없습니다는 **Main** STAThread 사용 하 여 메서드. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러 자동으로 수행 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 추가 <xref:System.STAThreadAttribute> 진입점에 대 한 특성입니다. 경우는 <xref:System.MTAThreadAttribute?displayProperty=fullName> 특성이 있으면 제거 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 .NET Compact Framework에 대 한 개발 하는 경우이 규칙에서는 경고를에서 표시 하지 않는를 안전 하 게는 <xref:System.STAThreadAttribute> 특성은 불필요 한 지원 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 변수의 올바른 사용법을 보여 줍니다. <xref:System.STAThreadAttribute>합니다.  
  
 [!code-csharp[FxCop.Usage.StaThread#1](../code-quality/codesnippet/CSharp/ca2232-mark-windows-forms-entry-points-with-stathread_1.cs)]
 [!code-vb[FxCop.Usage.StaThread#1](../code-quality/codesnippet/VisualBasic/ca2232-mark-windows-forms-entry-points-with-stathread_1.vb)]