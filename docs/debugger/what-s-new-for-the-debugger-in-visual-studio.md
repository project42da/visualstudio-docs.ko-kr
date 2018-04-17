---
title: Visual Studio 2017 디버거의 새로운 기능 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, what's new
- what's new [debugger]
- debugging [Visual Studio], what's new
- what's new [Visual Studio], debugging
ms.assetid: 2aed9caa-2384-4e49-8595-82d8b06cf271
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d0bcd44da88279f042469356a97bce7f369e1190
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="whats-new-for-the-debugger-in-includevsdev15miscincludesvsdev15mdmd"></a>디버거의 새로운 기능 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

디버거는 이러한 새 기능에 포함 됩니다.

- 15.5의 새로운는 **스냅숏 디버거** 에 관심이 있는 코드가 실행 되 면 프로덕션에서 응용 프로그램의 스냅숏을 수행 합니다. 디버거가 스냅숏을 생성하도록 명령하려면 코드에서 snappoint와 logpoint를 설정합니다. 디버거를 통해 프로덕션 응용 프로그램의 트래픽에 영향을 미치지 않으면서 정확히 무엇이 잘못되었는지를 볼 수 있습니다. 스냅샷 디버거를 사용하면 프로덕션 환경에서 발생하는 문제를 해결하는 데 걸리는 시간을 상당히 줄일 수 있습니다.

    스냅숏 컬렉션은 Azure App Service에서 실행되는 다음 웹앱에서 사용할 수 있습니다.

    * .NET Framework 4.6.1 이상에서 실행되는 ASP.NET 응용 프로그램
    * Windows의 .NET Core 2.0 이상에서 실행되는 ASP.NET Core 응용 프로그램

    자세한 내용은 참조 [스냅숏 디버거를 사용 하 여 라이브 ASP.NET 응용 프로그램을 디버깅](../debugger/debug-live-azure-applications.md)합니다.

- Visual Studio Enterprise에서 15.5만의 새로운 **IntelliTrace 단계 다시** 자동으로 단계 이벤트는 모든 중단점 및 디버거에서의 응용 프로그램의 스냅숏을 만듭니다. 기록된 스냅숏을 통해 이전 중단점 또는 단계로 돌아가서 응용 프로그램의 과거 상태를 볼 수 있습니다. IntelliTrace 뒤로 이동을 사용하면 이전 응용 프로그램 상태를 보고 싶지만 디버깅을 다시 시작하거나 원하는 앱 상태를 다시 만들지 않으려는 경우에 시간을 절약할 수 있습니다.

    디버그 도구 모음의 **뒤로 가기**와 **앞으로 가기** 단추를 사용하여 이동하고 스냅숏을 볼 수 있습니다. 이 단추를 사용하여 **진단 도구** 창의 **이벤트** 탭에 나타나는 이벤트를 탐색할 수 있습니다.

    ![뒤로 및 앞으로 단추 단계](../debugger/media/intellitrace-step-back-icons-description.png  "단계 뒤로 및 앞으로 단추")

    자세한 내용은 [IntelliTrace 뒤로 이동을 사용하여 스냅숏 보기](../debugger/how-to-use-intellitrace-step-back.md) 페이지를 참조하세요.

- **예외 도우미** 예외 도우미를 대체 하 고 오류가 발생 하는 비 모달 대화 상자에 나타납니다. **예외 도우미** 모든 내부 예외, 디버거에서 (있는 경우), 추가 분석에 대 한 빠른 액세스를 제공 하는에 즉시 액세스할 수는 **예외 설정** 예외에 대 한 합니다. 차단 하 고 않은지 확인 해야 할 경우 예외 도우미 부동 뷰로 끌어 수도 있습니다.

    예를 들어 한 **NullReferenceException** 이제 변수를 null 참조 (추가 정보)를 표시 합니다.

    ![디버거 예외 도우미](../debugger/media/dbg-exception-helper.png "DbgExceptionHelper")

    자세한 내용은 [Using the New Exception Helper in Visual Studio](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/31/using-the-new-exception-helper-in-visual-studio-15-preview/)(Visual Studio에서 새 예외 도우미 사용) 블로그 게시물을 참조하세요.

- 선택 하 여 디버거에서 일시 중지 된 동안 코드의 줄으로 실행할 수 있습니다는 **여기로 실행** (아이콘이 표시 코드 줄을 가리키면) 녹색 화살표 아이콘입니다. 이렇게 하면 임시 중단점을 설정할 필요가 없습니다.

    ![디버거는 클릭에 실행의](../debugger/media/dbg-run-to-click.png "DbgRunToClick") 

- 예외 조건을 설정할 수 있습니다는 **예외 설정** 대화 상자 (사용 하 여이 작업을 수행할 수는 **조건 편집** 예외 설정 대화 상자에서 또는 오른쪽 클릭 메뉴에서 사용 하 여 아이콘은 예외입니다.) 현재 지원 되는 조건, 모듈 이름 포함 하거나 제외할 예외에 대 한 포함 됩니다.

    ![예외에 대 한 조건](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")

- 대화 상자에 사용자를 연결 해야 하는 프로세스를 신속 하 게 식별 하는 데 도움이 되는 새 검색 기능에 연결 합니다.

    ![프로세스에 연결 된 검색의](../debugger/media/dbg-attach-to-process-search.png "DbgAttachToProcessSearch") 

이러한 새 기능에 대 한 자세한 내용은 참조는 [릴리스 정보에 대 한 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] ](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#debuggingdiag)합니다.
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio의 디버깅](../debugger/index.md)  
 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)