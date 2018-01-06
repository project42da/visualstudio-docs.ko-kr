---
title: "데이터의 사용자 지정 시각화 도우미를 만드는 | Microsoft Docs"
ms.custom: 
ms.date: 06/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.visualizer.troubleshoot
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers
ms.assetid: c24c006f-f2ac-429f-89db-677fc0c6e1ea
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 23985c56ba61e5a788232523611a48cfde902335
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="create-custom-visualizers-of-data"></a>데이터의 사용자 지정 시각화 도우미 만들기
 시각화 도우미는의 구성 요소는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 디버거 사용자 인터페이스입니다. A *시각화 도우미* 대화 상자나 다른 인터페이스의 데이터 형식에 적합 한 방식으로 변수나 개체를 표시 하려면를 만듭니다. 예를 들어 HTML 시각화 도우미는 HTML 문자열을 해석하고 브라우저 창에서와 마찬가지로 그 결과를 표시합니다. 비트맵 시각화 도우미는 비트맵 구조를 해석하고 그 구조가 표현하는 그래픽을 표시합니다. 일부 시각화 도우미에서는 데이터를 볼 수 있을 뿐만 아니라 수정할 수도 있습니다.

 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 디버거에는 6가지 표준 시각화 도우미가 포함되어 있습니다. 텍스트, HTML, XML 및 JSON 시각화 도우미, 문자열 개체에 사용 되는 WPF 트리 시각화 도우미는 WPF 개체 시각적 트리의 속성 표시 및 데이터 집합 시각화 도우미 DataSet, DataView 및 DataTable 개체에 대해 작동 합니다. 향후 Microsoft Corporation의 추가 시각화 도우미를 다운로드할 수 있으며 타사와 커뮤니티의 시각화 도우미도 사용 가능합니다. 또한 자신만의 시각화 도우미를 직접 작성하여 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 디버거에 설치할 수 있습니다.

 > [!NOTE]
 > 네이티브 코드에 대 한 사용자 지정 시각화 도우미를 만들려면 참조 된 [SQLite 네이티브 디버거 시각화 도우미](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/SqliteVisualizer) 샘플. UWP 및 Windows 8.x 앱에서 사용자 지정 시각화 도우미는 지원 되지 않습니다.

 디버거에서 시각화 도우미 돋보기 모양의 아이콘으로 표시 됩니다 ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "시각화 도우미 아이콘")합니다. 돋보기 아이콘을 표시 될 때는 **DataTip**, 같은 디버거 창에는 **조사식** 창 또는 **간략 한 조사식** 돋보기를 클릭 대화 상자 해당 개체의 데이터 형식에 적합 한 시각화 도우미를 선택 합니다.

## <a name="overview-of-custom-visualizers"></a>사용자 지정 시각화 도우미의 개요

<xref:System.Object> 또는 <xref:System.Array>를 제외한 모든 관리되는 클래스의 개체에 대해 사용자 지정 시각화 도우미를 작성할 수 있습니다.  
  
 디버거 시각화 도우미의 아키텍처는 두 부분으로 구성되어 있습니다.  
  
-   *디버거 쪽* Visual Studio 디버거 내에서 실행 됩니다. 디버거 쪽 코드에서는 시각화 도우미의 사용자 인터페이스를 만들고 표시합니다.  
  
