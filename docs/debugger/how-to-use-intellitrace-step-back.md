---
title: "IntelliTrace 단계 백-Visual Studio를 사용 하 여 스냅숏 보기 | Microsoft Docs"
ms.description: Learn how to take snapshots, and view snapshots with IntelliTrace step-back
ms.custom: mvc
ms.date: 12/06/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: tutorial
ms.assetid: 7c60d929-d993-49dc-9db3-43b30be9912b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 9602aa5c75f9572f2ca0f5cd8ef3426cde8ed96a
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="view-snapshots-using-intellitrace-step-back-in-visual-studio"></a>Visual Studio에서 IntelliTrace를 사용 하 여 스냅숏 볼 단계 저장

IntelliTrace 단계 다시 자동으로 스냅숏을에서 모든 중단점 및 디버거 응용 프로그램의 단계 이벤트입니다. 기록된 스냅숏을 통해 이전 중단점 또는 단계로 돌아가서 응용 프로그램의 과거 상태를 볼 수 있습니다. IntelliTrace 뒤로 이동을 사용하면 이전 응용 프로그램 상태를 보고 싶지만 디버깅을 다시 시작하거나 원하는 앱 상태를 다시 만들지 않으려는 경우에 시간을 절약할 수 있습니다.

IntelliTrace 단계 저장은 Visual Studio Enterprise 2017 15.5 이상 버전에서에서 시작 가능 하 고 Windows 10 Anniversary 업데이트 필요 이상. 기능은 현재 ASP.NET, WinForms, WPF, 관리 되는 콘솔 응용 프로그램 및 관리 되는 클래스 라이브러리를 디버깅을 위해 지원 됩니다. Visual Studio 2017 Enterprise 버전 15.7 미리 보기 1 부터는 기능 또한 대해서는.NET Core 및 ASP.NET Core 합니다. UWP 응용 프로그램 디버깅 현재 지원 되지 않습니다.

이 자습서에서는 다음을 수행합니다.

> [!div class="checklist"]
> * Intellitrace 이벤트와 스냅숏 사용
> * 단계 뒤로 및 앞 단계 명령을 사용 하 여 이벤트를 이동 합니다.
> * 스냅샷 이벤트 보기
  
## <a name="enable-intellitrace-events-and-snapshots-mode"></a>IntelliTrace 이벤트 및 스냅숏 모드를 사용 하도록 설정 

1. Visual Studio Enterprise에서 프로젝트를 엽니다.

1. 로 이동 **도구 > 옵션 > IntelliTrace** 설정 및 옵션을 선택 **IntelliTrace 이벤트 및 스냅숏**합니다. 

    ![IntelliTrace 이벤트 및 스냅숏 모드를 사용 하도록 설정](../debugger/media/intellitrace-enable-snapshots.png "IntelliTrace 이벤트를 사용 하도록 설정 및 스냅숏 모드")

1. 프로젝트에 하나 이상의 중단점을 설정 하 고 디버깅 시작 (키를 눌러 **F5**), 코드를 단계별로 실행 하 여 디버깅을 시작 하거나 (**F10** 또는 **F11**).

    IntelliTrace 스냅숏을 응용 프로그램의 프로세스의 각 디버거에서 단계와 중단점 이벤트입니다. 이러한 이벤트에 기록 됩니다는 **이벤트** 탭에 **진단 도구** 다른 IntelliTrace 이벤트와 함께 창. 이 창을 열려면 선택 **디버그** > **Windows** > **진단 도구 표시**합니다.

    카메라 아이콘 사용할 수 있는 스냅숏이를 이벤트 옆에 나타납니다. 

    ![이벤트 탭 스냅숏과 함께](../debugger/media/intellitrace-events-tab-with-snapshots.png "중단점 및 단계에 대 한 스냅숏이 포함 된 이벤트 탭")

    성능상의 이유로 스냅숏 매우 신속 하 게 단계별로 실행할 때 수행 되지 않습니다. 카메라 아이콘이 표시 되지 않으면 단계 옆에 느리게 단계별 실행 해 보십시오.

## <a name="navigate-and-view-snapshots"></a>이동 하 고 스냅숏 보기

