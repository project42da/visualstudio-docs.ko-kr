---
title: "콘텐츠 정의 대화 상자가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
caps.latest.revision: "3"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: fa0276e284f84eb6514fc407c9ce9be9cf24d8c4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="content-definition-dialog-box"></a>콘텐츠 정의 대화 상자
**콘텐츠 정의** 에 대화 상자를 사용 하는 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] 구성 하는 **콘텐츠** 의 속성은 <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, 및 <xref:System.ServiceModel.Activities.ReceiveReply> 작업을 합니다. [!INCLUDE[crabout](../test/includes/crabout_md.md)]이 상자를 사용 하는 activity designer 참조는 [보낼](../workflow-designer/send-activity-designer.md), [수신](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), 및 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) 항목입니다.  
  
 다음 표에 사용자 인터페이스 (UI) 요소는 **상관 관계 초기화** 대화 상자.  
  
|UI 요소|설명|  
|----------------|-----------------|  
|**메시지**|메시지 콘텐츠를 지정는 **메시지 데이터** 식 입력란 및 사용 하 여 유형은 **메시지 유형을** 드롭다운 목록 상자입니다. 기본적으로는 **콘텐츠 정의** 사용 하 여는 <xref:System.ServiceModel.Activities.ReceiveMessageContent>,이 필요한 한 <xref:System.ServiceModel.Channels.Message> 또는 메시지 계약 형식을 워크플로 서비스 정의 내에서.|  
|**매개 변수**|클릭는 **매개 변수** 라디오 단추를 사용 하 여 <xref:System.ServiceModel.Activities.ReceiveParametersContent>, 데이터 계약이 필요한입니다. 데이터 표를 사용하여 현재 워크플로의 가변 매개 변수에 값을 지정할 <xref:System.Activities.OutArgument> 키/값 쌍의 제네릭 컬렉션을 설정합니다.|  
  
 **콘텐츠 정의** 대화 상자를 사용 하 여는 **보낼**, **수신**, **ReceiveAndSendReply**, 및  **SendAndReceiveReply** 디자이너. 비슷한 방법으로 각각의 디자이너에 액세스할 수 있으며 여기서는 Receive 디자이너로 액세스 절차를 설명하겠습니다.  
  
 **수신** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 활동은 일반적으로 배치 합니다. 그러면 기본 <xref:System.ServiceModel.Activities.Receive>인 Receive라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. 선택 된 **수신** 활동 디자이너에 대 한 (콘텐츠) 텍스트 옆 줄임표 단추를 클릭 하 고는 **콘텐츠** 속성에 대 한 속성 표에 **콘텐츠 정의**대화 상자를 표시 합니다.  
  
 콘텐츠 내에서 지정할 수는 **메시지** 섹션에 대 한는 <xref:System.ServiceModel.Activities.ReceiveMessageContent> 활동 또는 **매개 변수** 섹션는 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 활동입니다.  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 디자이너 UI 도움말](../workflow-designer/workflow-designer-ui-help.md)