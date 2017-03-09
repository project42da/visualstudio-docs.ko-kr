---
title: "Pick 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.Pick.UI"
ms.assetid: 642c0a47-1b47-45de-a19a-ca0606cedd7a
caps.latest.revision: 9
caps.handback.revision: 9
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# Pick 활동 디자이너
<xref:System.Activities.Statements.Pick> 활동은 이벤트 기반의 제어 흐름을 제공합니다.이 활동은 트리거를 시작하는 이벤트에 대해 몇 가지 분기 중 하나를 실행합니다.  
  
## Pick 활동  
 <xref:System.Activities.Statements.Pick> 활동에는 <xref:System.Activities.Statements.PickBranch> 개체 컬렉션이 포함되어 있는데, <xref:System.Activities.Statements.Pick> 활동은 트리거 역할을 하는 들어오는 이벤트로 이러한 개체 중 하나를 실행할 수 있습니다.이러한 방식으로 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]는 이벤트 기반 제어 흐름 모델링을 제공합니다.각 <xref:System.Activities.Statements.PickBranch>에는 <xref:System.Activities.Statements.PickBranch.Trigger%2A> 및 <xref:System.Activities.Statements.PickBranch.Action%2A>이 포함되어 있습니다.<xref:System.Activities.Statements.Pick> 활동을 실행하기 시작할 때 <xref:System.Activities.Statements.PickBranch> 요소의 트리거 활동이 모두 예약됩니다.첫 번째 활동이 완료되면 해당하는 동작 활동이 예약되고 다른 트리거 활동은 모두 취소됩니다.  
  
### Pick 활동 디자이너를 사용하는 방법  
 **Pick** 활동 디자이너는 **도구 상자**의 **제어 흐름** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나 Ctrl\+Alt\+X를 누릅니다.  
  
 **도구 상자**의 **Pick** 활동 디자이너를 **Sequence** 활동 디자이너 내부 등 활동 디자이너가 일반적으로 배치되는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면 아무 곳에나 끌어 놓을 수 있습니다.[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에 끌어 놓으면 <xref:System.Activities.Statements.Pick> 활동이 만들어집니다. 이 활동에는 기본적으로 빈 <xref:System.Activities.Statements.PickBranch> 활동 두 개가 요소\(표시 이름 Branch1 및 Bracnh2\)로 포함되어 있습니다.이러한 각 <xref:System.Activities.Statements.PickBranch.DisplayName%2A> 속성 값은 **PickBranch** 활동 디자이너 머리글 또는 각 분기의 **속성** 창에서 편집할 수 있습니다.  
  
 <xref:System.Activities.Statements.PickBranch> 활동을 <xref:System.Activities.Statements.Pick> 개체에 추가하는 방법은 **도구 상자**에서 **PickBranch** 디자이너를 끌어 놓는 방법 또는 **Pick** 디자인 화면 내 상황에 맞는 메뉴를 사용하는 방법의 두 가지입니다.자세한 내용은 [PickBranch](../workflow-designer/pickbranch-activity-designer.md) 항목을 참조하십시오.**Pick** 활동 디자이너 내부에 배치할 수 있는 항목은 **PickBranch** 활동 디자이너뿐입니다.  
  
### Workflow Designer의 Pick 활동  
 다음 표에서는 <xref:System.Activities.Statements.Pick> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이러한 속성은 속성 표 또는 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 <xref:System.Activities.Statements.Pick> 활동 디자이너의 이름을 지정합니다.기본값은 Pick입니다.속성 표에서 또는 활동 디자이너의 머리글에서 직접 값을 편집할 수 있습니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
  
## 참고 항목  
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)   
 [Pick 활동](../Topic/Pick%20Activity.md)   
 [Pick 활동 사용](../Topic/Using%20the%20Pick%20Activity.md)