1. 사용 하 여 이벤트 간의 탐색는 **이전 (Alt + [)** 및 **단계 (Alt +])** 디버그 도구 모음 단추입니다.

    에 나타나는 이벤트를 탐색 하는이 단추는 **이벤트** 탭에 **진단 도구 창을**합니다. 단계별 실행 뒤로 또는 앞으로 이벤트에 자동으로 활성화 [기록 디버깅](../debugger/historical-debugging.md) 선택한 이벤트를 처리 합니다.

    ![뒤로 및 앞으로 단추](../debugger/media/intellitrace-step-back-icons-description.png "단계 뒤로 및 앞으로 단계 단추")

    한 걸음 물러나 또는으로 이동 하는 경우 Visual Studio 기록 디버깅 모드를 입력 합니다. 이 모드에서는 선택한 이벤트가 기록 된 경우 시간은 디버거의 컨텍스트 전환 됩니다. 또한 visual Studio는 소스 창에서 코드의 해당 줄에 포인터를 이동합니다. 

    이 보기에서의 값을 검사할 수 있습니다는 **호출 스택**, **지역**, **자동**, 및 **조사식** windows 합니다. DataTips를 확인 하 고에 식 평가 수행 하는 변수를 가리키면 수도 있습니다는 **직접 실행** 창. 보고 있는 데이터는 시간에서 해당 시점에 수행 되는 응용 프로그램의 프로세스의 스냅숏에서 됩니다.

    따라서, 예를 들어 중단점에 도달 하 고 단계를 수행 하는 경우 (**F10**), **이전 단계** 단추 중단점에 해당 코드의 줄에서 기록 모드에서 Visual Studio를 넣습니다. 

    ![활성 중 기록 모드 스냅숏 사용 하 여 이벤트에서](../debugger/media/intellitrace-historical-mode-with-snapshot.png "활성 중 기록 모드 스냅숏 사용 하 여 이벤트에서")

2. 라이브 실행 돌아가려면 선택 **계속 (F5)** 하거나 클릭 하 고 **라이브 디버깅으로 돌아가세요** 정보 표시줄에 링크 합니다. 

3. 스냅숏을 볼 수 있습니다는 **이벤트** 탭 합니다. 이 작업을 수행 하려면 스냅숏 사용 하 여 이벤트를 선택 하 고 클릭 **기록 디버깅 활성화**합니다.

    기록 디버깅 활성화 하려면 카메라 아이콘을 클릭할 수도 있습니다.

    ![이벤트에 기록 디버깅 활성화](../debugger/media/intellitrace-activate-historical-debugging.png "이벤트에 기록 디버깅 활성화")

    와 달리는 **다음 문 설정** 스냅숏 보기 명령 코드를 다시 실행 하지 않으면 제공 응용 프로그램의 상태에 대 한 정적 뷰 시점 이전에 발생 한 시간에서입니다.

    ![IntelliTrace 단계 다시 간략하게](../debugger/media/intellitrace-step-back-overview.png "개요의 IntelliTrace 단계 저장")

    Visual Studio에서 변수를 검사 하는 방법에 대 한 자세한 참조 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)  

## <a name="frequently-asked-questions"></a>질문과 대답

#### <a name="how-is-intellitrace-step-back-different-from-intellitrace-events-only-mode"></a>IntelliTrace 단계 다시 IntelliTrace 이벤트에 대 한 유일한 모드와 어떻게 다릅니까?

전용 모드 이벤트에서에서 IntelliTrace에서는 디버거에서 한 단계씩 실행 하 고 중단점에 기록 디버깅 활성화 수 있습니다. IntelliTrace 데이터에만 capture 되는 반면는 **지역** 및 **자동** windows, 열려 있으며만 확장 되는 데이터를 캡처할 경우 windows 및 표시 합니다. 이벤트 전용 모드에서 종종 않아도 변수 및 복잡 한 개체의 전체 보기입니다. 또한 식 평가 및 보기의 데이터는 **조사식** 창이 지원 되지 않습니다. 

IntelliTrace는 이벤트 및 스냅숏 모드에서 복잡 한 개체를 포함 하는 응용 프로그램의 프로세스의 전체 스냅숏이 캡처합니다. 코드 줄에서 중단점에서 중지 된 (및 이전에 정보를 확장 하는 여부가 중요 하지 않은) 하는 경우에 따라 동일한 정보를 볼 수 있습니다. 식 계산 스냅숏을 볼 때에 지원 됩니다.  

#### <a name="what-is-the-performance-impact-of-this-feature"></a>이 기능은 성능에 영향을 무엇입니까? 

