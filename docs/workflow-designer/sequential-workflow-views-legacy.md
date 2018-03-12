---
title: "순차 워크플로 뷰 (레거시) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- sequential workflow views
- sequential workflows, views
ms.assetid: 135f24b9-1b37-442b-9ef8-f0f2108a3212
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 9f412fa9afee6aa768447fc226553fd68970e646
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="sequential-workflow-views-legacy"></a>순차 워크플로 뷰(레거시)
[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 사용할 수 있는 레거시 Windows 워크플로 디자이너를 제공 합니다. 대상에는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]합니다.

 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에서는 친숙한 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 사용자 인터페이스를 사용하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 응용 프로그램을 시각적으로 만들 수 있습니다. [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 응용 프로그램은 활동이라고 하는 워크플로 프로세스 단계로 구성됩니다. 해당 활동 디자이너를 디자이너를 끌어 디자인 화면에 활동을 작성 워크플로 만들려면 **도구 상자** 디자인 화면으로 합니다.

 순차 워크플로 만들 때는 [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040), 워크플로의 세 가지 뷰를 사용할 수 있습니다. 이러한 뷰는에서 액세스할 수는 **워크플로** 메뉴와 디자인 화면에서 상황에 맞는 메뉴에서 합니다.

 다음 표에서는 각 뷰의 이름과 설명을 보여 줍니다.

|메뉴/탭 옵션|설명|
|----------------------|-----------------|
|**순차 워크플로 보기**|선택 하 고 화면의 디자인을 마우스 오른쪽 단추로 클릭는 **SequentialWorkflow 보기** 표시 하려면 상황에 맞는 메뉴 옵션은 **순차 워크플로** 활동 기반 보여 주는 보기 그래픽 순차 워크플로의 표현입니다. 선택 또는 **SequentialWorkflow 보기** 에서 **워크플로** 메뉴.|
|**취소 처리기 보기**|선택 하 고 화면의 디자인을 마우스 오른쪽 단추로 클릭는 **취소 처리기 보기** 표시 하려면 상황에 맞는 메뉴 옵션은 **순차 워크플로** 뷰가 [CancellationHandlerActivity ](http://go.microsoft.com/fwlink?LinkID=65050) 워크플로와 연결 된 활동입니다. 선택 또는 **취소 처리기 보기** 에서 **워크플로** 메뉴.|
|**오류 처리기 보기**|선택 하 고 화면의 디자인을 마우스 오른쪽 단추로 클릭는 **오류 처리기 보기** 표시 하려면 상황에 맞는 메뉴 옵션은 **오류** 뷰가 [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) 워크플로와 연결 된 활동입니다. 선택 또는 **오류 처리기 보기** 에서 **워크플로** 메뉴.|

 유사한 방식에 대 한 자세한 내용은 참조 [활동 뷰 (레거시)](../workflow-designer/activity-views-legacy.md)합니다.

## <a name="see-also"></a>참고 항목

- [활동 뷰(레거시)](../workflow-designer/activity-views-legacy.md)
- [레거시 워크플로 프로젝트 만들기](../workflow-designer/creating-legacy-workflow-projects.md)
- [워크플로 제작 모드](http://go.microsoft.com/fwlink?LinkID=65014)