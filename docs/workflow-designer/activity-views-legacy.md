---
title: 활동 보기 (레거시) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- activities, activity views
- views, activity
- activity views
ms.assetid: 83dc68cd-2cb2-45c2-9a6e-10d82053171a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2cc053be2f9d11a9a1f3cd48c6c9d24e366410c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="activity-views-legacy"></a>활동 뷰(레거시)
제공 하는 활동의 여러 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)], 워크플로으로 구성 됨에서 일부의 디자인 뷰가 레거시 Windows 워크플로 디자이너에서 사용할 수 있습니다. 활동 디자이너를 끌어 올 때는 **도구 상자** 디자인 화면으로 이동 하 고 그 이후에 활동을 선택할 때마다 중 하나를 사용 하 여 여러 디자인 뷰 간에 전환할 수 있습니다는 **워크플로**메뉴 또는 선택 된 활동을 마우스 오른쪽 단추로 클릭 합니다. 또한 선택된 항목의 이름 위로 포인터를 옮기면 드롭다운 탭 집합이 나타나 여러 뷰 사이를 전환할 때 사용할 수 있습니다.

 모든 활동에 하나 이상의 보기가 있습니다. 활동 디자이너를 끌어 올 때 표시 된 기본 보기는 **도구 상자** 디자인 화면으로 합니다. 이 활동 기본 뷰는으로 사용할 수는 **[활동 유형] 보기** 메뉴 및 예를 들어 탭에서 옵션 **병렬 보기**합니다. 대부분의 활동에 추가 뷰가 있으며, 활동마다 서로 다른 뷰를 가질 수 있습니다. 예를 들어는 [TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093) 활동에는 보상 보기가 및 [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030) 활동에는 이벤트 보기입니다. 대부분의 Windows Workflow Foundation과 함께 제공 되는 활동에는 **취소 처리기 보기** 및 **보기 오류** 보기로 뷰 디자인는 [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) 및 [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) 연관 됩니다.

 다음 표에서는 각 뷰의 이름과 설명을 보여 줍니다.

|메뉴/탭 옵션|설명|
|----------------------|-----------------|
|**[활동 유형] 보기**|선택한 활동의 기본 그래픽 표현을 보려면 이 메뉴 또는 탭 옵션을 선택합니다.|
|**취소 처리기 보기**|이 메뉴 또는 탭 옵션 보기는 [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) 사용 하면 선택한 활동과 연결 합니다.|
|**오류 처리기 보기**|이 메뉴 또는 탭 옵션 보기는 [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) 사용 하면 선택한 활동과 연결 합니다.|
|**보정 핸들러 보기**|이 메뉴 또는 탭 옵션 보기는 [CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053) 에서 선택한 내용과 연관 [TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093)합니다.|
|**이벤트 핸들러 보기**|이 메뉴 또는 탭 옵션 보기는 [EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018) 에서 선택한 내용과 연관 된 [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030)합니다.|

 유사한 방식에 대 한 정보를 참조 하십시오. [순차 워크플로 뷰 (레거시)](../workflow-designer/sequential-workflow-views-legacy.md)합니다.

## <a name="see-also"></a>참고자료

- [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)
- [순차 워크플로 뷰(레거시)](../workflow-designer/sequential-workflow-views-legacy.md)