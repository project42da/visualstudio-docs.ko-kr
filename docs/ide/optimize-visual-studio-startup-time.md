---
title: "Visual Studio 시작 시간 최적화 | Microsoft 문서"
ms.custom: 
ms.date: 7/20/2017
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
author: kempb
ms.author: kempb
manager: ghogen
f1_keywords:
- vs.performancecenter
ms.translationtype: HT
ms.sourcegitcommit: c3521e1de25854db012cb91bbe09d9463ecb42c7
ms.openlocfilehash: af1ff0dbeeb30e6b3169c6a94dab8da50085bf20
ms.contentlocale: ko-kr
ms.lasthandoff: 07/21/2017

---

# <a name="optimize-visual-studio-startup-time"></a>Visual Studio 시작 시간 최적화
이상적으로 Visual Studio는 항상 최대한 빨리 시작되어야 합니다. 그러나 시작 시 Visual Studio 확장 및 열린 도구 창이 자동으로 로드되기 때문에 시작 시간이 느려질 수 있습니다. **Visual Studio 성능 관리 창**에서 Visual Studio 시작 시간에 영향을 미치는 확장과 기능을 확인하고 이러한 확장과 기능의 로드 동작을 제어할 수 있습니다.

## <a name="control-startup-behavior"></a>시작 동작 제어

Visual Studio 2017에서는 시작 시간이 늘어나지 않도록 요청 시 로드 방법을 사용하여 시작 시 확장이 로드되지 않도록 합니다. 즉, Visual Studio가 시작된 후 즉시 확장이 열리지 않고 시작 후 필요에 따라 열리도록 하는 동작입니다. 또한 이전 Visual Studio 세션에서 열려 있는 도구 창으로 인해 시작 시간이 느려질 수 있으므로 Visual Studio는 시작 시간에 영향을 주지 않도록 보다 지능적인 방식으로 도구 창을 엽니다.

Visual Studio에서 시작 속도가 느린 것을 감지하면 속도 저하를 초래하는 확장이나 도구 창을 알려주는 팝업 메시지가 나타납니다. 이 메시지에는 **Visual Studio 성능 관리** 대화 상자에 대한 링크도 제공됩니다. 이 대화 상자는 **도움말 > Visual Studio 성능 관리** 메뉴 명령을 사용해서 열 수도 있습니다.

![Visual Studio 성능 관리에 '... 확장으로 인해 Visual Studio가 느려집니다'라는 팝업이 나타납니다.](~/docs/ide/media/vside_perfdialog_popup.PNG)

이 대화 상자에는 시작 성능에 영향을 미치는 확장 및 도구 창이 나열됩니다. 이 대화 상자에서 확장 및 도구 창 설정을 변경하여 시작 성능을 향상할 수 있습니다.

### <a name="change-extension-settings"></a>확장 설정 변경

확장으로 인해 Visual Studio 시작 속도가 느려지는 경우 확장 형식 중 하나를 선택하면 **Visual Studio 성능 관리** 대화 상자에 해당 확장이 나타납니다. 이 대화 상자에는 시작 시, 솔루션 로딩 시 및 편집기에서 입력 시 성능에 영향을 미치는 확장이 표시됩니다.

![Visual Studio 성능 관리 - 확장 보기](~/docs/ide/media/vside_perfdialog_extensions.PNG)

시작, 솔루션 로드 또는 입력 시간에 대한 영향이 지나치게 높은 경우, **사용 안 함** 단추를 선택하여 해당 시나리오에 대한 확장을 사용하지 않도록 설정합니다. 확장 관리자 또는 Visual Studio 성능 관리 대화 상자를 통해 이후 세션에 확장을 언제든 다시 사용할 수 있습니다.

### <a name="change-tool-window-settings"></a>도구 창 설정 변경

도구 창으로 인해 Visual Studio 시작 속도가 느려지는 경우 그로 인한 영향을 줄이려면 **기본 동작 사용**이 아닌 다음 두 옵션 중 하나를 선택하여 동작을 재정의할 수 있습니다.

- **시작 시 창 표시 안 함:** 이전 세션에서 열려 있는 경우에도 Visual Studio를 열 때 지정한 도구 창이 항상 닫힙니다. 적절한 메뉴에서 도구 창을 열 수 있습니다.
- **시작 시 창 자동 숨기기:** 도구 창이 이전 세션에서 열려 있는 경우 이 옵션은 시작 시 도구 창의 그룹이 축소되어 도구 창이 초기화되지 않도록 합니다. 도구 창을 자주 사용하는 경우 도구 창을 여전히 사용할 수 있지만 더 이상 Visual Studio 시작 시간을 지연시키지 않으므로 이 옵션을 선택하는 것이 좋습니다.

![Visual Studio 성능 관리 - 도구 창 보기](~/docs/ide/media/vside_perfdialog_toolwindows.PNG)

