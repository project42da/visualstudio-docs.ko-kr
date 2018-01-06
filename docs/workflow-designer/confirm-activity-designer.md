---
title: "Confirm 활동 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Confirm.UI
ms.assetid: c753b67b-b0e7-462a-bb4e-ba8db04a078d
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 51e44d98aaec929f1194420227a6a3871dc4f2ad
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="confirm-activity-designer"></a>Confirm 활동 디자이너
**확인** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.Confirm> 활동입니다.  
  
## <a name="the-confirm-activity"></a>Confirm 활동  
 <xref:System.Activities.Statements.Confirm> 활동은 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>에 포함된 활동에 대해 <xref:System.Activities.Statements.CompensableActivity>를 명시적으로 호출합니다. <xref:System.Activities.Statements.Confirm>, <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> 또는 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>의 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>에서 <xref:System.Activities.Statements.CompensableActivity> 활동을 사용하지 않는 경우 <xref:System.Activities.Statements.Confirm.Target%2A> 속성을 지정해야 합니다.  
  
 <xref:System.Activities.Statements.CompensationToken>에 의해 지정된 <xref:System.Activities.Statements.Compensate.Target%2A>은 <xref:System.Activities.Statements.CompensableActivity>의 <xref:System.Activities.Statements.CompensableActivity.Body%2A>가 성공적으로 완료된 후 <xref:System.Activities.Statements.CompensableActivity>를 명시적으로 확인하거나 보정하는 수단을 제공합니다.  
  
### <a name="using-the-confirm-activity-designer"></a>Confirm 활동 디자이너 사용  
 **확인** 활동 디자이너에서 확인할 수 있습니다는 **트랜잭션** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**탭의 왼쪽에는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)  
  
 **확인** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 활동은 일반적으로, 등 배치는 <xref:System.Activities.Statements.Sequence>합니다. 그러면 기본 <xref:System.Activities.Statements.Confirm>인 Confirm이라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. <xref:System.Activities.Activity.DisplayName%2A> 값일 수의 헤더에서 편집할는 **확인** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.  
  
### <a name="the-confirm-properties"></a>Confirm 속성  
 다음 표에서는 <xref:System.Activities.Statements.Confirm> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. <xref:System.Activities.Activity.DisplayName%2A> 속성은 속성 표 또는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있지만 <xref:System.Activities.Statements.Confirm.Target%2A> 속성은 반드시 속성 표에서 편집해야 합니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.CancellationScope> 활동의 선택적 이름을 지정합니다. 기본값은 Confirm입니다.|  
|<xref:System.Activities.Statements.Confirm.Target%2A>|True|이 <xref:System.Activities.InArgument%601> 활동의 <xref:System.Activities.Statements.CompensationToken>이 들어 있는 <xref:System.Activities.Statements.Confirm>을 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [트랜잭션](../workflow-designer/transaction-activity-designers.md)   
 [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [보정](../workflow-designer/compensate-activity-designer.md)   
 [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)