---
title: Visual Studio 디버거를 사용 하는 c + +를 사용 하 여 디버그 | Microsoft Docs
ms.custom: mvc
ms.date: 03/18/2018
ms.technology:
- vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: 639e430b-6d2d-46bd-b738-8c60dfb384f1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 1d73549fb556a52acb0e086ab8bcbfe9fb88c7b0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debug-with-c-using-the-visual-studio-debugger"></a>Visual Studio 디버거를 사용 하는 c + +를 사용 하 여 디버그

Visual Studio 디버거는 앱을 디버그할 수 있도록 여러 강력한 기능을 제공 합니다. 이 항목에는 기본 기능 중 일부에 대해 알아보는 빠른 방법을 제공합니다.

## <a name="create-a-new-project"></a>새 프로젝트 만들기 

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택합니다.

2. **Visual C++**에서 **Windows 데스크톱**을 선택한 다음, 가운데 창에서 **Windows 콘솔 응용 프로그램**을 선택합니다.

    표시 되지 않으면는 **Windows 콘솔 응용 프로그램** 서식 파일 프로젝트를 클릭 하 여는 **Open Visual Studio 설치 관리자** 의 왼쪽된 창에서 링크는 **새 프로젝트** 대화 상자. Visual Studio 설치 관리자가 시작됩니다. 선택 된 **c + + 데스크톱 개발** 작업을 선택 합니다 **수정**합니다.

3. 같은 이름을 입력 **MyDbgApp** 클릭 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

4. MyDbgApp.cpp에서 다음 코드를 

    ```c++
    int main()
    {
        return 0;
    }
    ```

    이 코드로 바꿉니다(`#include "stdafx.h"` 제거 안 함).

    ```c++
    #include <list>  
    #include <iostream>

    using namespace std;

    void doWork()
    {
        list <int> c1;

        c1.push_back(10);
        c1.push_back(20);

        const list <int> c2 = c1;
        const int &i = c2.front();
        const int &j = c2.front();
        cout << "The first element is " << i << endl;
        cout << "The second element is " << j << endl;

    }

    int main()
    {
        doWork();
    }
    ```

## <a name="set-a-breakpoint"></a>중단점 설정

A *중단점* 은 Visual Studio 사용자 실행 일시 중지 해야 할지 여부를 나타내는 표식 코드가 메모리 또는 여부는 분기의 코드는 실행의 동작 또는 변수 값을 참조 될 수 있도록 합니다. 디버깅의 가장 기본적인 기능입니다.

1. 왼쪽 여백에 중단점을 설정 하려면을 클릭는 `doWork` 함수 호출 (키를 눌러 코드 줄을 선택 하거나 **F9**).

    ![중단점을 설정](../debugger/media/dbg-qs-set-breakpoint.png "중단점 설정")

2. 이제 키를 눌러 **F5** (선택 또는 **디버그 > 디버깅 시작**).

    ![중단점이 적중](../debugger/media/dbg-qs-hit-breakpoint.png "중단점에 도달")

    중단점을 설정 하면 디버거에서 일시 중지 합니다. 디버거 및 앱 실행 일시 중지 된 문에 노란색 화살표로 표시 됩니다. 한 줄으로 된 `doWork` 함수 호출은 아직 실행 되지 않았습니다.

    > [!TIP]
    > 루프 또는 재귀에 중단점이 있는 하거나 자주를 단계별로 실행 하는 많은 중단점을 설정한 경우 사용 하는 경우는 [조건부 중단점](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) 특정 조건이 충족 되는 경우에 코드는 일시 중단 되도록 합니다. 조건부 중단점을 시간 절약 하 고 또한 쉽게 만들 수는 재현 하기 어려운 문제를 디버깅 하 합니다.

    메모리 관련 오류가 c + +에서 디버그를 시도할 때 사용할 수도 있습니다 중단점 주소 값 (NULL 검색)을 검사 하 고 개수를 참조 합니다. 

## <a name="navigate-code"></a>코드 탐색

디버거를 계속 하도록 지시 하려면 명령입니다. Visual Studio 2017에 새로 추가 된 유용 코드 탐색 명령을 보여줍니다.

중단점에서 일시 중지 된 동안 위로 마우스를 가져가고 문을 `c1.push_back(20)` 녹색 될 때까지 **클릭 하 여 실행** 단추 ![클릭에 실행](../debugger/media/dbg-tour-run-to-click.png "RunToClick") 나타나고 누릅니다는 **클릭 하 여 실행** 단추입니다.

![클릭 하 여 실행](../debugger/media/dbg-qs-run-to-click.png "클릭 하 여 실행")

응용 프로그램 실행을 계속 호출 `doWork`, 단추를 클릭 하면 코드 줄에서 일시 중지 하 고 있습니다.

하는 데 사용 되는 일반적인 키보드 명령 코드를 단계별로 포함 **F10** 및 **F11**합니다. 더 자세한 지침에 대 한 참조는 [초보자 가이드](../debugger/getting-started-with-the-debugger.md)합니다.

## <a name="inspect-variables-in-a-datatip"></a>Datatip에서 변수 검사

1. (노란색 실행 포인터에 의해 표시 된) 코드의 현재 줄에서 마우스로 `c1` 마우스 datatip을 표시 하는 개체입니다.

    ![Datatip 보기](../debugger/media/dbg-qs-data-tip.png "datatip 보기")

    Datatip의 현재 값을 보여 줍니다는 `c1` 변수 및 해당 속성을 검사할 수 있습니다. 디버깅, 감염 되지 않은 값이 표시를 코드의 이전 또는 호출 줄에서 버그 아마도 필요. 

2. 확장의 현재 속성 값을 살펴볼 수 datatip은 `c1` 개체입니다.

3. 값을 보려면 계속할 수 있도록 datatip을 고정 하려면 `c1` 코드를 실행 하는 동안 작은 압정 아이콘을 클릭 합니다. (고정 된 datatip을 편리한 위치에 이동할 수 있습니다.)

## <a name="edit-code-and-continue-debugging"></a>코드를 편집 하 고 디버깅을 계속합니다

디버깅 세션 중에 코드에서 테스트 하려면 변경 내용을 식별 한 경우에 너무 수행할 수 있습니다.

1. 두 번째 인스턴스를 클릭 `c2.front()` 변경 `c2.front()` 를 `c2.back()`합니다.

2. 키를 눌러 **F10** (또는 **디버그 > 프로시저 단위 실행**)를 여러 번 진행 하는 디버거 고 편집 된 코드를 실행 합니다.

    ![편집 하며 계속 하기](../debugger/media/dbg-qs-edit-and-continue.gif "편집 하며 계속 하기")

    **F10** 함수 (지정 하지 않으려면는 코드를 실행 여전히)를 단계별로 실행 하는 대신에 한 번 있지만 단계가 하나 디버거 문이 앞으로 이동 합니다.

편집 하며 계속 하기를 사용 하 여 및 기능 제한 사항에 자세한 내용은 참조 하십시오. [편집 하며 계속 하기](../debugger/edit-and-continue.md)합니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 코드를 단계별로 실행 하 고 디버거를 시작 하 고 변수를 검사 하는 방법을 배웠습니다. 높은 수준의 디버거 기능 추가 정보에 대 한 링크를 확인 하려는 경우.

> [!div class="nextstepaction"]
> [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)