언제든지 이 대화 상자로 돌아와서 지정된 모든 도구 창에 대한 설정을 변경할 수 있습니다.

## <a name="speed-up-solution-load"></a>솔루션 로드 속도 향상

Visual Studio 2017에서는 IDE에서 큰 솔루션을 로드하는 데 필요한 시간과 메모리 크기를 줄이는 **경량 솔루션 로드**를 지원합니다. 많은 C#, VB 및/또는 C++ 프로젝트를 포함하는 큰 솔루션이 있는 경우 경량 솔루션 로드를 사용하면 성능이 향상될 가능성이 큽니다.

경량 솔루션 로드를 사용하는 경우 일부 IDE 기능을 완전히 사용할 수 없기 때문에 이 기능은 기본적으로 꺼져 있습니다. 다음 섹션은 이 기능을 사용할지 여부를 결정하는 데 도움이 됩니다.

### <a name="enable-lightweight-solution-load"></a>경량 솔루션 로드 사용

전체 IDE 또는 개별 솔루션에 대해 경량 솔루션 로드를 사용할 수 있습니다.

모든 프로젝트 및 솔루션에 대한 경량 솔루션 로드 설정을 변경하려면 **도구 > 옵션 > 프로젝트 및 솔루션**으로 이동하여 다음 세 가지 로드 옵션 중 하나를 선택합니다.

![옵션 대화 상자, 도구](~/docs/ide/media/VSIDE_LightweightSolutionLoad.png)

- **Visual Studio에서 내 솔루션에 적합한 설정을 선택할 수 있도록 허용**: 솔루션이 열릴 때 Visual Studio에서 각 솔루션을 분석하여 경량 솔루션 로드를 적용할지 여부를 결정합니다. 
- **사용:** IDE 차원의 설정과 관계없이 이 솔루션에 경량 솔루션 로드를 사용하도록 설정합니다.
- **사용 안 함:** IDE 차원의 설정과 관계없이 이 솔루션에 경량 솔루션 로드를 사용하지 않도록 설정합니다.

개별 솔루션에 대해 경량 솔루션 로드를 사용하려면 솔루션 탐색기에서 최상위 솔루션 노드를 선택합니다. **속성** 창에서 **경량 로드** 속성에 대해 **기본**, **사용** 또는 **사용 안 함**을 선택합니다.

![솔루션 탐색기](~/docs/ide/media/VSIDE_LSL Solution Setting.png)

솔루션 탐색기에서 최상위 솔루션 노드를 마우스 오른쪽 단추로 클릭하고 **경량 솔루션 로드 사용**(현재 기능을 사용하지 않는 경우) 또는 **경량 솔루션 로드 사용 안 함**(현재 기능을 사용하는 경우)을 선택할 수도 있습니다.

경량 솔루션 로드 설정을 변경하는 경우 다음에 솔루션을 로드할 때 변경 내용이 적용됩니다. IDE를 다시 시작할 필요가 없습니다.

### <a name="automatically-enable-lightweight-solution-load"></a>자동으로 경량 솔루션 로드 사용

Visual Studio 2017에서 큰 솔루션을 여는 경우 경량 솔루션 로드를 사용하라는 팝업 메시지가 표시될 수 있습니다. 많은 C#, VB 또는 C++ 프로젝트가 포함된 솔루션의 경우에만 메시지가 나타납니다. **사용**을 선택하면 해당 솔루션에 대해서만 경량 솔루션 로드가 활성화됩니다. IDE 차원의 설정은 변경되지 않습니다.

![팝업 창](~/docs/ide/media/VSIDE_LSL Popup.png)

나중에 솔루션의 **속성** 창에서 경량 솔루션 로드를 사용하지 않도록 설정할 수 있습니다.

### <a name="limitations"></a>제한 사항

경량 솔루션 로드를 사용하는 경우에도 IDE의 기능을 대부분 사용할 수 있습니다. 그러나 일부 IDE 기능과 타사 확장이 완벽하게 호환되지 않을 수도 있습니다.  경량 솔루션 로드를 사용하는 경우 작동하지 않는 것으로 알려진 기능은 다음과 같습니다.

- 경량 솔루션 로드를 사용하는 경우 일부 타사 확장이 올바르게 동작하지 않을 수도 있습니다.
- 디버깅을 시작할 때 로드되지 않은 프로젝트에서는 편집하며 계속하기 기능이 작동하지 않습니다. 이러한 프로젝트에 포함된 파일은 읽기 전용이며, 편집을 시도하는 경우 프로젝트가 로드되지 않았다는 오류가 보고됩니다.
- 경량 솔루션 로드를 사용하도록 설정되었을 때 F# 프로젝트가 제대로 빌드되지 않고 GoTo에서 기호를 일부 사용하지 못할 수 있습니다.

