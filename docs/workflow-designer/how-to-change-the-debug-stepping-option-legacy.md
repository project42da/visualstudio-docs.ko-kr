---
title: '방법: 단계별 디버깅 옵션 (레거시) 변경 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aedb8e738dc2e6ca2b066dd9a2cd42e332bbd8be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>방법: 단계별 디버깅 옵션 변경(레거시)
이 항목에서는 단계별 디버깅 옵션을 변경 하는 방법을 설명 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 동시 동작 있는 레거시 Windows 워크플로 디자이너에서 응용 프로그램입니다. 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.

 와 같은 동시에 실행 되는 레거시 활동을 디버깅할 때 **ParallelActivity** 또는 **ConditionedActivityGroup**, 두 옵션 중 하나를 사용 하 여 코드를 단계별로 실행할 수 있습니다.

 레거시 워크플로 프로젝트에서 단계별 디버깅 옵션을 변경하려면 다음 단계를 따르세요.

## <a name="procedures"></a>절차

#### <a name="to-change-the-debug-stepping-option"></a>디버그 단계별 옵션을 변경하려면

1.  Visual Studio를 시작합니다.

2.  기존 레거시 워크플로 프로젝트를 열거나 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 하며 동시 활동을 사용하는 새 프로젝트를 만듭니다.

3.  에 **워크플로** 레거시의 메뉴 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], 가리킨 **디버그**를 차례로 **단계별 실행 옵션**합니다.

4.  선택 **인스턴스** 또는 **분기**합니다.

## <a name="see-also"></a>참고자료

- [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)
- [단계별 디버깅 옵션(레거시)](../workflow-designer/debug-stepping-options-legacy.md)