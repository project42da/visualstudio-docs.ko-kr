---
title: '방법: Windows Communication Foundation 계약 작업 (레거시)를 구현 합니다. | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d6aeb20e-fac8-4a9d-bd26-ae78bef96b41
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 71bf4e4e6f5abc1d2984362396f21f3c613de795
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-implement-a-windows-communication-foundation-contract-operation-legacy"></a>방법: Windows Communication Foundation 계약 작업 구현(레거시)
이 항목에서는 구현 하는 방법을 설명는 [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] 대상으로 하는 레거시 Windows 워크플로 디자이너를 사용 하 여 작업 계약에서 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]합니다.

 끌어 놓은 후는 **ReceiveActivity** 워크플로 디자인 화면에 도구 상자의 활동을 하거나 만들게 될 새 [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] 계약 또는 기존 계약을 가져오고 작업을 구현 합니다. 선택 및 계약을 만들고 해당 작업을 통해는 [선택 작업 대화 상자 (레거시)](../workflow-designer/choose-operation-dialog-box-legacy.md)합니다.

### <a name="to-implement-a-wcf-contract-operation"></a>WCF 계약 작업을 구현하려면

1.  두 번 클릭은 **ReceiveActivity** 디자이너의 활동 옆의 줄임표를 클릭 하거나는 **ServiceOperationInfo** 속성에는 **속성** 창.

2.  다음 작업 중 하나를 수행합니다.

    -   클릭 **추가 계약** 대화 상자의 오른쪽 위 모퉁이에 있습니다. 이렇게 하면 새 [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] 계약 및 작업이 자동으로 만들어집니다.

         -또는-

    -   클릭 **가져오기** 대화 상자의 오른쪽 위 모퉁이에 있습니다. [찾아.NET 유형 선택 대화 상자 (레거시)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) 열립니다. 원하는 계약이 들어 있는 어셈블리나 프로젝트를 검색합니다. 계약을 선택 하 고 클릭 **확인**합니다.

     계약을 만들거나 가져온 다음에는 만들거나 가져온 해당 계약에 새 작업을 추가할 수 있습니다. 새 작업을 추가 하려면 계약을 선택 하 고 클릭 **Add 작업** 대화 상자의 오른쪽 위 모퉁이에 있습니다. 작업 추가가 완료되면 3단계로 진행합니다.

3.  와 연결 하려는 작업 선택은 **ReceiveActivity** 활동입니다. 작업의 이름, 매개 변수, 속성 및 사용 권한 설정을 변경하여 작업에 대한 정의를 조작할 수 있습니다.

     이름을 변경 하려면에 새 이름을 입력 된 **작업 이름** 입력란.

     클릭는 **매개 변수** 작업의 매개 변수에 액세스 하려면 탭 합니다. 매개 변수의 이름, 형식 또는 방향을 변경할 뿐만 아니라 작업에서 매개 변수를 추가하거나 삭제할 수 있습니다.

     클릭는 **속성** 작업의 작업 보호 수준 및 지원 되는 메시지 교환 기능에 액세스 하려면 탭 합니다.

     클릭는 **권한을** 작업을 구현할 수 있는 그룹을 탭 합니다.

4.  클릭 **확인** 및 **ReceiveActivity** 활동은 구현 하는 작업에 대 한 작업 이름에 표시 됩니다.

5.  워크플로 활동 내에서 해당 작업의 구현에 사용할 것인지를 배치에서 **ReceiveActivity** 활동입니다.

## <a name="see-also"></a>참고자료

- [작업 선택 대화 상자(레거시)](../workflow-designer/choose-operation-dialog-box-legacy.md)
- [방법: WCF 계약 작업 호출 (레거시)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)
- [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)