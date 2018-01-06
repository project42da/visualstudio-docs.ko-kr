---
title: "Pick 활동 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Pick.UI
ms.assetid: 642c0a47-1b47-45de-a19a-ca0606cedd7a
caps.latest.revision: "9"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: ab9ef5504b8785e31446d51f517e8ac41c27d579
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="pick-activity-designer"></a>Pick 활동 디자이너
<xref:System.Activities.Statements.Pick> 활동은 이벤트 기반의 제어 흐름을 제공합니다. 이 활동은 트리거를 시작하는 이벤트에 대해 몇 가지 분기 중 하나를 실행합니다.  
  
## <a name="the-pick-activity"></a>Pick 활동  
 <xref:System.Activities.Statements.Pick> 활동에는 <xref:System.Activities.Statements.PickBranch> 개체 컬렉션이 포함되어 있는데, <xref:System.Activities.Statements.Pick> 활동은 트리거 역할을 하는 들어오는 이벤트로 이러한 개체 중 하나를 실행할 수 있습니다. 이러한 방식으로 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]는 이벤트 기반 제어 흐름 모델링을 제공합니다. 각 <xref:System.Activities.Statements.PickBranch>에는 <xref:System.Activities.Statements.PickBranch.Trigger%2A> 및 <xref:System.Activities.Statements.PickBranch.Action%2A>이 포함되어 있습니다. 맨 앞에 <xref:System.Activities.Statements.Pick> 의 모든 트리거 활동을 활동의 실행은 <xref:System.Activities.Statements.PickBranch> 요소 예약 됩니다. 첫 번째 활동이 완료되면 해당 동작 작업이 예약되고 다른 트리거 활동은 모두 취소됩니다.  
  
### <a name="how-to-use-the-pick-activity-designer"></a>Pick 활동 디자이너를 사용하는 방법  
 **선택** 활동 디자이너에서 확인할 수 있습니다는 **제어 흐름** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**탭 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)  
  
 **선택** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 activity designer가 정상적으로 배치 하는 예를 들어 내부에  **시퀀스** 활동 디자이너입니다. [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에 끌어 놓으면 <xref:System.Activities.Statements.Pick> 활동이 만들어집니다. 이 활동에는 기본적으로 빈 <xref:System.Activities.Statements.PickBranch> 활동 두 개가 요소(표시 이름 Branch1 및 Bracnh2)로 포함되어 있습니다. 이러한 각 <xref:System.Activities.Statements.PickBranch.DisplayName%2A> 에서 속성 값을 편집할 수는 **PickBranch** 활동 디자이너 머리글 또는 **속성** 각 분기에 대 한 창.  
  
 추가 하는 방법은 두 가지가 <xref:System.Activities.Statements.PickBranch> 활동의 컬렉션에는 <xref:System.Activities.Statements.Pick> 개체: 끌어서 놓기는 **PickBranch** 에서 디자이너는 **도구 상자** 또는에서 상황에 맞는 메뉴를 사용 하 여 내에서 **선택** 디자인 화면입니다. 자세한 내용은 참조는 [PickBranch](../workflow-designer/pickbranch-activity-designer.md) 항목입니다. 공지는 유일한 항목을 넣을 수 있습니다는 **선택** activity designer 크기가 **PickBranch** 활동 디자이너입니다.  
  
### <a name="pick-activity-properties-in-the-workflow-designer"></a>워크플로 디자이너의 Pick 활동 속성  
 다음 표에서는 <xref:System.Activities.Statements.Pick> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표 또는 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 <xref:System.Activities.Statements.Pick> 활동 디자이너의 이름을 지정합니다. 기본값은 Pick입니다. 속성 표에서 또는 활동 디자이너의 머리글에서 직접 값을 편집할 수 있습니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)   
 [선택 활동](/dotnet/framework/windows-workflow-foundation/pick-activity)   
 [Pick 작업 사용](/dotnet/framework/windows-workflow-foundation/samples/using-the-pick-activity)