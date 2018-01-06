---
title: "PickBranch 활동 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.PickBranch.UI
ms.assetid: f523ad47-bbc0-4cda-a35c-41e67c4ba081
caps.latest.revision: "10"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: d583c662de31b990982b78d876bc0046e89089d7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="pickbranch-activity-designer"></a>PickBranch 활동 디자이너
<xref:System.Activities.Statements.PickBranch>는 들어오는 이벤트에 의해 트리거되는 <xref:System.Activities.Statements.Pick> 활동 내에서 이벤트 기반의 실행 경로를 제공합니다.  
  
## <a name="pickbranch"></a>PickBranch  
 <xref:System.Activities.Statements.PickBranch> 개체는 <xref:System.Activities.Statements.Pick.Branches%2A> 활동의 <xref:System.Activities.Statements.Pick> 컬렉션에 포함되어 있습니다. 각 <xref:System.Activities.Statements.PickBranch>는 <xref:System.Activities.Statements.Pick> 활동의 분기에 포함되며 트리거 역할을 하는 일부 들어오는 이벤트에 따라 실행될 수 있습니다. 이러한 방식으로 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]는 이벤트 기반의 제어 흐름 모델링을 제공합니다. 각 <xref:System.Activities.Statements.PickBranch>에는 <xref:System.Activities.Statements.PickBranch.Trigger%2A> 및 <xref:System.Activities.Statements.PickBranch.Action%2A>이 포함되어 있습니다.  
  
### <a name="how-to-use-the-pick-activity-designer"></a>Pick 활동 디자이너를 사용하는 방법  
 **PickBranch** 디자이너에서 확인할 수 있습니다는 **제어 흐름** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자** 탭 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X).  
  
 두 개의 빈 <xref:System.Activities.Statements.PickBranch> 사용 하 여 개체의 이름을 표시 **Branch1** 및 **분기 2** 요소로 기본적으로 생성 되는 <xref:System.Activities.Statements.Pick> 활동 때는 **선택** 처음에 활동 디자이너를 끌어는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]합니다. 이러한 각 <xref:System.Activities.Statements.PickBranch.DisplayName%2A> 에서 속성 값을 편집할 수는 **PickBranch** 디자이너 머리글 또는 **속성** 각 분기에 대 한 창.  
  
 추가 하는 방법은 두 가지가 <xref:System.Activities.Statements.PickBranch> 개체의 컬렉션에는 <xref:System.Activities.Statements.Pick> 개체: 끌어서 놓기는 **PickBranch** 에서 디자이너는 **도구 상자** 또는에서 상황에 맞는 메뉴를 사용 하 여 내에서 **선택** 디자인 화면:  
  
1.  **PickBranch** 디자이너 만듭니다는 <xref:System.Activities.Statements.PickBranch> 에서 끌어는 **도구 상자** 분기 중 하나에 **선택** 는 에활동디자이너[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면입니다. 새 <xref:System.Activities.Statements.PickBranch> 개체는 <xref:System.Activities.Statements.Pick> 디자이너 내에서 컬렉션에 이미 포함되어 있는 기존 <xref:System.Activities.Statements.PickBranch> 요소의 왼쪽 또는 오른쪽에 배치됩니다. 끌어 올 때는 **PickBranch** 디자이너에 **선택** 마우스를 디자이너는 **선택** 디자이너 세로 파란색-회색 밴드를 사용 하 여 위치를 나타내기 위해는 <xref:System.Activities.Statements.PickBranch> 해당된 마우스 위치에 대 한 추가 됩니다.  
  
2.  마우스 오른쪽 단추로 클릭 **선택** 활동 디자이너 (바깥 **PickBranch** 디자이너)를 선택 하 고 상황에 맞는 메뉴를 가져오는 **분기 생성** 새 <xref:System.Activities.Statements.PickBranch>합니다. 새 <xref:System.Activities.Statements.PickBranch> 기존 오른쪽에 추가 <xref:System.Activities.Statements.PickBranch> 개체에 **선택** 디자이너입니다.  
  
 **PickBranch** 디자이너를 표시 하기 위해 확장할 수는 **트리거** 및 **동작** 상자를 표시 하거나 머리글 오른쪽에 있는 이중 캐럿을 클릭 하 여 축소 합니다. 편집 된 <xref:System.Activities.Statements.PickBranch.Trigger%2A> 및 <xref:System.Activities.Statements.PickBranch.Action%2A> 각 <xref:System.Activities.Statements.PickBranch> 활동을 끌어 놓아는 **트리거** 및 **작업** 해당 디자이너의 상자 합니다.  
  
 <xref:System.Activities.Statements.PickBranch> 개체에 <xref:System.Activities.Statements.Pick.Branches%2A> 컬렉션은 <xref:System.Activities.Statements.Pick> 개체를 끌어서 내의 새 위치를 놓아서 다시 정렬할 수 있습니다는 **선택** 디자이너입니다. **선택** 디자이너 세로 파란색-회색 밴드를 사용 하 여 위치를 나타내기 위해는 <xref:System.Activities.Statements.PickBranch> 는 해당된 마우스 위치에 대 한 추가 됩니다.  
  
 <xref:System.Activities.Statements.PickBranch>를 삭제하는 방법은 두 가지입니다.  
  
1.  선택 된 **PickBranch** 디자이너를 삭제 합니다.  
  
2.  선택 된 **PickBranch** 디자이너를 마우스 오른쪽 단추 클릭 상황에 맞는 메뉴를 구하고 선택 **삭제**합니다.  
  
 선택 해야는 **PickBranch** 활동 중 하나를 선택 하 여 디자이너의 **트리거** 또는 **동작** 해당 활동 중 하나를 상자 실수로 삭제 및 not <xref:System.Activities.Statements.PickBranch> 개체입니다.  
  
### <a name="pickbranch-properties-in-the-workflow-designer"></a>워크플로 디자이너의 PickBranch 속성  
 다음 표에서는 가장 유용한 <xref:System.Activities.Statements.PickBranch> 속성을 보여 주고 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.PickBranch.DisplayName%2A>|False|머리글에 표시 되는 이름은 **PickBranch** 디자이너입니다. 기본값은 분기입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.PickBranch.Trigger%2A>|True|각 <xref:System.Activities.Statements.PickBranch>에는 <xref:System.Activities.Statements.PickBranch.Trigger%2A>을 호출할 수 있는 <xref:System.Activities.Statements.PickBranch.Action%2A> 활동이 포함되어 있습니다.|  
|<xref:System.Activities.Statements.PickBranch.Action%2A>|False|각 <xref:System.Activities.Statements.PickBranch>에는 트리거될 경우 실행되는 <xref:System.Activities.Statements.PickBranch.Action%2A>이 포함되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)   
 [선택 활동](/dotnet/framework/windows-workflow-foundation/pick-activity)   
 [Pick 작업 사용](/dotnet/framework/windows-workflow-foundation/samples/using-the-pick-activity)