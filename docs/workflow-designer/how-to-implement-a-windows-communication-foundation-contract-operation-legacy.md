---
title: "방법: Windows Communication Foundation 계약 작업 구현(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d6aeb20e-fac8-4a9d-bd26-ae78bef96b41
caps.latest.revision: 7
caps.handback.revision: 7
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 방법: Windows Communication Foundation 계약 작업 구현(레거시)
이 항목에서는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 하는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]를 사용하여 [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] 계약 작업을 구현하는 방법에 대해 설명합니다.  
  
 **ReceiveActivity** 활동을 도구 상자에서 워크플로 디자인 화면으로 끌어 온 후에는 새 [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] 계약을 만들거나 기존 계약을 가져오고 작업을 구현합니다.[작업 선택 대화 상자\(레거시\)](../workflow-designer/choose-operation-dialog-box-legacy.md)를 통해 계약 및 작업을 선택하거나 만듭니다.  
  
### WCF 계약 작업을 구현하려면  
  
1.  디자이너에서 **ReceiveActivity** 활동을 두 번 클릭하거나 **속성** 창에서 **ServiceOperationInfo** 속성 옆의 줄임표를 클릭합니다.  
  
2.  다음 작업 중 하나를 수행합니다.  
  
    -   대화 상자의 오른쪽 위 모퉁이에서 **계약 추가**를 클릭합니다.이렇게 하면 새 [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] 계약 및 작업이 자동으로 만들어집니다.  
  
         \-또는\-  
  
    -   대화 상자의 오른쪽 위 모퉁이에서 **가져오기**를 클릭합니다.[.NET 유형 선택 대화 상자\(레거시\)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md)가 열립니다.원하는 계약이 들어 있는 어셈블리나 프로젝트를 검색합니다.계약을 선택하고 **확인**을 클릭합니다.  
  
     계약을 만들거나 가져온 다음에는 만들거나 가져온 해당 계약에 새 작업을 추가할 수 있습니다.새 작업을 추가하려면 계약을 선택하고 대화 상자의 오른쪽 위 모퉁이에서 **작업 추가**를 클릭합니다.작업 추가가 완료되면 3단계로 진행합니다.  
  
3.  **ReceiveActivity** 활동과 연결할 작업을 선택합니다.작업의 이름, 매개 변수, 속성 및 사용 권한 설정을 변경하여 작업에 대한 정의를 조작할 수 있습니다.  
  
     이름을 변경하려면 **작업 이름** 텍스트 상자에 새 이름을 입력합니다.  
  
     작업의 매개 변수에 액세스하려면 **매개 변수** 탭을 클릭합니다.매개 변수의 이름, 형식 또는 방향을 변경할 뿐만 아니라 작업에서 매개 변수를 추가하거나 삭제할 수 있습니다.  
  
     작업 보호 수준 및 작업의 지원되는 메시지 교환 기능에 액세스하려면 **속성** 탭을 클릭합니다.  
  
     작업을 구현할 수 있는 그룹을 지정하려면 **사용 권한** 탭을 클릭합니다.  
  
4.  **확인**을 클릭하면 구현되고 있는 작업의 이름이 **ReceiveActivity** 활동에 표시됩니다.  
  
5.  해당 작업을 구현하는 데 사용할 워크플로 활동을 **ReceiveActivity** 활동 내에 배치합니다.  
  
## 참고 항목  
 [작업 선택 대화 상자\(레거시\)](../workflow-designer/choose-operation-dialog-box-legacy.md)   
 [방법: WCF 계약 작업 호출\(레거시\)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)   
 [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)