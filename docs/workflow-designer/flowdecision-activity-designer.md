---
title: "FlowDecision 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.FlowDecision.UI"
ms.assetid: 4a49edc3-3662-4b7b-812e-0a5ba00d6c94
caps.latest.revision: 4
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# FlowDecision 활동 디자이너
<xref:System.Activities.Statements.FlowDecision> 노드는 지정된 조건이 충족되었는지 여부에 따라 제어 흐름을 두 가지 대안 중 하나로 보내는 분기를 제공하는 조건 노드입니다.흐름에 두 개 이상의 분기가 필요하면 <xref:System.Activities.Statements.FlowSwitch%601>을 대신 사용합니다.  
  
## FlowDecision 노드  
 흐름이 두 경로로 분기될 수 있는 경우 <xref:System.Activities.Statements.FlowDecision>을 사용합니다.<xref:System.Activities.Statements.FlowDecision> 노드에는 <xref:System.Activities.Statements.FlowDecision.True%2A> 또는 <xref:System.Activities.Statements.FlowDecision.False%2A>의 두 가지 결과와 각각 연결된 <xref:System.Activities.Statements.FlowNode>와 <xref:System.Activities.Statements.FlowDecision.Condition%2A>이 있습니다.<xref:System.Activities.Statements.FlowDecision.Condition%2A>을 평가하고 이 평가의 값으로 <xref:System.Activities.Statements.Flowchart>에서 처리할 다음 번 <xref:System.Activities.Statements.FlowNode>를 결정합니다.  
  
### FlowDecision 디자이너 사용  
 **FlowDecision** 디자이너는 **도구 상자**의 **순서도** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **FlowDecision** 디자이너는 **도구 상자**에서 **순서도** 활동 디자이너 안에 있는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면으로 끌어 놓을 수 있습니다.그러면 <xref:System.Activities.Statements.Flowchart> 활동 안에 **결정**이라는 레이블의 <xref:System.Activities.Statements.FlowDecision>이 만들어집니다.마우스를 디자이너 위로 가져가면 두 분기의 **True** 및 **False** 정사각형 핸들이 나타납니다.  
  
 **FlowDecision** 디자이너와 다른 디자이너를 **순서도**로 끌어 놓은 후 노드를 함께 연결하여 실행 순서를 지정할 수 있습니다.소스 노드\(**FlowDecision**의 **True** 및 **False** 분기 포함\)와 대상 노드 사이에 연결을 만들려면 소스 노드의 디자이너 위로 마우스를 가져갑니다. 그러면 정사각형 핸들이 양쪽에 나타납니다.정사각형 핸들 중 하나를 클릭한 후 마우스 단추를 누른 상태에서 핸들 중 하나로 끕니다. 대상 노드 위로 마우스를 가져가면 대상 노드 주변에도 이 핸들이 비슷한 방식으로 나타납니다.마우스 단추를 놓으면 두 노드 간 연결이 만들어지고 소스 디자이너에서 대상 디자이너를 향하는 화살표로 표시됩니다.  
  
 "VB 식 입력"이라는 힌트 텍스트가 표시된 부분을 클릭하여 <xref:System.Activities.Statements.FlowDecision.Condition%2A>을 명시하는 식을 **속성** 창의 **조건** 상자에 입력할 수 있습니다.  
  
### FlowDecision 속성  
 다음 표에서는 <xref:System.Activities.Statements.FlowDecision> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이러한 속성은 속성 표 또는 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Statements.FlowDecision.Condition%2A>|True|흐름 제어의 경로를 결정하는 조건입니다.|  
|<xref:System.Activities.Statements.FlowDecision.True%2A>|False|<xref:System.Activities.Statements.FlowDecision.Condition%2A>이 충족되는 경우의 흐름 제어 경로입니다.|  
|<xref:System.Activities.Statements.FlowDecision.False%2A>|False|<xref:System.Activities.Statements.FlowDecision.Condition%2A>이 충족되지 않는 경우의 흐름 제어 경로입니다.|  
  
## 참고 항목  
 [순서도](../workflow-designer/flowchart-activity-designers.md)   
 [순서도](../workflow-designer/flowchart-activity-designer.md)   
 [FlowSwitch\<T\>](../workflow-designer/flowswitch-t-activity-designer.md)