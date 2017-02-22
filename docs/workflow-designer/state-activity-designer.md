---
title: "상태 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "09/27/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.State.UI"
ms.assetid: 9455ab37-93a0-4c46-9eb8-b6611ca23167
caps.latest.revision: 5
caps.handback.revision: 5
ms.author: "sdanie"
manager: "erikre"
---
# 상태 활동 디자이너
<xref:System.Activities.Statements.State>는 상태 시스템이 처할 수 있는 상태를 나타냅니다.  
  
## 상태 활동 디자이너 사용  
 <xref:System.Activities.Statements.State>를 워크플로에 추가하려면 **도구 상자**의 **시스템 상태** 섹션에서 **State** 활동 디자이너를 끌어 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] 화면의 <xref:System.Activities.Statements.StateMachine> 활동에 놓습니다.<xref:System.Activities.Statements.State> 활동은 <xref:System.Activities.Statements.StateMachine>에 끌어 놓고 나중에 전환을 추가하거나 <xref:System.Activities.Statements.State> 활동을 끌어 놓을 때 전환을 만들 수 있습니다.한번에 <xref:System.Activities.Statements.State> 활동을 추가하고 전환을 만들려면 **도구 상자**의 **상태 시스템** 섹션에서 **State** 활동을 끌어 Workflow Designer의 다른 상태 위로 가져갑니다.끌어 온 <xref:System.Activities.Statements.State>를 다른 <xref:System.Activities.Statements.State> 위로 가져가면 <xref:System.Activities.Statements.State> 주위에 삼각형 4개가 표시됩니다.<xref:System.Activities.Statements.State>를 삼각형 4개 중 하나에 놓으면 상태 시스템에 추가되고, 소스 <xref:System.Activities.Statements.State>에서 놓은 대상 <xref:System.Activities.Statements.State>로의 전환이 만들어집니다. 자세한 내용은 [전환](../workflow-designer/transition-activity-designer.md)를 참조하십시오.  
  
### Workflow Designer의 State 활동 속성  
 다음 표에서는 가장 워크플로 디자이너를 사용하여 설정할 수 있는 <xref:System.Activities.Statements.State> 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.이러한 일부 속성은 속성 표에서 편집할 수 있으며 일부 속성은 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|용도|  
|-----------|--------|--------|  
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|머리글에 <xref:System.Activities.Statements.State> 활동 디자이너의 이름을 지정합니다.기본값은 **State**입니다,속성 표에서 또는 활동 디자이너의 머리글에서 직접 값을 편집할 수 있습니다.<xref:System.Activities.Statements.State.DisplayName%2A>은 워크플로 디자이너 상단에 표시되는 이동 경로 탐색에 사용됩니다.<br /><br /> <xref:System.Activities.Statements.State.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.State.Entry%2A>|False|이 상태가 전환될 때 발생하는 동작을 지정합니다.<xref:System.Activities.Statements.State> 활동이 확장되면 **도구 상자**에서 활동을 끌어 상태의 **항목** 섹션에 놓으면 이 값을 설정할 수 있습니다.|  
|<xref:System.Activities.Statements.State.Exit%2A>|False|이 상태가 다른 상태로 전환될 때 발생하는 동작을 지정합니다.<xref:System.Activities.Statements.State> 활동이 확장되면 **도구 상자**에서 활동을 끌어 상태의 **끝내기** 섹션에 놓으면 이 값을 설정할 수 있습니다.|  
|<xref:System.Activities.Statements.State.Transitions%2A>|False|<xref:System.Activities.Statements.State>에서 가능한 전환을 나열합니다.목록의 각 항목에는 관련 <xref:System.Activities.Statements.Transition> 및 대상 <xref:System.Activities.Statements.State>에 대한 링크가 있습니다.링크를 클릭하면 디자이너가 <xref:System.Activities.Statements.Transition> 또는 <xref:System.Activities.Statements.State>의 확장된 보기로 전환됩니다.|  
  
## 참고 항목  
 [StateMachine](../workflow-designer/statemachine-activity-designer.md)   
 [FinalState](../workflow-designer/finalstate-activity-designer.md)   
 [전환](../workflow-designer/transition-activity-designer.md)