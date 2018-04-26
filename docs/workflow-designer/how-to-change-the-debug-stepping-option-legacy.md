---
title: '워크플로 디자이너-방법: 단계별 디버깅 옵션 (레거시)를 변경 합니다.'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
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
ms.openlocfilehash: 31047cedd4e8772b9ebab4ef238a8fe32bc07663
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>방법: 단계별 디버깅 옵션 변경(레거시)

이 항목에서는 단계별 디버깅 옵션 동시 작업 수 있는 Windows WF (Workflow Foundation) 응용 프로그램은 레거시 Windows 워크플로 디자이너에서 변경 하는 방법에 설명 합니다. WinFX 또는.NET Framework 버전 3.5 대상으로 해야 하는 경우 레거시 워크플로 디자이너를 사용 합니다.

와 같은 동시에 실행 되는 레거시 활동을 디버깅할 때 **ParallelActivity** 또는 **ConditionedActivityGroup**, 두 옵션 중 하나를 사용 하 여 코드를 단계별로 실행할 수 있습니다.

레거시 워크플로 프로젝트에서 단계별 디버깅 옵션을 변경하려면 다음 단계를 따르세요.

## <a name="procedures"></a>절차

### <a name="to-change-the-debug-stepping-option"></a>디버그 단계별 옵션을 변경하려면

1.  Visual Studio를 시작합니다.

2.  기존 레거시 워크플로 프로젝트를 열거나.NET Framework 버전 3.5 또는 WinFX 동시 활동 및를 대상으로 사용 하는 새 프로젝트를 만듭니다.

3.  에 **워크플로** 메뉴 레거시 워크플로 디자이너에서 가리키고 **디버그**를 차례로 **단계별 실행 옵션**합니다.

4.  선택 **인스턴스** 또는 **분기**합니다.

## <a name="see-also"></a>참고자료

- [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)
- [단계별 디버깅 옵션(레거시)](../workflow-designer/debug-stepping-options-legacy.md)