---
title: "PickBranch 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.PickBranch.UI"
ms.assetid: f523ad47-bbc0-4cda-a35c-41e67c4ba081
caps.latest.revision: 10
caps.handback.revision: 10
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# PickBranch 활동 디자이너
<xref:System.Activities.Statements.PickBranch>는 들어오는 이벤트에 의해 트리거되는 <xref:System.Activities.Statements.Pick> 활동 내에서 이벤트 기반의 실행 경로를 제공합니다.  
  
## PickBranch  
 <xref:System.Activities.Statements.PickBranch> 개체는 <xref:System.Activities.Statements.Pick> 활동의 <xref:System.Activities.Statements.Pick.Branches%2A> 컬렉션에 포함되어 있습니다.각 <xref:System.Activities.Statements.PickBranch>는 <xref:System.Activities.Statements.Pick> 활동의 분기에 포함되며 트리거 역할을 하는 일부 들어오는 이벤트에 따라 실행될 수 있습니다.이러한 방식으로 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]는 이벤트 기반의 제어 흐름 모델링을 제공합니다.각 <xref:System.Activities.Statements.PickBranch>에는 <xref:System.Activities.Statements.PickBranch.Trigger%2A> 및 <xref:System.Activities.Statements.PickBranch.Action%2A>이 포함되어 있습니다.  
  
### Pick 활동 디자이너를 사용하는 방법  
 **PickBranch** 디자이너는 **도구 상자**의 **제어 흐름** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **Pick** 활동 디자이너를 처음 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에 끌어 놓으면 기본적으로 표시 이름이 **Branch1** 및 **Branch2**인 두 개의 빈 <xref:System.Activities.Statements.PickBranch> 개체가 <xref:System.Activities.Statements.Pick> 활동의 요소로 만들어집니다.이러한 각 <xref:System.Activities.Statements.PickBranch.DisplayName%2A> 속성 값은 **PickBranch** 디자이너 머리글 또는 각 분기의 **속성** 창에서 편집할 수 있습니다.  
  
 <xref:System.Activities.Statements.PickBranch> 개체를 <xref:System.Activities.Statements.Pick> 개체의 컬렉션에 추가하려면 **도구 상자**에서 **PickBranch** 디자이너를 끌어 놓는 방법이나 **Pick** 디자인 화면에서 상황에 맞는 메뉴를 사용하는 방법을 사용할 수 있습니다.  
  
1.  **도구 상자**의 **PickBranch** 디자이너를 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 **Pick** 활동 디자이너 분기 중 하나로 끌어 놓으면 <xref:System.Activities.Statements.PickBranch>가 만들어집니다.새 <xref:System.Activities.Statements.PickBranch> 개체는 <xref:System.Activities.Statements.Pick> 디자이너 내에서 컬렉션에 이미 포함되어 있는 기존 <xref:System.Activities.Statements.PickBranch> 요소의 왼쪽 또는 오른쪽에 배치됩니다.마우스로 **PickBranch** 디자이너를 **Pick** 디자이너로 끌어 놓을 때 **Pick** 디자이너는 해당 마우스 위치를 기준으로 <xref:System.Activities.Statements.PickBranch>가 추가되는 위치를 파란색\-회색의 수직 띠로 나타냅니다.  
  
2.  **PickBranch** 디자이너 바깥에서 **Pick** 활동 디자이너를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **분기 생성**을 선택하여 새 <xref:System.Activities.Statements.PickBranch> 활동을 추가합니다.새 <xref:System.Activities.Statements.PickBranch>는 **Pick** 디자이너에서 기존 <xref:System.Activities.Statements.PickBranch> 개체의 오른쪽에 추가됩니다.  
  
 **PickBranch** 디자이너를 확장하여 **트리거** 및 **작업** 상자를 표시하거나 머리글 오른쪽에 있는 이중 캐럿을 클릭하여 디자이너를 축소할 수 있습니다.해당 디자이너의 **트리거** 및 **작업** 상자로 활동을 끌어서 각 <xref:System.Activities.Statements.PickBranch>의 <xref:System.Activities.Statements.PickBranch.Trigger%2A> 및 <xref:System.Activities.Statements.PickBranch.Action%2A>을 편집합니다.  
  
 <xref:System.Activities.Statements.Pick> 개체의 <xref:System.Activities.Statements.Pick.Branches%2A> 컬렉션에서 <xref:System.Activities.Statements.PickBranch> 개체를 **Pick** 디자이너의 새 위치로 끌어 놓아 순서를 조정할 수 있습니다.**Pick** 디자이너는 특정 마우스 위치를 기준으로 <xref:System.Activities.Statements.PickBranch>가 추가되는 위치를 파란색\-회색의 수직 띠로 나타냅니다.  
  
 <xref:System.Activities.Statements.PickBranch>를 삭제하는 방법은 두 가지입니다.  
  
1.  **PickBranch** 디자이너를 선택한 다음 삭제합니다.  
  
2.  **PickBranch** 디자이너를 선택하고 마우스 오른쪽 단추를 클릭하여 상황에 맞는 메뉴를 표시한 다음 **삭제**를 선택합니다.  
  
 **PickBranch** 디자이너를 선택해야 합니다. 실수로 **트리거** 또는 **작업** 상자의 활동 중 하나를 선택하면 해당 활동만 삭제되고 <xref:System.Activities.Statements.PickBranch> 개체는 삭제되지 않습니다.  
  
### Workflow Designer의 PickBranch 속성  
 다음 표에서는 가장 유용한 <xref:System.Activities.Statements.PickBranch> 속성을 보여 주고 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Statements.PickBranch.DisplayName%2A>|False|**PickBranch** 디자이너의 머리글에 표시되는 이름입니다.기본값은 Branch입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.PickBranch.Trigger%2A>|True|각 <xref:System.Activities.Statements.PickBranch>에는 <xref:System.Activities.Statements.PickBranch.Action%2A>을 호출할 수 있는 <xref:System.Activities.Statements.PickBranch.Trigger%2A> 활동이 포함되어 있습니다.|  
|<xref:System.Activities.Statements.PickBranch.Action%2A>|False|각 <xref:System.Activities.Statements.PickBranch>에는 트리거될 경우 실행되는 <xref:System.Activities.Statements.PickBranch.Action%2A>이 포함되어 있습니다.|  
  
## 참고 항목  
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)   
 [Pick 활동](../Topic/Pick%20Activity.md)   
 [Pick 활동 사용](../Topic/Using%20the%20Pick%20Activity.md)