---
title: "ParallelForEach&lt;T&gt; 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.ParallelForEach`1.UI"
ms.assetid: e93a4843-aef2-4d3e-9a0a-a2d3d1411aa7
caps.latest.revision: 9
caps.handback.revision: 9
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# ParallelForEach&lt;T&gt; 활동 디자이너
<xref:System.Activities.Statements.ParallelForEach%601> 활동은 컬렉션의 요소를 열거하고 컬렉션의 각 요소에 대해 포함 문을 병렬로 실행합니다. 각 요소는 동일 스레드에서 비동기적입니다.<xref:System.Activities.Statements.Sequence> 활동의 자식 활동이 유휴 상태가 되는 경우 이 활동 대신 이 흐름 제어 활동을 사용합니다.  
  
 <xref:System.Activities.Statements.ParallelForEach%601> 활동에는 사용자가 지정한 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 식이 포함된 <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> 속성이 있습니다.<xref:System.Activities.Statements.ParallelForEach%601> 활동은 각 분기가 완료된 후 이 속성을 평가합니다.**true**로 평가되면 다른 분기를 실행하지 않고 <xref:System.Activities.Statements.ParallelForEach%601> 활동이 완료됩니다.<xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>이 **true**로 평가되지 않는 경우 자식 활동이 모두 완료되어야 <xref:System.Activities.Statements.ParallelForEach%601> 활동이 완료됩니다.  
  
## ParallelForEach\<T\> 활동  
 <xref:System.Activities.Statements.ParallelForEach%601>은 값을 열거하고 열거되는 모든 값에 대해 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>을 예약합니다.<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>만 예약합니다.<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>가 유휴 상태로 전환되는지 여부에 따라 본문의 실행 방법이 달라집니다.  
  
 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>가 유휴 상태로 전환되지 않는 경우에는 예약된 활동이 스택으로 처리되기 때문에 역순으로 실행됩니다. 즉, 마지막으로 예약된 활동이 가장 먼저 실행됩니다.예를 들어 <xref:System.Activities.Statements.ParallelForEach%601>에 {1,2,3,4} 컬렉션이 있고 **WriteLine**을 본문으로 사용하여 값을 작성할 경우콘솔에는 4, 3, 2, 1로 출력됩니다.**WriteLine**이 유휴 상태로 전환되지 않으므로 4 **WriteLine** 활동을 예약한 후 스택 동작을 사용하여 실행하기 때문입니다. 즉, 처음 예약한 활동이 마지막에 실행됩니다.  
  
 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>에 유휴 상태로 전환될 수 있는 활동\(예: <xref:System.ServiceModel.Activities.Receive> 활동 또는 <xref:System.Activities.Statements.Delay> 활동\)이 있는 경우에는활동이 완료될 때까지 기다릴 필요가 없습니다.<xref:System.Activities.Statements.ParallelForEach%601>은 예약된 다음 본문 활동으로 이동하여 해당 활동을 실행합니다.이 활동도 유휴 상태가 될 경우 <xref:System.Activities.Statements.ParallelForEach%601>은 다시 다음 본문 활동으로 넘어갑니다.  
  
### ParallelForEach\<T\> 활동 디자이너 사용  
 **ParallelForEach\<T\>** 활동 디자이너는 **도구 상자**의 **제어 흐름** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 왼쪽에 있는 **도구 상자** 탭을 클릭하거나 **보기** 메뉴에서 **도구 모음**을 선택하거나 Ctrl\+Alt\+X를 누릅니다.  
  
 **도구 상자**의 **ParallelForEach\<T\>** 활동 디자이너를 **Sequence** 활동 디자이너 대신에 활동 디자이너가 일반적으로 배치되는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에나 끌어 놓을 수 있습니다.[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]로 활동 디자이너를 끌어 놓으면 <xref:System.Activities.Statements.ParallelForEach%601> 활동이 만들어집니다. 기본적으로 이 활동에는 **ParallelForEach\<Int32\>.** 의 <xref:System.Activities.Activity.DisplayName%2A>이 포함되어 있습니다.  
  
### Workflow Designer의 ParallelForEach\<T\> 속성  
 다음 표에서는 가장 유용한 <xref:System.Activities.Statements.ParallelForEach%601> 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 활동 디자이너의 표시 이름을 지정합니다.기본값은 **ParallelForEach\<Int32\>**입니다.값은 **속성** 창에서 선택적으로 편집하거나 활동 디자이너 머리글에서 직접 편집할 수 있습니다.|  
|<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>|False|컬렉션의 각 항목에 대해 실행할 활동입니다.<xref:System.Activities.Statements.ParallelForEach%601.Body%2A> 활동을 추가하려면 도구 상자의 활동을 "여기에 작업 놓기" 힌트 텍스트가 있는 **ParallelForEach\<T\>** 활동 디자이너의 **본문** 상자로 끌어 놓습니다.|  
|**TypeArgument**|True|제네릭 매개 변수 *T*에 지정된 <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> 컬렉션의 항목 형식입니다.기본적으로 **TypeArgument**는 **Int32**로 설정됩니다.**ParallelForEach\<T\>** 활동 디자이너에서 형식 T를 변경하려면 속성 표에서 **TypeArgument** 콤보 상자의 값을 변경합니다.|  
|<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>|True|반복할 항목의 컬렉션입니다.<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>를 설정하려면 **ForEach\<T\>** 활동 디자이너의 **값** 상자에서 "VB 식 입력" 힌트 텍스트가 있는 상자에, 또는 **속성** 창의 **값** 창에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 식을 입력합니다.|  
|<xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>||각 반복이 완료된 후 평가됩니다.true이면 예약된 보류 중인 반복이 취소됩니다.이 속성을 설정하지 않으면 예약된 모든 문이 완료될 때까지 실행됩니다.|  
  
 루프 반복기는 기본적으로 이름이 지정된 항목입니다.**ParallelForEach\<T\>** 활동 디자이너의 **ForEach** 상자에서 반복기 변수의 이름을 변경할 수 있습니다.루프 반복기는 <xref:System.Activities.Statements.ParallelForEach%601> 활동의 자식에 포함된 식에서 사용할 수 있습니다.  
  
## 참고 항목  
 [Sequence](../workflow-designer/sequence-activity-designer.md)   
 [Parallel](../workflow-designer/parallel-activity-designer.md)   
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)