전체 단계별 실행 성능에 미치는 영향을 응용 프로그램에 따라 달라 집니다. 오버 헤드의 스냅숏을 만드는 것은 약 30 밀리초입니다. 스냅숏이 만들어질 때 응용 프로그램의 프로세스 분기 하 고 분기 복사본 일시 중지 됩니다. 스냅숏으로 보면 Visual Studio이 프로세스의 분기 복사본에 연결 합니다. 각 스냅숏에 대 한 Visual Studio만 페이지 테이블을 복사 하 고 쓰기 시 복사 페이지 설정 합니다. 힙의 개체에 연결 된 스냅숏을 사용 하 여 디버거 단계 사이 변경, 해당 페이지 테이블이 다음 복사 됩니다 최소 메모리 비용이 듭니다. Visual Studio는 하다 메모리가 부족 하 여 스냅숏을 검색 하는 경우 고려 되지 하나입니다.
 
## <a name="known-issues"></a>알려진 문제  
* Windows 10 년 작성자 업데이트 (RS3) 보다 오래 된 Windows 버전에서 IntelliTrace 이벤트 및 스냅숏 모드를 사용 하는 경우 및 응용 프로그램의 디버그 플랫폼 대상을 x86로 설정 된 경우 IntelliTrace 스냅숏을 고려 하지 않습니다.

    해결 방법:
    * 설치 또는 Windows 10 년 작성자 업데이트 (RS3)로 업그레이드 합니다. 
    * 또는: 
        1. Visual Studio 설치 관리자에서 데스크톱(x86, x64) 구성 요소용 VC++ 2015.3 v140 도구 집합을 설치합니다.
        2. 대상 응용 프로그램을 빌드합니다.
        3. 명령줄에서 editbin 도구 설정를 사용 하는 `Largeaddressaware` 대상 실행 파일에 대 한 플래그입니다. 예를 들어 (경로 업데이트) 한 후이 명령을 사용할 수 있습니다: "C:\Program Files (x86) \Microsoft Visual Studio\Preview\Enterprise\VC\Tools\MSVC\14.12.25718\bin\Hostx86\x86\editbin.exe" /Largeaddressaware "C:\Path\To\Application\app.exe"입니다.
        4. 디버깅을 시작하려면 **F5** 키를 누릅니다. 이제 스냅숏은 디버거 단계와 중단점에 수행 됩니다.

        > [!Note]
        > `Largeaddressaware` 플래그는 실행 파일 변경 내용으로 다시 빌드될 때마다 설정 되어야 합니다.

* 지속형된 메모리 매핑된 파일을 사용 하는 응용 프로그램에서 응용 프로그램의 프로세스의 스냅숏을 생성 하는 경우 (후에 잠금을 부모 프로세스를 출시 했습니다) 스냅숏 사용 하 여 프로세스 메모리 매핑된 파일에 대 한 단독 잠금의 보유 합니다. 다른 프로세스를 읽을 수 있지만 쓸, 메모리 매핑된 파일에 여전히 수 있습니다.

    해결 방법:
    * 디버깅 세션을 종료 하 여 모든 스냅숏의 선택을 취소 합니다. 

* 해당 프로세스에 많은 수의 Dll 로드 하는 응용 프로그램과 같이 고유 메모리 영역의 너무 많은 응용 프로그램을 디버깅할 때 사용 하도록 설정 하는 스냅숏과 함께 성능 단계별 실행 영향을 받습니다. 이 문제는 이후 버전의 Windows에서 해결 될 예정입니다. 이 문제를 발생 하는 경우에 도달 하 여 문의해 주십시오 stepback@microsoft.com합니다. 

* 파일을 저장할 때 **디버그 > IntelliTrace > 저장 IntelliTrace 세션** 이벤트 및 스냅숏 모드에서 스냅숏에서 캡처한 추가 데이터에서에서 사용할 수 없는.itrace 파일입니다. 중단점 및 단계 이벤트에서 IntelliTrace 이벤트에 대 한 전용 모드에서 파일에 저장 하는 경우 동일한 정보를 참조 합니다. 

## <a name="next-steps"></a>다음 단계

이 자습서의 단계 다시 IntelliTrace를 사용 하는 방법을 배웠습니다. 다른 IntelliTrace 기능에 대 한 자세한 내용을 보려면이 좋습니다.

> [!div class="nextstepaction"]
> [IntelliTrace 기능](../debugger/intellitrace-features.md)
