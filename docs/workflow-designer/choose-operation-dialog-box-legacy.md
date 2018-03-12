---
title: "작업 선택 대화 상자 (레거시) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Workflow.Activities.Design.OperationPickerDialog.UI
ms.assetid: bc3ec902-7797-494e-af48-e70c97eb6779
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b2d26d97fd147ea39e8d074ea65f4a4121f9be71
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="choose-operation-dialog-box-legacy"></a>작업 선택 대화 상자(레거시)

이 항목에서는 설명 방법을 사용 하 여는 **작업 선택** 레거시 Windows 워크플로 디자이너의 대화 상자. 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.

 **작업 선택** 과 연결할 작업 선택 대화 상자를 사용 하는 한 <xref:System.Workflow.Activities.ReceiveActivity> 활동 또는 <xref:System.Workflow.Activities.SendActivity> 활동입니다. 이 대화 상자를 사용 하 여 해당 작업을 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: WCF 계약 작업 구현 (레거시)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md) 및 [하는 방법: WCF 계약 작업 호출 (레거시)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)합니다.

 다음 표에 사용자 인터페이스 (UI) 요소는 **작업 선택** 대화 상자.

|UI 요소|설명|
|----------------|-----------------|
|**계약 추가**|자동으로 새 계약을 만듭니다. 이 계약에 새 작업을 정의할 수 있습니다. 이 UI 요소는 <xref:System.Workflow.Activities.ReceiveActivity>에만 사용됩니다.|
|**추가 작업**|새 작업에서 만든 새 계약을 추가 **작업 선택** 대화 상자. **참고:** 새 작업을 통해 만든 계약만 추가할 수 있습니다는 **작업 선택** 대화 상자. <br /><br /> 이 UI 요소는 <xref:System.Workflow.Activities.ReceiveActivity>에만 사용됩니다.|
|**가져오기...**|이전에 정의된 계약을 가져오며 해당 계약에서 작업을 선택할 수 있습니다.|
|**작업 이름**|현재 선택한 작업의 이름입니다. 이 입력란을 통해 작업을 만든 경우에 편집할 수는 **작업 선택** 대화 상자.|
|**매개 변수**|현재 선택한 작업에 대한 매개 변수 정의가 포함된 탭입니다. **참고:** 매개 변수 정의 통해 작업을 만든 경우에 변경할 수 있습니다는 **작업 선택** 대화 상자.|
|**속성**|클라이언트와 서비스 간에 보낸 메시지의 <xref:System.Net.Security.ProtectionLevel> 설정이 포함된 탭입니다. **참고:** 이 탭은 통해 작업을 만든 경우에 사용할 수는 **작업 선택** 대화 상자.|
|**권한**|해당 작업을 호출할 수 있는 사용자의 <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionName%2A> 및 <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionRole%2A> 속성이 포함된 탭입니다. 예를 들어 관리자 그룹에서 사용자가 해당 작업을 호출할 수만 씁니다 "Administrators"의 **역할** 입력란.<br /><br /> 이 탭이 두 작업 모두를 통해 만들어진 설정는 **ChooseOperation** 대화 상자를 통해 가져온 작업 하 고는 **가져오기** 단추입니다.|

> [!NOTE]
> **작업 선택** 계약이 나 작업만 다른에서 사용 되는 대화 상자 표시 <xref:System.Workflow.Activities.SendActivity> 워크플로의 활동에에서 있습니다. 마찬가지로,는 **작업 선택** 대화 상자에 대 한 <xref:System.Workflow.Activities.ReceiveActivity> 계약이 나 다른에서 사용 되는 작업 활동 표시 **ReceiveActivity** 워크플로의 활동에에서 있습니다.

## <a name="see-also"></a>참고 항목

- [방법: WCF 계약 작업 구현 (레거시)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)
- [방법: WCF 계약 작업 호출 (레거시)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)
- [Windows Workflow Foundation용 레거시 디자이너 UI 도움말](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)