-   *디버기 쪽* Visual Studio가 디버깅 하는 프로세스 내에서 실행 (의 *디버기*).  
  
 시각화하려는 데이터 개체(예: String 개체)는 디버기 프로세스에 있습니다. 따라서 디버기 쪽에서 디버거 쪽에 데이터 개체를 전달해야 디버거 쪽에서 작성된 사용자 인터페이스를 사용하여 이 개체를 표시할 수 있습니다.  
  
 디버거 쪽에서 시각화할이 데이터 개체를 수신는 *개체 공급자* 구현 하는 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> 인터페이스입니다. 디버기 쪽 코드를 통해 데이터 개체를 전달 된 *개체 소스*에서 파생 된 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>합니다. 개체 공급자는 데이터를 다시 개체 소스로 전달할 수도 있습니다. 이를 통해 데이터를 표시할 뿐만 아니라 편집도 하는 시각화 도우미를 작성할 수 있습니다. 식 계산기와 통신하고 궁극적으로는 개체 소스와 통신하도록 개체 공급자를 재정의할 수 있습니다.  
  
 디버기 쪽과 디버거 쪽에서는 <xref:System.IO.Stream>을 통해 서로 통신합니다. 데이터 개체를 <xref:System.IO.Stream>으로 serialize하고 <xref:System.IO.Stream>을 데이터 개체로 다시 deserialize하기 위한 메서드가 제공됩니다.  
  
 디버기 쪽 코드는 DebuggerVisualizer 특성(<xref:System.Diagnostics.DebuggerVisualizerAttribute>)을 사용하여 지정됩니다.  
  
 디버거 쪽에 시각화 도우미 사용자 인터페이스를 만들려면 <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>에서 상속되는 클래스를 만들고 인터페이스를 표시하도록 <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName> 메서드를 재정의해야 합니다.  
  
 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService>를 사용하여 시각화 도우미의 Windows Forms, 대화 상자 및 컨트롤을 표시할 수 있습니다.  
  
 제네릭 형식에 대한 지원은 제한되어 있습니다. 제네릭 형식이 개방형 형식인 경우에만 제네릭 형식을 대상으로 하는 시각화 도우미를 작성할 수 있습니다. `DebuggerTypeProxy` 특성을 사용하는 경우에도 이 제한은 동일하게 적용됩니다. 자세한 내용은 참조 [DebuggerTypeProxy 특성 사용 하 여](../debugger/using-debuggertypeproxy-attribute.md)합니다.  
  
 사용자 지정 시각화 도우미를 작성할 때는 보안 문제를 고려해야 합니다. 참조 [시각화 도우미 보안 고려 사항](../debugger/visualizer-security-considerations.md)합니다.  
  
 다음 절차에서는 시각화 도우미를 만들기 위해 수행해야 할 작업에 대한 간략한 개요를 제공합니다. 보다 자세한 설명을 참조 하십시오. [연습: C#에서 시각화 도우미 작성](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)합니다.  
  
### <a name="to-create-the-debugger-side"></a>디버거 쪽 코드를 만들려면  
  
1.  <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> 메서드를 사용하여 디버거 쪽에서 시각화되는 개체를 가져옵니다.  
  
2.  <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>에서 상속된 클래스를 만듭니다.  
  
3.  <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName> 메서드를 재정의하여 인터페이스를 표시합니다. <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> 메서드를 사용하여 Windows Forms, 대화 상자 및 컨트롤을 인터페이스의 일부로 표시합니다.  
  
4.  시각화 도우미(<xref:System.Diagnostics.DebuggerVisualizerAttribute>)를 제공하여 <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>를 적용합니다.  
  
### <a name="to-create-the-debuggee-side"></a>디버기 쪽 코드를 만들려면  
  
1.  시각화 도우미(<xref:System.Diagnostics.DebuggerVisualizerAttribute>)와 개체 소스(<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>)를 제공하여 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>를 적용합니다. 개체 소스를 제공하지 않으면 기본 개체 소스가 사용됩니다.  
  
2.  시각화 도우미에서 데이터 개체를 표시할 뿐만 아니라 편집할 수도 있도록 하려면 `TransferData`에서 `CreateReplacementObject` 또는 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource> 메서드를 재정의해야 합니다.   
  
## <a name="in-this-section"></a>섹션 내용
  
 [연습: C#에서 시각화 도우미 작성](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)  

 [연습: Visual Basic에서 시각화 도우미 작성](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)  
  
 [방법: 시각화 도우미 설치](../debugger/how-to-install-a-visualizer.md)  
  
 [방법: 시각화 도우미 테스트 및 디버그](../debugger/how-to-test-and-debug-a-visualizer.md)  
  
 [시각화 도우미 API 참조](../debugger/visualizer-api-reference.md)  
  
## <a name="related-sections"></a>관련 단원  
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)