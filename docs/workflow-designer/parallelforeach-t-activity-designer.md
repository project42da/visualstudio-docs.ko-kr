---
title: "ParallelForEach&lt;T&gt; 활동 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.ParallelForEach`1.UI
ms.assetid: e93a4843-aef2-4d3e-9a0a-a2d3d1411aa7
caps.latest.revision: "9"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 56a20f6e29f0f1bd6e071e6d3b48442c0bf02e77
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="parallelforeachlttgt-activity-designer"></a>ParallelForEach&lt;T&gt; 활동 디자이너
<xref:System.Activities.Statements.ParallelForEach%601> 활동은 컬렉션의 요소를 열거하고 컬렉션의 각 요소에 대해 포함 문을 병렬로 실행합니다. 각 요소는 동일 스레드에서 비동기적입니다. <xref:System.Activities.Statements.Sequence> 활동의 자식 활동이 유휴 상태가 되는 경우 이 활동 대신 이 흐름 제어 활동을 사용합니다.  
  
 <xref:System.Activities.Statements.ParallelForEach%601> 활동에는 사용자가 지정한 <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> 식이 포함된 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 속성이 있습니다. <xref:System.Activities.Statements.ParallelForEach%601> 활동은 각 분기가 완료된 후 이 속성을 평가합니다. 로 평가 되 면 **true**, 하면 <xref:System.Activities.Statements.ParallelForEach%601> 활동이 다른 분기를 실행 하지 않고 완료 합니다. 경우는 <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> 계산 되지 않습니다 **true**, 하면 <xref:System.Activities.Statements.ParallelForEach%601> 자식 활동이 모두 완료 했을 때 활동이 완료 합니다.  
  
## <a name="the-parallelforeacht-activity"></a>ParallelForEach는 < T\> 활동  
 <xref:System.Activities.Statements.ParallelForEach%601>은 값을 열거하고 열거되는 모든 값에 대해 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>을 예약합니다. <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>만 예약합니다. <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>가 유휴 상태로 전환되는지 여부에 따라 본문의 실행 방법이 달라집니다.  
  
 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>가 유휴 상태로 전환되지 않는 경우에는 예약된 활동이 스택으로 처리되기 때문에 역순으로 실행됩니다. 즉, 마지막으로 예약된 활동이 가장 먼저 실행됩니다. 예를 들어, 1,2,3,4에 {} 컬렉션이 있고 <xref:System.Activities.Statements.ParallelForEach%601> 사용 및는 **WriteLine** 값을 쓰지 본문으로 합니다. 콘솔에는 4, 3, 2, 1로 출력됩니다. 때문에 이것이 **WriteLine** 4 후 하므로 유휴는 설명 하지 않습니다 **WriteLine** 스택 동작을 사용 하 여 스크립트가 실행 되지, 활동 예약 된 (마지막에 첫 번째).  
  
 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>에 유휴 상태로 전환될 수 있는 활동(예: <xref:System.ServiceModel.Activities.Receive> 활동 또는 <xref:System.Activities.Statements.Delay> 활동)이 있는 경우에는 활동이 완료될 때까지 기다릴 필요가 없습니다. <xref:System.Activities.Statements.ParallelForEach%601>은 예약된 다음 본문 활동으로 이동하여 해당 활동을 실행합니다. 이 활동도 유휴 상태가 될 경우 <xref:System.Activities.Statements.ParallelForEach%601>은 다시 다음 본문 활동으로 넘어갑니다.  
  
### <a name="using-the-parallelforeacht-activity-designer"></a>본문을 사용 하 여\<T > 활동 디자이너  
 **ParallelForEach\<T >** 활동 디자이너에서 확인할 수 있습니다는 **제어 흐름** 의 범주는 **도구 상자**는 를클릭하여액세스 **도구 상자** 탭의 왼쪽에는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)  
  
 **ParallelForEach\<T >** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 활동 디자이너가 일반적으로 배치 하는 경우 항상 화면에 대 한 예를 들어 내부는 **시퀀스** 활동 디자이너입니다. 놓으면는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], 만듭니다는 <xref:System.Activities.Statements.ParallelForEach%601> 기본적으로 포함 된 활동을 한 <xref:System.Activities.Activity.DisplayName%2A> 의 **ParallelForEach < Int32\>합니다.**  
  
### <a name="parallelforeacht-properties-in-the-workflow-designer"></a>ParallelForEach < T\> 워크플로 디자이너의 속성  
 다음 표에서는 가장 유용한 <xref:System.Activities.Statements.ParallelForEach%601> 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 활동 디자이너의 표시 이름을 지정합니다. 기본값은 **ParallelForEach\<i n t 32 >**합니다. 값을 선택적으로 편집할 수는 **속성** 표에서 또는 활동 디자이너 머리글에서 직접 합니다.|  
|<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>|False|컬렉션의 각 항목에 대해 실행할 활동입니다. 추가 하는 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> 활동을 도구 상자의 활동은 **본문** 상자에 **ParallelForEach\<T >** 활동 디자이너를 "여기에 작업 놓기" 힌트 텍스트가 있습니다.|  
|**TypeArgument**|True|에 있는 항목의 종류는 <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> 제네릭 매개 변수로 지정 된 컬렉션 *T*합니다. 기본적으로 **TypeArgument** 로 설정 된 **Int32**합니다. 형식 T를 변경 하는 **ParallelForEach < T\>**  활동 디자이너의 값을 변경는 **TypeArgument** 속성 표의 콤보 상자입니다.|  
|<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>|True|반복할 항목의 컬렉션입니다. 설정 하는 <xref:System.Activities.Statements.ParallelForEach%601.Values%2A>, 입력 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 식에는 **값** 상자에 **ForEach < T\>**  또는 "VB 식 입력" 힌트 텍스트가 있는 상자에 활동 디자이너 **값** 상자에 **속성** 창.|  
|<xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>||각 반복이 완료된 후 평가됩니다. true이면 예약된 보류 중인 반복이 취소됩니다. 이 속성을 설정하지 않으면 예약된 모든 문이 완료될 때까지 실행됩니다.|  
  
 루프 반복기는 기본적으로 이름이 지정된 항목입니다. 반복기 변수의 이름을 변경할 수 있습니다는 **ForEach** 상자에 **ParallelForEach\<T >** 활동 디자이너입니다. 루프 반복기는 <xref:System.Activities.Statements.ParallelForEach%601> 활동의 자식에 포함된 식에서 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [시퀀스](../workflow-designer/sequence-activity-designer.md)   
 [병렬](../workflow-designer/parallel-activity-designer.md)   
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)