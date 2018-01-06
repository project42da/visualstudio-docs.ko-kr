---
title: "CorrelationScope 활동 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.ServiceModel.Activities.CorrelationScope.UI
ms.assetid: 75f20664-9042-464d-8e2b-148d365a2286
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 71f2ce7f69351c0e829f43f9e491304db39e6cea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="correlationscope-activity-designer"></a>CorrelationScope 활동 디자이너
**CorrelationScope** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.ServiceModel.Activities.CorrelationScope> 활동을 사용 하 여 자식 메시징 활동을 암시적으로 관리는 <xref:System.ServiceModel.Activities.CorrelationHandle> 개체입니다.  
  
## <a name="the-correlationscope-activity"></a>CorrelationScope 활동  
 <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> 속성은 자식 메시징 활동을 관리하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>을 지정합니다. <xref:System.ServiceModel.Activities.Send>에 포함된 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.CorrelationScope.Body%2A> 활동은 해당 활동을 포함하는 <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> 활동의 <xref:System.ServiceModel.Activities.CorrelationScope> 속성을 사용하여 상호 연결을 수행하도록 구성됩니다.  
  
### <a name="using-the-correlationscope-activity-designer"></a>CorrelationScope 활동 디자이너 사용  
 **CorrelationScope** 활동 디자이너에서 확인할 수 있습니다는 **메시징** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구상자** 탭의 왼쪽에는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)  
  
 **CorrelationScope** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면입니다. 그렇기 때문에 <xref:System.ServiceModel.Activities.CorrelationScope> 기본값 활동 **DisplayName** CorrelationScope의 합니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **CorrelationScope** 활동 디자이너 또는 **DisplayName** 상자는 **속성** 창.  
  
 지정 하는 <xref:System.ServiceModel.Activities.CorrelationHandle> 옆에 있는 줄임표 단추를 클릭을 사용 하는 자식 메시징 활동은 **CorrelatesWith** 필드에 **속성** 창에 표시 된 **식 편집기**  대화 상자. 이 속성은 활동 디자이너 화면에서도 설정할 수 있습니다.  
  
 범위가 상관 관계 내부 활동 내에서 해당 디자이너를 끌어 놓아 지정는 **본문** 상자 안에 **CorrelationScope** 디자이너입니다.  
  
### <a name="the-correlationscope-properties"></a>CorrelationScope 속성  
 다음 표에서는 <xref:System.ServiceModel.Activities.CorrelationScope> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성에 편집할 **속성** 창 또는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 디자이너 화면 및 종종 모두에서 합니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.InitializeCorrelation> 활동의 선택적 이름입니다.|  
|<xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A>|False|자식 메시징 활동을 관리하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>을 지정합니다. 이 속성을 설정하지 않으면 <xref:System.ServiceModel.Activities.CorrelationScope>는 자동으로 <xref:System.ServiceModel.Activities.CorrelationHandle>을 만듭니다.|  
|<xref:System.ServiceModel.Activities.CorrelationScope.Body%2A>|False|상관 관계 범위 내에 활동을 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [수신](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [보내기](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)