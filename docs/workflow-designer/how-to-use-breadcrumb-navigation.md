---
title: '방법: 이동 경로 탐색을 사용 하 여 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4a688056-37dc-406a-9071-be2141e192fe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 97c88a8c47bfaa2e1ccd135baec95f19a49c4e5a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-breadcrumb-navigation"></a>방법: 이동 경로 탐색 사용

Windows 워크플로 디자이너에 표시 되는 활동 집합을 변경 하려면 세 가지 주요 방법이 있습니다.

1.  두 번 클릭하여 자식 활동으로 드릴인합니다.

2.  이동 경로 탐색 막대의 단추를 클릭하여 상위 활동으로 이동합니다.

3.  현재 위치의 활동을 확장하거나 축소합니다.

### <a name="using-breadcrumb-navigation"></a>이동 경로 탐색 사용

1.  [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 활동을 두 번 클릭하여 루트 활동을 클릭한 활동으로 변경합니다. 그러면 클릭한 활동이 루트에서 완전히 확장되고 상위 항목이 이동 경로 탐색 막대에 표시됩니다. 이를 활동 드릴인/드릴아웃이라고도 합니다.

2.  현재 루트 활동의 상위 항목으로 이동하려면 이동 경로 탐색 막대에서 해당 활동을 클릭합니다.

### <a name="expanding-or-collapsing-an-activity-in-place"></a>현재 위치의 활동 확장 또는 축소

1.  활동의 갈매기형 펼침 단추를 클릭하면 현재 위치의 활동이 확장되거나 축소됩니다.

2.  이 단추를 클릭하여 확장 상태를 변경하면 확장의 새로운 상태가 XAML에 저장됩니다.

    > [!WARNING]
    > 일부 활동은 현재 위치에서 확장되지 않을 수도 있습니다. 현재 위치에서 활동을 확장할 수 없는 경우는 두 가지입니다. 즉, 활동의 부모가 현재 위치에서 자식을 확장하도록 허용하지 않는 경우(예: 순서도의 활동은 현재 위치에서 확장 불가능) 또는 활동 디자이너 자체에서 현재 위치에서의 확장을 허용하지 않는 경우입니다. [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에 포함된 활동 디자이너는 후자와 같이 작동하지 않지만 일부 사용자 지정 활동은 이와 같은 작동을 보일 수도 있습니다.

### <a name="expanding-all-or-collapsing-all-activities"></a>모든 활동 확장명 또는 축소

1.  사용 하 여는 **모두 확장** 및 **모두 축소** 단추는 사용자 인터페이스를 확장 하거나 축소 하는 모든 활동 현재의 이동 경로 탐색 루트 아래에 있습니다. 모두 확장명 및 모두 축소는 전역 상태입니다. 즉, 이동 경로 탐색을 모두 확장을 사용 하 여 루트 활동을 변경 또는 모두 축소 상태를 클릭할 때까지 유지 되도록 **복원**합니다.

2.  또는 모두 축소 상태를 모두 확장 적용 후 클릭할 수 있습니다는 **복원** 돌아가서 각 활동에 적용 되었던 상태를 보면에 나타나는 단추입니다.

    > [!WARNING]
    > 경우 활동, 같은 <xref:System.Activities.Statements.Flowchart>, 제외 된 확장에서 현재 위치와 관련 된 기능는 **모두 확장** 및 **모두 축소** 단추가 비활성화 됩니다는 **순서도**  디자이너입니다. 에 대 한 자세한 내용은 **순서도** 디자이너, 참조는 [순서도](../workflow-designer/flowchart-activity-designer.md) 항목입니다.

    > [!WARNING]
    > 모두 확장에서 특수 한 효과 갖도록 **스위치** 및 **TryCatch** 활동 디자이너입니다. 클릭할 때 **모두 확장**, 모든 switch case와 모든 try/catch/finally 블록이 표시 됩니다. 클릭 하면 **복원** 또는 **모두 축소** 는 개별 e/블록의 내용을 보려면 클릭 수를 기본 상태로 이러한 디자이너를 반환 합니다.