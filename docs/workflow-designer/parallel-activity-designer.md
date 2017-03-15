---
title: "Parallel 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.Parallel.UI"
ms.assetid: 0306dc3b-075a-4091-ac3a-96486fbabed5
caps.latest.revision: 10
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Parallel 활동 디자이너
<xref:System.Activities.Statements.Parallel> 활동은 자식 활동 컬렉션을 동시에 실행합니다.  
  
## Parallel 활동  
 <xref:System.Activities.Statements.Parallel> 활동은 자식 활동을 <xref:System.Activities.Statements.Parallel.Branches%2A> 컬렉션에 저장합니다.일부 자식 활동이 유휴 상태가 될 수 있는 경우에는 <xref:System.Activities.Statements.Sequence> 활동 대신 <xref:System.Activities.Statements.Parallel> 활동을 사용합니다.  
  
 <xref:System.Activities.Statements.Parallel> 활동에는 사용자가 지정한 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 식이 포함된 <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 속성이 있습니다.<xref:System.Activities.Statements.Parallel> 활동은 각 분기가 완료된 후 이 속성을 평가합니다.**True**로 평가되면 다른 분기를 실행하지 않고 <xref:System.Activities.Statements.Parallel> 활동이 완료됩니다.<xref:System.Activities.Statements.Parallel.CompletionCondition%2A>이 **True**로 평가되지 않는 경우 자식 활동이 모두 완료되어야 <xref:System.Activities.Statements.Parallel> 활동이 완료됩니다.  
  
### Parallel 활동 디자이너 사용  
 **병렬** 활동 디자이너는 **도구 상자**의 **제어 흐름** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 왼쪽에 있는 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **도구 상자**의 **Parallel** 활동 디자이너를 **Sequence** 활동 디자이너 내부 등 활동 디자이너가 일반적으로 배치되는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면 아무 곳에나 끌어 놓을 수 있습니다.[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]로 활동 디자이너를 끌어 놓으면 <xref:System.Activities.Statements.Parallel> 활동이 만들어집니다. 기본적으로 이 활동에는 **Parallel** 의 <xref:System.Activities.Activity.DisplayName%2A>이 포함되어 있습니다.  
  
 Parallel 활동의 <xref:System.Activities.Statements.Parallel.Branches%2A> 컬렉션에 활동을 추가하려면 **도구 상자**의 다른 활동 디자이너를 **Parallel** 활동 디자이너 내부에 있는 삼각형으로 끌어 옵니다.이 삼각형은 분기에 포함된 활동 옆에 표시됩니다.이 절차를 반복하여 다른 활동을 추가할 수 있습니다.**Parallel** 활동 디자이너 내에서 활동을 끌어 놓아 활동을 다시 정렬할 수 있습니다.  
  
### Workflow Designer의 Parallel 활동  
 다음 표에서는 가장 유용한 Parallel 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 활동 디자이너의 표시 이름을 지정합니다.기본값은 **Parallel**입니다.값은 **속성** 창에서 선택적으로 편집하거나 활동 디자이너 머리글에서 직접 편집할 수 있습니다.|  
|<xref:System.Activities.Statements.Parallel.Branches%2A>|True|실행할 자식 활동의 컬렉션을 포함합니다.|  
|<xref:System.Activities.Statements.Parallel.CompletionCondition%2A>|False|분기가 완료된 후 확인됩니다.**True**이면 예약된 보류 중인 분기가 취소됩니다.이 속성이 설정되어 있지 않거나 **False**가 아닌 경우에는 자식 활동이 모두 완료되어야 활동이 완료됩니다.기본값은 **null**입니다.|  
  
## 참고 항목  
 [Sequence](../workflow-designer/sequence-activity-designer.md)   
 [ParallelForEach\<T\>](../workflow-designer/parallelforeach-t-activity-designer.md)   
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)