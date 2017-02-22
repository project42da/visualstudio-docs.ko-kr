---
title: "전환 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "09/02/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.Transition.UI"
ms.assetid: f6e8b5cc-7fb8-4699-9703-f3c9fc7cc316
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "sdanie"
manager: "erikre"
---
# 전환 활동 디자이너
<xref:System.Activities.Statements.Transition>는 두 상태 간 전환을 나타냅니다.  
  
## Transition 활동 디자이너 사용  
 전환 활동 디자이너를 사용하면 두 상태 간에 전환을 구성할 수 있습니다.  
  
### Workflow Designer의 Transition 속성  
 다음 표에서는 가장 워크플로 디자이너를 사용하여 설정할 수 있는 <xref:System.Activities.Statements.Transition> 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Statements.Transition.DisplayName%2A>|False|<xref:System.Activities.Statements.Transition> 활동 디자이너의 이름을 지정합니다.기본값은 **T1**입니다.값은 속성 그리드, 확장된 전환 디자이너의 헤더 및 확장된 전환 디자이너 내에서 작업 섹션의 헤더에서 편집할 수 있습니다.<xref:System.Activities.Activity.DisplayName%2A>은 워크플로 디자이너 상단에 표시되는 이동 경로 탐색에 사용됩니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.Transition.Condition%2A>|False|있을 경우 대상 상태에 제어를 전달하기 전에 **True**가 되는 식을 지정합니다.속성 그리드 및 확장 전환 디자이너에서 이 조건을 편집할 수 있습니다.전환 디자이너에 나타나는 순서로 공유 전환의 여러 조건을 평가합니다. **Note:**  전환의 <xref:System.Activities.Statements.Transition.Condition%2A>가 **False**가 되거나 모든 공유 트리거 전환 조건이 **False**가 되는 경우, 전환이 일어나지 않으며 해당 상태로부터의 모든 전환에 대한 모든 트리거가 다시 예정됩니다.이 자습서에서는 조건을 구성하는 방법 때문에 이 상황이 일어날 수 없으며, 추측이 올바른 것인지 또는 잘못된 것인지에 대한 구체적인 작업을 가지고 있습니다.|  
|**소스**|True|이 전환이 원래 발생한 상태를 나타냅니다.소스 상태의 이름을 클릭하면 디자이너 보기가 해당 상태의 확장된 보기로 전환됩니다.이 값은 전환이 만들어질 때 설정되며 변경될 수 있습니다.|  
|<xref:System.Activities.Statements.Transition.Trigger%2A>|False|완료는 전환을 시작하는 활동을 지정합니다.이 활동을 설정하려면 **도구 상자**에서 활동을 끌어 전환의 **트리거** 섹션에 놓습니다.|  
|<xref:System.Activities.Statements.Transition.Action%2A>|False|트리거 활동이 완료될 때 실행되는 활동을 지정하고 <xref:System.Activities.Statements.Transition.Condition%2A>가 있을 경우 **true**로 평가합니다.이 활동은 소스 상태\(있을 경우\)에 대한 <xref:System.Activities.Statements.State.Exit%2A> 활동이 실행된 후에 대상 상태로 전환할 때 실행됩니다.전환 디자이너가 확장되면 **도구 상자**에서 활동을 끌어 전환의 **작업** 섹션에 놓으면 이 값을 설정할 수 있습니다.단일 전환에 여러 작업이 있을 수 있습니다.개별 작업을 확장하고 수축할 수 있으며 전환 중인 작업이 여러 개 있을 때 작업에 나타나는 위 또는 아래 화살표를 클릭하여 순서를 지정할 수 있습니다.|  
|**Destination**|True|전환이 완료된 후 상태 시스템이 전환하는 상태를 나타냅니다.이는 개체 모델에 있는 전환의 <xref:System.Activities.Statements.Transition.To%2A> 속성에 해당합니다.대상 상태의 이름을 클릭하면 디자이너 보기가 해당 상태의 확장된 보기로 전환됩니다.이 값은 전환이 만들어지면 설정되고 전환을 디자이너의 대상 상태에 연결하는 화살표를 끌어 변경할 수 있습니다.|  
  
### 전환 만들기  
 전환은 한 상태에서 다른 상태로 선을 끌거나 한 상태를 다른 상태 위로 끌어갈 때 나타나는 삼각형에 상태를 놓으면 만들어집니다.끌어서 전환을 만들려면 소스 상태의 가장자리 위로 마우스를 가져가 소스 상태에서 대상 상태로 선을 끕니다.놓아서 전환을 만들려면 대상 상태를 끌어 소스 상태 위로 가져가 소스 상태 주변에 나타나는 4개의 삼각형 중 하나에 놓습니다.대상 상태는 **도구 상자**에서 끌어온 새로운 상태이거나 워크플로 디자이너에서 끌어온 기존 상태가 될 수 있습니다.  
  
> [!NOTE]
>  상태 시스템에서 하나의 상태는 Workflow Designer를 사용하여 만들어지는 전환을 76개까지 사용할 수 있습니다.디자이너 밖에서 만들어지는 워크플로 상태의 전환에 대한 제한은 시스템 리소스로만 제한됩니다.  
  
 공유 트리거 전환은 같은 트리거 이벤트를 공유하는 전환 집합입니다.공유 트리거를 사용하면 공통의 트리거 이벤트를 공유하는 여러 전환에 대해 구성된 식의 평가를 기준으로 대상 상태로 조건적 진행이 가능합니다.전환에 추가 작업을 추가하고 공유 전환을 만들려면 원하는 전환의 시작을 나타내는 원을 클릭하고 원하는 상태로 끕니다.새 전환은 초기 전환과 동일한 트리거를 공유하지만 고유한 조건과 작업을 사용합니다.공유 전환은 전환 디자이너의 아래쪽에서 **공유 트리거 전환 추가**를 클릭한 다음 **연결할 사용 가능한 상태** 드롭다운에서 원하는 대상 상태를 선택하여 전환 디자이너에서도 만들 수 있습니다.  
  
## 참고 항목  
 [StateMachine](../workflow-designer/statemachine-activity-designer.md)   
 [FinalState](../workflow-designer/finalstate-activity-designer.md)   
 [상태](../workflow-designer/state-activity-designer.md)