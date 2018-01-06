---
title: "추가 CorrelationInitializers 대화 상자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: AddCorrelationInitializers.UI
ms.assetid: c0517467-d54a-4ee6-aef0-c19b96b6f395
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 4c4d8e07aa172aef524b4d85bda5ad8efdfb509f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="add-correlationinitializers-dialog-box"></a>상관 관계 이니셜라이저 추가 대화 상자
**상관 관계 이니셜라이저 추가** 에 대화 상자를 사용 하는 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] 구성 하는 **CorrelationInitializers** 의 속성은 <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, 및 <xref:System.ServiceModel.Activities.ReceiveReply> 활동입니다. [!INCLUDE[crabout](../test/includes/crabout_md.md)]이 상자를 사용 하는 activity designer 참조는 [보낼](../workflow-designer/send-activity-designer.md), [수신](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), 및 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) 항목입니다.  
  
 이 대화 상자에서 지정한 컬렉션의 상관 관계 이니셜라이저는 쿼리 기반, 컨텍스트, 콜백 컨텍스트 또는 메시징 활동 간의 요청-회신 상관 관계를 초기화할 수 있습니다.  
  
 다음 표에 사용자 인터페이스 (UI) 요소는 **상관 관계 이니셜라이저 추가** 대화 상자.  
  
|UI 요소|설명|  
|----------------|-----------------|  
|**이니셜라이저 추가**|클릭는 **추가 초기화** 상자 컬렉션에 이니셜라이저를 추가할 수 있습니다.|  
|**상관 관계 유형**|상관 관계 이니셜라이저의 형식을 지정합니다. 다음 네 가지 형식 중에서 선택할 수 있습니다.<br /><br /> 1.  <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>를 지정하는 콜백 상관 관계 이니셜라이저<br />2.  <xref:System.ServiceModel.Activities.CorrelationInitializer>를 지정하는 컨텍스트 상관 관계 이니셜라이저<br />3.  <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>를 지정하는 요청-회신 상관 관계 이니셜라이저<br />4.  <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>를 지정하는 쿼리 상관 관계 이니셜라이저<br /><br /> 편집 하 여 **CorrelationType**<br /><br /> 1.  탭의 특정 행에는 **이니셜라이저 추가** DataGrid 합니다.<br />2.  Ctrl + Tab 키를 눌러 포커스를 설정할 **CorrelationTypeComboBox**<br />3.  Alt + 아래쪽 팝업을 눌러는 **ComboBox** 하 고 편집 합니다.|  
|**XPath 쿼리**|들어오는 메시지와 나가는 메시지에서 상관 관계 데이터를 추출하는 데 사용되는 쿼리가 포함된 키/값 쌍입니다. 이 목록은 <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 형식을 사용하는 경우에만 유효합니다.|  
  
## <a name="to-launch-the-add-correlation-initializers-dialog-box"></a>상관 관계 이니셜라이저 추가 대화 상자를 시작하려면  
 **상관 관계 이니셜라이저 추가** 대화 상자를 사용 하 여는 **보낼**, **수신**, **ReceiveAndSendReply**, 및  **SendAndReceiveReply** 디자이너. 각각의 경우와 관련 된 사례는에 액세스 하는 **수신** 디자이너 절차를 설명 하기 위해 여기에 사용 됩니다.  
  
 **수신** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 활동은 일반적으로 배치 합니다. 그러면 기본 <xref:System.ServiceModel.Activities.Receive>인 Receive라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. 선택 된 **수신** 의 (컬렉션) 텍스트 옆 줄임표 단추를 클릭 하 고 활동 디자이너는 **CorrelationInitializers** 속성에 대 한 속성 표에 **추가 상관 관계 이니셜라이저** 대화 상자를 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [추가 상관 관계 대화 상자](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)   
 [상관 관계 초기화 대화 상자](../workflow-designer/initialize-correlation-dialog-box.md)