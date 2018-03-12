---
title: "CorrelatesOn 정의 대화 상자가 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 386d27e96ad1b3a04b9cdb8f76f96ee5e2ad6a46
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="correlateson-definition-dialog-box"></a>CorrelatesOn 정의 대화 상자
**CorrelatesOn** 대화 상자 편집 하려면 Windows 워크플로 디자이너에서 사용 됩니다는 <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> 의 속성을 <xref:System.ServiceModel.Activities.Receive> 활동입니다. 자세한 내용은 참조는 [수신](../workflow-designer/receive-activity-designer.md) 항목입니다.

 <xref:System.ServiceModel.Activities.Receive> 활동 간의 상관 관계는 워크플로에서 서비스 작업 간의 다양한 상호 연결 방식을 지정합니다.

 다음 표에 사용자 인터페이스 (UI) 요소는 **CorrelatesOn** 대화 상자.

|UI 요소|설명|
|----------------|-----------------|
|**CorrelatesWith**|메시지를 적절한 워크플로 인스턴스로 라우팅하는 데 사용되는 <xref:System.ServiceModel.Activities.CorrelationHandle>입니다.|
|**XPath 쿼리**|받은 메시지에서 상관 관계 데이터를 추출하는 데 사용되는 쿼리가 포함된 키/값 쌍입니다. 이것은 <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> 속성에 해당합니다. XPath 쿼리는 <xref:System.ServiceModel.MessageQuerySet> 개체에 포함되어 있습니다.|

## <a name="to-launch-the-correlateson-dialog-box"></a>CorrelatesOn 대화 상자를 시작하려면
 **수신** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 활동은 일반적으로 배치 합니다. 그러면 기본 <xref:System.ServiceModel.Activities.Receive>인 Receive라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. 선택 된 **수신** 의 (컬렉션) 텍스트 옆 줄임표 단추를 클릭 하 고 활동 디자이너는 **CorrelatesOn** 속성에 대 한 속성 표에 **CorrelatesOn 정의**  대화 상자를 표시 합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Activities.Receive>
- [상관 관계 이니셜라이저 추가 대화 상자](../workflow-designer/add-correlationinitializers-dialog-box.md)
- [추가 상관 관계 대화 상자](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)
- [상관 관계 초기화 대화 상자](../workflow-designer/initialize-correlation-dialog-box.md)