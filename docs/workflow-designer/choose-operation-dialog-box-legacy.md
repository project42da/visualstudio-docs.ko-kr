---
title: "작업 선택 대화 상자(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Workflow.Activities.Design.OperationPickerDialog.UI"
ms.assetid: bc3ec902-7797-494e-af48-e70c97eb6779
caps.latest.revision: 10
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# 작업 선택 대화 상자(레거시)
이 항목에서는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]에서 **작업 선택** 대화 상자를 사용하는 방법에 대해 설명합니다.레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.  
  
 **작업 선택** 대화 상자는 <xref:System.Workflow.Activities.ReceiveActivity> 활동이나 <xref:System.Workflow.Activities.SendActivity> 활동과 연결할 작업을 선택하는 데 사용됩니다.이러한 동작과 관련하여 이 대화 상자를 사용하는 방법에 대한 자세한 내용은 [방법: WCF 계약 작업 구현\(레거시\)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md) 및 [방법: WCF 계약 작업 호출\(레거시\)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)을 참조하십시오.  
  
 다음 표에서는 **작업 선택** 대화 상자의 UI\(사용자 인터페이스\) 요소에 대해 설명합니다.  
  
|UI 요소|설명|  
|-----------|--------|  
|**계약 추가**|자동으로 새 계약을 만듭니다.이 계약에 새 작업을 정의할 수 있습니다.이 UI 요소는 <xref:System.Workflow.Activities.ReceiveActivity>에만 사용됩니다.|  
|**작업 추가**|**작업 선택** 대화 상자에서 만든 새 계약에 새 작업을 추가합니다. **Note:**  **작업 선택** 대화 상자를 통해 만든 계약에만 새 작업을 추가할 수 있습니다. <br /><br /> 이 UI 요소는 <xref:System.Workflow.Activities.ReceiveActivity>에만 사용됩니다.|  
|**가져오기...**|이전에 정의된 계약을 가져오며 해당 계약에서 작업을 선택할 수 있습니다.|  
|**작업 이름**|현재 선택한 작업의 이름입니다.이 텍스트 상자는 **작업 선택** 대화 상자를 통해 작업을 만든 경우에만 편집할 수 있습니다.|  
|**매개 변수**|현재 선택한 작업에 대한 매개 변수 정의가 포함된 탭입니다. **Note:**  매개 변수 정의는 **작업 선택** 대화 상자를 통해 작업을 만든 경우에만 변경할 수 있습니다.|  
|**속성**|클라이언트와 서비스 간에 보낸 메시지의 <xref:System.Net.Security.ProtectionLevel> 설정이 포함된 탭입니다. **Note:**  이 탭은 **작업 선택** 대화 상자를 통해 작업을 만든 경우에만 사용할 수 있습니다.|  
|**사용 권한**|해당 작업을 호출할 수 있는 사용자의 <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionName%2A> 및 <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionRole%2A> 속성이 포함된 탭입니다.예를 들어 Administrators 그룹의 사용자만 해당 작업을 호출할 수 있으면 **역할** 텍스트 상자에 "Administrators"를 씁니다.<br /><br /> 이 탭은 **작업선택** 대화 상자를 통해 만든 작업과 **가져오기** 단추를 통해 가져온 작업 모두에 사용할 수 있습니다.|  
  
> [!NOTE]
>  **작업 선택** 대화 상자에는 워크플로의 다른 <xref:System.Workflow.Activities.SendActivity> 활동에서 사용하는 계약이나 작업만 표시됩니다.마찬가지로 <xref:System.Workflow.Activities.ReceiveActivity> 활동에 대한 **작업 선택** 대화 상자에는 워크플로의 다른 **ReceiveActivity** 활동에서 사용하는 계약이나 작업만 표시됩니다.  
  
## 참고 항목  
 [방법: WCF 계약 작업 구현\(레거시\)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)   
 [방법: WCF 계약 작업 호출\(레거시\)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Windows Workflow Foundation용 레거시 디자이너 UI 도움말](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)