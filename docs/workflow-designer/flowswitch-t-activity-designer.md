---
title: "FlowSwitch&lt;T&gt; 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Core.Presentation.FlowSwitchLink.UI"
  - "System.Activities.Statements.FlowSwitch`1.UI"
  - "System.Activities.Core.Presentation.FlowSwitchLink`1.UI"
  - "System.Activities.Core.Presentation.FlowSwitchLinkIdentifier.UI"
ms.assetid: 5b9c5afe-7499-4ee8-8c33-28aff14bde07
caps.latest.revision: 4
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# FlowSwitch&lt;T&gt; 활동 디자이너
<xref:System.Activities.Statements.FlowSwitch%601> 활동은 두 개 이상의 대안 분기가 필요할 때 일치 기준에 따라 제어 흐름에 대한 분기를 제공하는 조건 노드입니다.흐름 분기에 두 경로만 필요한 경우 <xref:System.Activities.Statements.FlowDecision> 활동을 대신 사용합니다.  
  
## FlowSwitch\<T\> 활동  
 <xref:System.Activities.Statements.FlowSwitch%601> 활동에는 계산 시 *T* 형식의 값\(제네릭 매개 변수로 지정\)을 반환하는 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>이 포함되어 있습니다.또한 이 활동에는 가능한 계산 결과와 <xref:System.Activities.Statements.FlowNode> 개체 집합 간의 고유 매핑을 지정하는 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 집합도 포함되어 있습니다.실행되는 <xref:System.Activities.Statements.FlowNode>는 *T* 형식의 개체가 계산된 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>의 값과 일치하는 노드입니다.일치하는 항목이 없는 case에 대해 선택적으로 <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> case를 제공할 수 있습니다.  
  
### FlowSwitch\<T\> 활동 디자이너 사용  
 **FlowSwitch\<T\>** 활동 디자이너는 **도구 상자**의 **순서도** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 왼쪽에 있는 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **도구 상자**의 **FlowSwitch\<T\>** 활동 디자이너를 **순서도** 활동 디자이너 안에 있는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면으로 끌어 놓을 수 있습니다.**형식 선택** 창이 표시되면 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>을 계산하여 얻은 형식\(제네릭 매개변수에 의해 코드에서 <xref:System.Activities.Statements.FlowSwitch%601>과 연결됨\)을 지정합니다.이 절차는 <xref:System.Activities.Statements.Flowchart> 활동 안에 **Switch**라는 <xref:System.Activities.Statements.FlowSwitch%601> 활동을 만듭니다."VB 식 입력"이라는 힌트 텍스트가 표시된 부분을 클릭하여 **속성** 창의 **식** 상자에 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>을 입력할 수 있습니다.  
  
 **FlowSwitch\<T\>** 활동 디자이너 위로 마우스를 가져가면 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>를 연결하는 데 사용되는 정사각형 핸들이 가장자리 주변에 표시됩니다.**FlowSwitch\<T\>** 활동 디자이너와 기타 활동 디자이너를 **순서도** 위로 끌어 놓은 후 표시되는 <xref:System.Activities.Activity> 개체를 함께 연결하여 실행 순서를 지정할 수 있습니다.<xref:System.Activities.Statements.FlowSwitch%601>에 연결된 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 하나를 만들려면 **FlowSwitch\<T\>**의 주변에 있는 정사각형 case 핸들 중 하나를 클릭한 후 마우스 단추를 누른 상태에서 핸들 중 하나로 끌어 놓습니다. 디자이너 위로 마우스를 가져가면 대상 활동 주변에도 이 핸들이 비슷한 방식으로 나타납니다.마우스 단추를 놓으면 **FlowSwitch\<T\>**에서 대상 디자이너를 향하는 화살표가 표시되어 이 case를 나타냅니다.이 case의 기본값은 화살표 위에 표시되며 **속성** 창의 **Case** 상자에서 편집할 수 있습니다.  
  
### FlowSwitch\<T\> 속성  
 다음 표에서는 <xref:System.Activities.Statements.FlowSwitch%601> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이러한 속성은 속성 표 또는 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>|True|실행 경로에서 전환할 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>를 결정하기 위해 계산할 식을 지정합니다.|  
|<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>|False|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 계산으로 얻은 가능한 결과와 <xref:System.Activities.Statements.FlowNode> 개체 집합 간의 고유 매핑을 지정합니다.|  
|<xref:System.Activities.Statements.FlowSwitch%601.Default%2A>|True|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 계산이 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 개체에 포함된 값 중 하나와 일치하지 않을 경우의 매핑을 지정합니다.|  
  
## 참고 항목  
 [순서도](../workflow-designer/flowchart-activity-designers.md)   
 [순서도](../workflow-designer/flowchart-activity-designer.md)   
 [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)