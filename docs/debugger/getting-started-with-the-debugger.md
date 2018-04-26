---
title: 디버거 시작
ms.description: Learn how to start the Visual Studio debugger, step through code, and inspect data.
ms.custom: mvc
ms.date: 03/16/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c62137422a4cbd7b85b4f7415e9b3fa85c2c0248
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="tutorial-learn-to-debug-using-visual-studio"></a>자습서: Visual Studio를 사용 하 여 디버깅 하는 방법을 알아봅니다

이 항목의 단계별 연습에서는 Visual Studio 디버거 기능을 소개 합니다. 참조의 디버거 기능을 더 자세히 분석 하려는 경우 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)합니다.

디버거 기능을 확인 하려면 따라 하거나 읽을 수 있거나 기능 둘러보기에 사용 되는 전체 샘플을 다운로드 하 고 단계를 수행 합니다. 이 샘플을 다운로드 하 고 수행 하려면로 이동 [사진 뷰어 데모](https://code.msdn.microsoft.com/windowsdesktop/WPF-Photo-Viewer-Demo-be75662a)합니다.

|         |         |
|---------|---------|
|  ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기")  |    [비디오 보기](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171) 유사한 단계를 보여 주는 디버깅 합니다. |

데모 앱의 C#을 기능은 c + +, Visual Basic, JavaScript 및 명시 된 경우) (제외 Visual Studio에서 지 원하는 다른 언어에 적용할 수 있습니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 디버거를 시작 하 고 중단점에 도달 합니다.
> * 디버거에서 코드를에서 단계별로 실행 하려면 명령에 알아보기
> * 데이터 팁 및 디버거 창에 변수 검사
> * 호출 스택을 검사합니다
> * 예외 도우미 사용

## <a name="start-the-debugger"></a>디버거를 시작!

1. Visual Studio에서 다음이 단계를 따르려면 샘플 다운로드 [이 페이지에](https://code.msdn.microsoft.com/windowsdesktop/WPF-Photo-Viewer-Demo-be75662a)합니다.

    > [!IMPORTANT]
    > .NET 데스크톱 개발 작업의 데모에 사용 하 여 앱을 실행 하려면 Visual Studio를 설치 해야 합니다.

2. 프로젝트를 압축을 풉니다.

3. Visual Studio를 열고 선택는 **파일 > 열기** 메뉴 명령, 한 다음 선택 **프로젝트/솔루션**, 한 다음 프로젝트를 다운로드 폴더를 엽니다.

     ![샘플 프로젝트를 열고](../debugger/media/dbg-tour-open-project.png "프로젝트 열기")

3. WPF 사진 뷰어 데모를 열고 > C# 폴더 photoapp.sln 파일 선택 및 선택 **열려**합니다.

     프로젝트는 Visual Studio에서 열립니다. 솔루션 탐색기의 오른쪽 창에서 모든 프로젝트 파일을 표시 합니다.

    ![솔루션 탐색기 파일](../debugger/media/dbg-tour-solution-explorer.png "솔루션 탐색기")

4. F5 키를 누릅니다 (**디버그 > 디버깅 시작** 또는 **디버깅 시작** 단추 ![디버깅 시작](../debugger/media/dbg-tour-start-debugging.png "디버깅 시작") 디버그 도구 모음에서).

     ![사진 뷰어 앱](../debugger/media/dbg-tour-wpf-app.png "사진 뷰어 앱")

     F5는 디버거가 이제 중단점을 추가 하거나 코드를 검사 하는 특별 한 작업을 수행 하지 않은 우리는 기능 이지만 응용 프로그램 프로세스에 연결 된 응용 프로그램을 시작 합니다. 따라서 응용 프로그램 로드 방금 하 고 사진 이미지를 참조 하십시오.

     이 둘러보기가에서 디버거를 사용 하 여이 앱에 자세히 살펴보겠습니다 알아보고 볼 디버거 기능 하겠습니다.

5. 빨간색 중지 키를 눌러 디버거를 중지 ![디버깅 중지](../debugger/media/dbg-tour-stop-debugging.png "디버깅 중지") 단추입니다.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>중단점을 설정 하 고 디버거를 시작

를 디버깅 하려면 디버거가 응용 프로그램 프로세스에 연결 된 앱을 시작 해야 합니다.

1. 에 `MainWindow` MainWindow.xaml.cs의 생성자는 첫 번째 코드 줄의 왼쪽된 여백을 클릭 하 여 중단점을 설정 합니다.

     ![중단점을 설정](../debugger/media/dbg-tour-set-a-breakpoint.gif "SetABreakPoint")

6. F5 키를 눌러 또는 **디버깅 시작** 단추, 응용 프로그램 시작 및 디버거는 중단점을 설정한 코드의 줄을 실행 합니다.

    노란색 화살표는 또한 (이 문은 실행 되지 않았으면 아직) 같은 지점에서 응용 프로그램 실행을 일시 중단 하는 문을입니다 디버거가 일시 중지를 나타냅니다.

    F 5를 눌러 응용 프로그램을 다음 중단점까지 실행을 계속 합니다. (앱 아직 실행 되지 않는 경우 f 5를 눌러 디버거를 시작 및 첫 번째 중단점에서 중지 합니다.)

    자세히 검사 하려는 코드 섹션 또는 코드 줄을 알고 있는 경우 중단점은 유용한 기능으로 지정 합니다.

## <a name="restart-your-app-quickly"></a>응용 프로그램을 신속 하 게 다시 시작

클릭는 **다시 시작** ![응용 프로그램 다시 시작](../debugger/media/dbg-tour-restart.png "RestartApp") 디버그 도구 모음에서 단추 (Ctrl + Shift + F5).

누를 때 **다시 시작**와 비교 하는 앱을 중지 하 고 디버거를 다시 시작 시간을 절약 합니다. 디버거는 코드를 실행 하 여 적중 하는 첫 번째 중단점에서 일시 중지 합니다.

에 설정한 중단점에서 디버거가 중지 다시는 `MainWindow` 생성자입니다.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>단계 명령을 사용 하 여 디버거에서 코드를 탐색

주로, 여기에서 사용 바로 가기 키를 얻을 수 있는 좋은 방법 이기 때문에 디버거에서 (해당 하는 명령 예: 메뉴 명령을 괄호 안에 표시 됩니다) 응용 프로그램을 실행 하는에 빠른 합니다.

1. F11 키를 누릅니다 (**디버그 > 한 단계씩 코드 실행**) 두 번의 앱을 실행 하는 `InitializeComponent()` 함수입니다.

     ![F11 한 단계씩 코드 실행 코드를 사용 하 여](../debugger/media/dbg-tour-f11.png "F11 한 단계씩 코드 실행")

     F11는는 **한 단계씩 코드 실행** 명령을 클릭 한 번에 응용 프로그램 실행 한 문 앞으로 이동 합니다. F11이 세부 정보에서 실행 흐름을 검사 하는 것이 좋습니다. (코드를 통해 더 빠르게 이동할 보여줍니다 다른 옵션 또한.) 기본적으로 디버거 사용자 코드가 아닌으로 건너뜁니다 (자세한 내용은 참조 [내 코드만](../debugger/just-my-code.md)).

     >[!NOTE]
     > 관리 코드에서 속성 및 연산자 건너뛰기 (기본 동작) 자동으로 단계별로 실행할 때 알림을 받을 것인지를 묻는 대화 상자가 표시 됩니다. 설정을 변경 하려는 경우 나중에 사용 하지 않도록 설정 **속성 및 연산자 건너뛰기** 에서 설정는 **도구 > 옵션** 메뉴 아래 **디버깅**합니다.

2. F10 키를 누릅니다 (**디버그 > 프로시저 단위 실행**)를 여러 번 중지 될 때까지 디버거가 코드의 첫 번째 줄에는 `OnApplicationStartup` 이벤트 처리기입니다.

     ![F10 프로시저 단위 실행 코드를 사용 하 여](../debugger/media/dbg-tour-f10-step-over.png "F10 프로시저 단위 실행")

     F10 함수나 (코드를 실행 여전히) 앱 코드에서 메서드를 한 단계씩 실행 하지 않고 디버거를 이동 합니다. 에 F10 키를 눌러는 `InitializeComponent` 메서드 호출에 대 한 구현 코드를 통해 생략 했습니다 (F11) 하는 대신 `InitializeComponent` (우리는에 관심이 없으므로 지금은 어떤 또는).

## <a name="step-into-a-property"></a>속성을 한 단계씩

1. 디버거에서이 코드 줄에서 일시 중지:

    ````
    mainWindow.Photos.Path = Environment.CurrentDirectory + "\\images";
    ````

    코드 줄을 마우스 오른쪽 단추로 클릭 하 고 선택 **한 단계씩 코드**, 다음 **SDKSamples.ImageSample.PhotoCollection.Path.set**

     ![특정 기능에 대 한 단계를 사용 하 여](../debugger/media/dbg-tour-step-into-specific.png "한 단계씩 코드")

    디버거 관리 되는 속성 및 필드를 건너뜁니다 기본적으로 앞에서 설명한 것 처럼 하지만 **한 단계씩 코드** 명령을이 동작을 재정의할 수 있습니다. 지금은 결과 확인 하려는 경우는 `Path.set` 속성 setter 실행 합니다. **한 단계씩 코드** 를 가져옵니다는 `Path.set` 여기에 코드를 합니다.

     ![단계씩 코드 실행의 결과](../debugger/media/dbg-tour-step-into-specific-2.png "한 단계씩 코드")

     `Update` 흥미 로우 것 처럼이 코드에서 메서드 디버거 해당 코드를 자세히 검사를 사용 하는 그럴 수 있습니다.

5. 위로 마우스를 가져가고는 `Update` 녹색 때까지 메서드 **클릭에 실행** 단추 ![클릭에 실행](../debugger/media/dbg-tour-run-to-click.png "RunToClick") 왼쪽에 나타납니다.

     ![실행에 사용 하 여 기능](../debugger/media/dbg-tour-run-to-click-2.png "클릭에 실행")

    >  [!NOTE] 
    > **클릭에 실행** 단추는의 새로운 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다. 녹색 화살표 단추 보이지 않으면 대신 F11이 예제에서를 디버거를 진행 합니다.

6. 클릭는 **클릭에 실행** 단추 ![클릭에 실행](../debugger/media/dbg-tour-run-to-click.png "RunToClick")합니다.

    이 단추를 사용 하 여 임시 중단점을 설정 하는 것과 비슷합니다. **클릭에 실행** (열려 있는 특정 파일에서 클릭 수)는 응용 프로그램 코드의 표시 영역 내에서 신속 하 게 살펴보기 유용 합니다.

    에 디버거가 전진할는 `Update` 메서드 구현 합니다.

7. 한 단계씩 코드 실행 F11 키를 눌러는 `Update` 메서드.

     ![Update 메서드를 한 단계씩 실행의 결과](../debugger/media/dbg-tour-update-method.png "단계에 Update 메서드")

    을 알 수 코드입니다. 응용 프로그램에는 모든 *.jpg 파일 특정 디렉터리에 있는 한 다음 각 파일에 대 한 사진 개체를 만드는 것입니다. 이 코드 목록 디버거를 사용 하면 응용 프로그램 상태가 (변수) 검사를 시작할 수 있는 좋은 기회에 있습니다. 이 자습서의 다음 섹션에 있는 수행 합니다.

    변수를 검사 하는 사용할 수 있는 기능 디버거의 가장 유용한 기능 중 하나 이며 여러 가지 방법으로 작업을 수행할을 합니다. 종종 문제를 디버깅 하려고 할 때 변수는 특정 한 번에 있어야 하는 값을 저장 하는 여부를 알아보려면 하려고 합니다.

## <a name="examine-the-call-stack"></a>호출 스택을 검사합니다

일시 중지 된 동안는 `Update` 메서드를 클릭 하 여는 **호출 스택** 은 기본적으로 오른쪽 아래 창에서 열려 있는 창을 합니다.

![호출 스택을 검사](../debugger/media/dbg-tour-call-stack.png "ExamineCallStack")

**호출 스택** 창에 있는 메서드 및 함수 호출 되는 순서를 가져오는 표시 합니다. 맨 윗줄로 현재 함수를 보여 줍니다 (의 `Update` 둘러보기 응용 프로그램에서 메서드). 두 번째 줄을 보여 줍니다 `Update` 에서 호출한는 `Path.set` 속성 및 기타 등등.

>  [!NOTE]
> **호출 스택** 창은 Eclipse와 같은 일부 Ide에서 디버그 관점 비슷합니다.

호출 스택은 검토 하 고 응용 프로그램의 실행 흐름을 이해 하는 좋은 방법입니다.

해당 소스 코드를 이동 하는 코드 줄을 두 번 클릭 수 및도 디버거를 통해 검사 중인 현재 범위를 변경 하는 합니다. 이 그러면 디버거를 진행 하지 않습니다.

오른쪽 클릭 메뉴에서 사용할 수도 있습니다는 **호출 스택** 창의 다른 작업을 수행 합니다. 지정 된 함수에 중단점을 삽입, 사용 하 여 디버거를 이동할 수 예를 들어 **커서까지 실행**, 소스 코드를 검사 이동 합니다. 자세한 내용은 참조 [하는 방법: 호출 스택 검사](../debugger/how-to-use-the-call-stack-window.md)합니다.

## <a name="step-out"></a>프로시저 나가기

작업이 완료 되는 경우를 가정해 검사 하는 `Update` Data.cs의 방법으로 함수에서 벗어나기 표시 하지만 디버거에서 유지 하려고 합니다. 사용 하 여 수행할 수 있습니다는 **나가기** 명령입니다.

1. Shift + F11 키를 누릅니다 (또는 **디버그 > 프로시저 나가기**).

     응용 프로그램 실행을 다시 시작 (및 디버거를 앞으로 이동)이이 명령은 현재 함수에서 반환 될 때까지 합니다.

     다시 해야 할는 `Update` Data.cs에서 메서드를 호출 합니다.

2. Shift + F11 다시 및 디버거 키를 눌러이 되는 호출 스택을 다시는 `OnApplicationStartup` 이벤트 처리기입니다.

## <a name="run-to-cursor"></a>커서까지 실행

1. 선택 된 **디버깅 중지** 빨간색 단추 ![디버깅 중지](../debugger/media/dbg-tour-stop-debugging.png "디버깅 중지") 또는 Shift + f 5를 눌러 합니다.

2. 에 `Update` 메서드 Data.cs에서 마우스 오른쪽 단추로 클릭는 `Add` 메서드를 호출 하 고 선택 **커서까지 실행**합니다. 이 명령은 디버깅을 시작 하 고 코드의 현재 줄에 임시 중단점을 설정 합니다.

     ![실행 커서 기능을 사용 하 여](../debugger/media/dbg-tour-run-to-cursor.png "커서까지 실행")

    중단점에서 일시 중지 해야 `MainWindow` (이므로 첫 번째 중단점 설정).

3. F5 키를 눌러으로 이동 하는 `Add` 하면 선택한 메서드가 **커서까지 실행**합니다.

    이 명령은 코드를 편집 하 고 신속 하 게 임시 중단점을 설정 하 고 디버거를 시작 하려고 할 때 유용 합니다.

## <a name="change-the-execution-flow"></a>실행 흐름 변경

1. 일시 중지 디버거는 `Add` 메서드 호출에서 왼쪽에 노란색 화살표는 (실행 포인터)을 가져올 마우스를 사용 하 고 노란색 화살표를 한 줄 위로 이동 하는 `foreach` 루프입니다.

     ![실행 포인터 이동](../debugger/media/dbg-tour-move-the-execution-pointer.gif "실행 포인터를 이동 합니다.")

    실행 흐름을 변경 하 여 서로 다른 코드 실행 경로 테스트 하거나 디버거를 다시 시작 하지 않고 코드를 다시 실행 하는 등의 작업을 수행할 수 있습니다.

2. 이제 F5 키를 누릅니다.

    응용 프로그램 창에 추가 하는 이미지를 볼 수 있습니다. 코드를 다시 실행 하는 때문에 `foreach` 일부 이미지 루프를 두 번 추가 되었습니다!
    
    > [!WARNING]
    > 종종이 기능에 주의 해야 하 고 도구 설명에 경고를 표시 합니다. 너무 다른 경고를 볼 수 있습니다. 포인터를 이동 하면 이전 응용 프로그램 상태로 응용 프로그램 되돌릴 수 없습니다.

## <a name="inspect-variables-with-data-tips"></a>데이터 팁을 사용 하 여 변수를 검사 합니다.

1. 사진 뷰어 데모 응용 프로그램에서 Data.cs를 열려면 마우스 오른쪽 단추로 클릭는 `private void Update` 함수 선언 하 고 선택 **커서까지 실행** (응용 프로그램을 먼저 중지 이미 실행 중인 경우).

    디버거가 연결 된 응용 프로그램을 멈춥니다. 이 통해 상태를 검사할 수 있습니다.

2. 위로 마우스를 가져가고는 `Add` 메서드를 호출 하 고 클릭는 **클릭에 실행** 단추 ![클릭에 실행](../debugger/media/dbg-tour-run-to-click.png "RunToClick")합니다.

3. 이제 파일 개체 위로 마우스를 가져가고 (`f`)의 기본 속성 값, 파일 이름 참조 및 `market 031.jpg`합니다.

     ![데이터 팁 보기](../debugger/media/dbg-tour-data-tips.gif "데이터 팁을 보려면")

4. 개체와 같은 속성은 모두 표시를 확장 하 고 `FullPath` 속성입니다.

    종종를 디버깅할 때 신속 하 게 개체에 속성 값을 확인 하 고 데이터 팁 설정을 수행 하는 좋은 방법입니다.

    > [!TIP]
    > 가장 지원 되는 언어로 변경할 부분이 있으면 디버거 세션 중에 코드를 편집할 수 있습니다. 자세한 내용은 참조 하십시오. [편집 하며 계속 하기](../debugger/edit-and-continue.md)합니다. 그러나이 응용 프로그램에서 해당 기능을 사용 하려면 우리 먼저를 업데이트 해야.NET Framework의 응용 프로그램의 버전입니다.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>자동 및 지역 창을 사용 하 여 변수를 검사 합니다.

1. 확인 된 **자동** 코드 편집기의 아래쪽 창에 있습니다.

     ![자동 창에서 변수를 검사](../debugger/media/dbg-tour-autos-window.png "자동 창")

    에 **자동** 창, 변수 및 해당 현재 값을 참조 합니다. **자동** 창에 현재 줄 이나 이전 줄에 사용 되는 모든 변수 표시 (c + +, 창에서는 변수 코드의 이전 세 줄. 언어별 동작에 대 한 설명서를 참조).

    > [!NOTE]
    > JavaScript에서는 **지역** 창이 있지 않고 지원 되는 **자동** 창.

2. 다음으로 확인 된 **지역** 창.

    **지역** 창에서는 현재 범위에 있는 변수를 보여 줍니다.

    ![지역 창에서 변수를 검사](../debugger/media/dbg-tour-locals-window.png "지역 창")

    현재는 `this` 개체 및 파일 개체 (`f`) 현재 범위에 있습니다. 자세한 내용은 참조 하십시오. [자동 및 지역 창에서 변수를 검사](../debugger/autos-and-locals-windows.md)합니다.

## <a name="set-a-watch"></a>조사식 설정

1. 파일 개체를 마우스 오른쪽 단추로 클릭 주 코드 편집기 창에서 (`f`) 선택 하 고 **조사식 추가**합니다.

    사용할 수는 **조사식** 창에 변수 (또는 식) 관심을 기울 원하는 지정 합니다.

    이제는 조사식에 설정 준비는 `File` 개체를 확인할 수 있습니다는 디버거를 통해 이동 변경의 값입니다. 다른 변수 창과 달리는 **조사식** 창 항상 표시 변수 조사 중인 있습니다 하는 회색 때 범위를 벗어났습니다.

2. 에 `Add` 메서드를 녹색 클릭 ![클릭에 실행](../debugger/media/dbg-tour-run-to-click.png "RunToClick") 단추를 다시 (또는 몇 번 F11 키를 눌러)를 진행 하려면는 `foreach` 루프입니다.

    ![조사식 변수에 설정](../debugger/media/dbg-tour-watch-window.png "조사식 창")

    실행 하는의 주 창에 추가 하는 첫 번째 그림을 볼 수도 있습니다 이미지 될 수 있습니다 표시 되지 않도록 아직 샘플 응용 프로그램을 하지만이 서로 다른 응용 프로그램 스레드에서 발생 합니다.

    자세한 내용은 참조 하세요. [조사식 및 간략 한 조사식 창 사용 하 여 감시를 설정 합니다.](../debugger/watch-and-quickwatch-windows.md)

## <a name="examine-an-exception"></a>예외를 검사 합니다.

1. 실행 중인 응용 프로그램 창에서 텍스트를 삭제는 **경로** 입력 상자는 **변경** 단추입니다.

     ![예외가 throw 될](../debugger/media/dbg-tour-cause-an-exception.png "에서 예외가 발생")

     응용 프로그램 예외를 throw 하 고 디버거에서 예외를 발생 시킨 코드 줄으로 이동 합니다.
     
     ![예외 도우미](../debugger/media/dbg-tour-exception-helper.png "예외 도우미")

     여기에서 **예외 도우미** 표시는 `System.ArgumentException` 경로가 올바른 형식이 않은 없다는 오류 메시지가 있습니다. 따라서 메서드 또는 함수 인수에 오류가 발생 한 알고 있습니다.

     이 예제는 `DirectoryInfo` 에 저장 된 빈 문자열에는 오류를 지정 하는 호출의 `value` 변수입니다. (위로 마우스를 가져가고 `value` 빈 문자열을 볼 수 있습니다.)

     예외 도우미는 오류를 디버그 하는 데 도움이 되는 유용한 기능입니다. 오류 세부 정보 보기와 같은 작업을 수행 하 고 예외 도우미에서 한 조사식을 추가할 수도 있습니다. 또는 필요에 따라 특정 예외를 throw 하는 조건을 변경할 수 있습니다.

    >  [!NOTE] 
    > 예외 도우미 대체 예외 도우미 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다.

2. 확장 된 **예외 설정** 수 있지만이 예외 형식을 처리 하는 방법에 대 한 다른 옵션을 보려면 노드를이 둘러보기는에 아무 것도 변경할 필요가 없습니다!

3. F5 키를 눌러 응용 프로그램을 계속 합니다.

디버거 기능에 대 한 자세한 참조 [디버거 팁과 요령](../debugger/debugger-tips-and-tricks.md)합니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 코드를 단계별로 실행 하 고 디버거를 시작 하 고 변수를 검사 하는 방법을 배웠습니다. 높은 수준의 디버거 기능 추가 정보에 대 한 링크를 확인 하려는 경우.

> [!div class="nextstepaction"]
> [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)
