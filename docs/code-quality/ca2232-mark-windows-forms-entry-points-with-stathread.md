---
title: "CA2232: Windows Forms 진입점을 STAThread를 사용하여 표시하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MarkWindowsFormsEntryPointsWithStaThread"
  - "CA2232"
helpviewer_keywords: 
  - "CA2232"
  - "MarkWindowsFormsEntryPointsWithStaThread"
ms.assetid: a3c95130-8e7f-4419-9fcd-b67d077e8efb
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 16
---
# CA2232: Windows Forms 진입점을 STAThread를 사용하여 표시하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MarkWindowsFormsEntryPointsWithStaThread|  
|CheckId|CA2232|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 어셈블리가 <xref:System.Windows.Forms> 네임스페이스를 참조하고 해당 진입점이 <xref:System.STAThreadAttribute?displayProperty=fullName> 특성으로 표시되어 있지 않습니다.  
  
## 규칙 설명  
 <xref:System.STAThreadAttribute>는 응용 프로그램에 대한 COM 스레딩 모델이 단일 스레드 아파트임을 나타냅니다.  이 특성은 Windows Forms을 사용하는 응용 프로그램의 진입점에 있어야 합니다. 이 특성을 생략하면 Windows 구성 요소가 제대로 작동하지 않을 수 있습니다.  이 특성이 없으면 응용 프로그램에서는 Windows Forms에 지원되지 않는 다중 스레드 아파트 모델을 사용합니다.  
  
> [!NOTE]
>  응용 프로그램 프레임워크를 사용하는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 프로젝트에서는 **Main** 메서드를 STAThread로 표시할 필요가 없습니다.  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러에서 이 작업을 자동으로 수행합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 진입점에 <xref:System.STAThreadAttribute> 특성을 추가합니다.  <xref:System.MTAThreadAttribute?displayProperty=fullName> 특성이 있으면 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 <xref:System.STAThreadAttribute> 특성이 필요하지도 않고 지원되지도 않는 .NET Compact Framework용으로 개발할 경우에는 이 규칙에서 경고를 표시하지 않도록 설정해도 안전합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.STAThreadAttribute>의 올바른 사용법을 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.StaThread#1](../code-quality/codesnippet/CSharp/ca2232-mark-windows-forms-entry-points-with-stathread_1.cs)]
 [!code-vb[FxCop.Usage.StaThread#1](../code-quality/codesnippet/VisualBasic/ca2232-mark-windows-forms-entry-points-with-stathread_1.vb)]