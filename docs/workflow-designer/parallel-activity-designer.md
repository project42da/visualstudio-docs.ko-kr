---
title: "활동 디자이너를 병렬 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Parallel.UI
ms.assetid: 0306dc3b-075a-4091-ac3a-96486fbabed5
caps.latest.revision: "10"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: b6b6c0498b98f38b786ce846fd6d975287a2c75e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="parallel-activity-designer"></a>Parallel 활동 디자이너
<xref:System.Activities.Statements.Parallel> 활동은 자식 활동 컬렉션을 동시에 실행합니다.  
  
## <a name="the-parallel-activity"></a>Parallel 활동  
 <xref:System.Activities.Statements.Parallel> 활동은 자식 활동을 <xref:System.Activities.Statements.Parallel.Branches%2A> 컬렉션에 저장합니다. 일부 자식 활동이 유휴 상태가 될 수 있는 경우에는 <xref:System.Activities.Statements.Parallel> 활동 대신 <xref:System.Activities.Statements.Sequence> 활동을 사용합니다.  
  
 <xref:System.Activities.Statements.Parallel> 활동에는 사용자가 지정한 <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 식이 포함된 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 속성이 있습니다. <xref:System.Activities.Statements.Parallel> 활동은 각 분기가 완료된 후 이 속성을 평가합니다. 로 평가 되 면 **True**, 하면 <xref:System.Activities.Statements.Parallel> 활동이 다른 분기를 실행 하지 않고 완료 합니다. 경우는 <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 계산 되지 않습니다 **True**, 하면 <xref:System.Activities.Statements.Parallel> 자식 활동이 모두 완료 했을 때 활동이 완료 합니다.  
  
### <a name="using-the-parallel-activity-designer"></a>Parallel 활동 디자이너 사용  
 **병렬** 활동 디자이너에서 확인할 수 있습니다는 **제어 흐름** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**탭의 왼쪽에는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)  
  
 **병렬** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 activity designer가 정상적으로 배치 하는 예를 들어는 내부**시퀀스** 활동 디자이너입니다. 놓으면는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], 생성 한 <xref:System.Activities.Statements.Parallel> 기본적으로 포함 된 활동을 한 <xref:System.Activities.Activity.DisplayName%2A> 의 **병렬**  
  
 에 활동을 추가 하는 <xref:System.Activities.Statements.Parallel.Branches%2A> parallel 활동의 컬렉션에는 몇 가지 다른 활동 디자이너를 끌어는 **도구 상자** 내부에 있는 삼각형에 놓는 것는 **병렬** 활동 디자이너입니다. 이 삼각형은 분기에 포함된 활동 옆에 표시됩니다. 이 절차를 반복하여 다른 활동을 추가할 수 있습니다. 활동 끌어서 놓아 내에서 다시 정렬할 수 있습니다는 **병렬** 활동 디자이너입니다.  
  
### <a name="parallel-activity-properties-in-the-workflow-designer"></a>워크플로 디자이너의 Parallel 활동 속성  
 다음 표에서는 가장 유용한 Parallel 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 활동 디자이너의 표시 이름을 지정합니다. 기본값은 **병렬**합니다. 값을 선택적으로 편집할 수는 **속성** 표에서 또는 활동 디자이너 머리글에서 직접 합니다.|  
|<xref:System.Activities.Statements.Parallel.Branches%2A>|True|실행할 자식 활동의 컬렉션을 포함합니다.|  
|<xref:System.Activities.Statements.Parallel.CompletionCondition%2A>|False|분기가 완료된 후 확인됩니다. 로 평가 되 면 **True**, 예약 된 보류 중인 분기가 취소 됩니다. 이 속성이 설정 되어 있지 않거나로 평가 되는 경우 **False**, 자식 활동이 모두 완료 했을 때 작업을 완료 합니다. 기본값은 **null**합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [시퀀스](../workflow-designer/sequence-activity-designer.md)   
 [ParallelForEach\<T >](../workflow-designer/parallelforeach-t-activity-designer.md)   
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)