---
title: "Visual Studio 시작 시간 최적화 | Microsoft 문서"
ms.custom: 
ms.date: 8/31/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- startup time [Visual Studio]
- optimizing startup time [Visual Studio]
- speed up start time [Visual Studio]
ms.assetid: d1508121-8499-4084-8eb5-fa89fa7b17d3
caps.latest.revision: 4
author: mikejo
ms.author: mikejo
manager: ghogen
f1_keywords:
- vs.performancecenter
ms.translationtype: HT
ms.sourcegitcommit: 4306111cd49a5299bfa5d4e5e22b212bc7799fe2
ms.openlocfilehash: 8e419de02104d30344b32e28174bd7de41f91677
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---

# <a name="optimize-visual-studio-startup-time"></a>Visual Studio 시작 시간 최적화
이상적으로 Visual Studio는 항상 최대한 빨리 시작되어야 합니다. 그러나 시작 시 Visual Studio 확장 및 열린 도구 창이 자동으로 로드되기 때문에 시작 시간이 느려질 수 있습니다. **Visual Studio 성능 관리 창**에서 Visual Studio 시작 시간에 영향을 미치는 확장과 기능을 확인하고 이러한 확장과 기능의 로드 동작을 제어할 수 있습니다.

성능 향상에 대한 더 일반적인 팁은 [Visual Studio 성능 팁과 요령](../ide/visual-studio-performance-tips-and-tricks.md)을 참조하세요.

## <a name="control-startup-behavior"></a>시작 동작 제어

Visual Studio 2017에서는 시작 시간이 늘어나지 않도록 요청 시 로드 방법을 사용하여 시작 시 확장이 로드되지 않도록 합니다. 즉, Visual Studio가 시작된 후 즉시 확장이 열리지 않고 시작 후 필요에 따라 열리도록 하는 동작입니다. 또한 이전 Visual Studio 세션에서 열려 있는 도구 창으로 인해 시작 시간이 느려질 수 있으므로 Visual Studio는 시작 시간에 영향을 주지 않도록 보다 지능적인 방식으로 도구 창을 엽니다.

Visual Studio에서 시작 속도가 느린 것을 감지하면 속도 저하를 초래하는 확장이나 도구 창을 알려주는 팝업 메시지가 나타납니다. 이 메시지는 **Visual Studio 성능 관리** 대화 상자에 대한 링크도 제공합니다. **도움말 > Visual Studio 성능 관리** 메뉴 명령을 사용하여 이 창을 열 수도 있습니다.

![Visual Studio 성능 관리에 ‘... 확장으로 인해 Visual Studio가 느려집니다’라는 팝업이 나타납니다.](../ide/media/vside_perfdialog_popup.png)

이 대화 상자에는 시작 성능에 영향을 미치는 확장 및 도구 창이 나열됩니다. 이 대화 상자에서 확장 및 도구 창 설정을 변경하여 시작 성능을 향상할 수 있습니다.

### <a name="change-extension-settings"></a>확장 설정 변경

확장으로 인해 Visual Studio 시작 속도가 느려지는 경우 확장 형식 중 하나를 선택하면 **Visual Studio 성능 관리** 대화 상자에 해당 확장이 나타납니다. 이 대화 상자에는 시작 시, 솔루션 로딩 시 및 편집기에서 입력 시 성능에 영향을 미치는 확장이 표시됩니다.

![Visual Studio 성능 관리 - 확장 보기](../ide/media/vside_perfdialog_extensions.png)

시작, 솔루션 로드 또는 입력 시간에 대한 영향이 지나치게 높은 경우, **사용 안 함** 단추를 선택하여 해당 시나리오에 대한 확장을 사용하지 않도록 설정합니다. 확장 관리자 또는 Visual Studio 성능 관리 대화 상자를 통해 이후 세션에 확장을 언제든 다시 사용할 수 있습니다.

### <a name="change-tool-window-settings"></a>도구 창 설정 변경

도구 창으로 인해 Visual Studio 시작 속도가 느려지는 경우 그로 인한 영향을 줄이려면 **기본 동작 사용**이 아닌 다음 두 옵션 중 하나를 선택하여 동작을 재정의할 수 있습니다.

- **시작 시 창 표시 안 함:** 이전 세션에서 열려 있는 경우에도 Visual Studio를 열 때 지정한 도구 창이 항상 닫힙니다. 적절한 메뉴에서 도구 창을 열 수 있습니다.
- **시작 시 창 자동 숨기기:** 도구 창이 이전 세션에서 열려 있는 경우 이 옵션은 시작 시 도구 창의 그룹이 축소되어 도구 창이 초기화되지 않도록 합니다. 도구 창을 자주 사용하는 경우 도구 창을 여전히 사용할 수 있지만 더 이상 Visual Studio 시작 시간을 지연시키지 않으므로 이 옵션을 선택하는 것이 좋습니다.

![Visual Studio 성능 관리 - 도구 창 보기](../ide/media/vside_perfdialog_toolwindows.png)

언제든지 이 대화 상자로 돌아와서 지정된 모든 도구 창에 대한 설정을 변경할 수 있습니다.

## <a name="speed_up_solution_load"></a>Visual Studio 2017에 큰 솔루션을 더 빠르게 로드

Visual Studio 2017에서는 IDE에서 큰 솔루션을 로드하는 데 필요한 시간과 메모리 크기를 줄이는 경량 솔루션 로드라는 새로운 기능이 도입되었습니다. 많은 C#, VB 또는 C++ 프로젝트를 포함하는 큰 솔루션이 있는 경우 경량 솔루션 로드를 사용하면 성능이 향상될 가능성이 큽니다. 이 기능을 사용하면 어떤 이점이 있는지 자세히 알아보려면 [솔루션 로딩 최적화](../ide/optimize-solution-loading-in-visual-studio)를 참조하세요.

> [!NOTE]
> 이 콘텐츠는 Visual Studio 2017 업데이트 3에 적용됩니다.

### <a name="enable-or-disable-lightweight-solution-load"></a>경량 솔루션 로드를 사용 또는 사용하지 않도록 설정

솔루션 탐색기에서 솔루션 이름을 마우스 오른쪽 단추로 클릭하고 **경량 솔루션 로드 사용**을 선택합니다. 옵션을 선택한 후 경량 솔루션 로드를 활성화하려면 솔루션을 닫았다가 다시 열어야 합니다.

![솔루션 탐색기](../ide/media/VSIDE_LSL_Solution_Setting.png)

경량 솔루션 로드에 대한 전역 설정을 구성하려면 [솔루션 로딩 최적화](../ide/optimize-solution-loading-in-visual-studio.md#global_solution_load_settings)를 참조하세요.

## <a name="see-also"></a>참고 항목
[Visual Studio 성능 팁과 요령](../ide/visual-studio-performance-tips-and-tricks.md)

