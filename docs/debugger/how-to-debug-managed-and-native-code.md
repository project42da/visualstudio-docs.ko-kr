---
title: '자습서: 관리 / 네이티브 코드를 디버깅 하 | Microsoft Docs'
description: .NET Core 또는.NET Framework 응용 프로그램에서 네이티브 DLL을 디버깅 하는 방법에 알아봅니다
ms.custom: ''
ms.date: 04/27/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
- C++
helpviewer_keywords:
- mixed mode debugging
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: aeb74bac5196450ec98426727a1456a009adb5c1
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="tutorial-debug-managed-and-native-code-in-visual-studio"></a>자습서: Visual Studio에서 관리 및 네이티브 코드를 디버깅 합니다.

Visual Studio를 사용 하면 혼합된 모드 디버깅 라는 둘 이상의 디버거 형식을 디버깅할 때 설정할 수 있습니다. 이 자습서에서는 단일 디버깅 세션의 관리 및 네이티브 코드를 디버깅 하는 옵션을 설정 합니다. 이 자습서에서는 관리 되는 앱에서 네이티브 코드를 디버깅 하는 방법을 보여 줍니다. 하지만 그 반대의 경우에 수행할 수 있습니다 및 [네이티브 응용 프로그램에서 관리 코드를 디버깅](../debugger/how-to-debug-in-mixed-mode.md)합니다. 디버거는 또한 다른 유형의 디버깅과 같이 혼합된 모드 디버깅 지원 [Python 및 네이티브 코드](../python/debugging-mixed-mode-c-cpp-python-in-visual-studio.md) 및 ASP.NET과 같은 응용 프로그램 형식에서 스크립트 디버거를 사용 합니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 간단한 기본 DLL 만들기
> * DLL을 호출 하는 간단한.NET Core 또는.NET Framework 앱 만들기
> * 디버거 시작
> * 관리 되는 앱의 중단점은 적중
> * 네이티브 코드를 한 단계씩

## <a name="prerequisites"></a>전제 조건

* Visual Studio가 설치 되어 있어야 하며 **c + + 데스크톱 개발** 작업 합니다.

    아직 Visual Studio를 설치하지 않은 경우 [여기](http://www.visualstudio.com)에서 평가판을 설치합니다.

    워크로드를 설치해야 하지만 이미 Visual Studio가 있는 경우 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Open Visual Studio 설치 관리자** 링크를 클릭합니다. Visual Studio 설치 관리자가 시작됩니다. **Node.js 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

* 또한 있어야는 **.NET 데스크톱 개발** 작업 부하 또는 **플랫폼 간 개발용.NET Core** 설치 작업을 만들려고 할 형식에 응용 프로그램에 따라 합니다.

## <a name="create-a-simple-native-dll"></a>간단한 기본 DLL 만들기

1. Visual Studio에서 선택 **파일** > **새로** > **프로젝트**합니다.

1. 에 **새 프로젝트** 대화 상자에서 선택 **Visual c + +**, **일반** 설치 된 템플릿 섹션에서 한 다음 가운데 창에서 선택 **빈 프로젝트** .

1. 에 **이름** 필드를 입력 **혼합 모드 디버깅** 클릭 **확인**합니다.

    Visual Studio 솔루션 탐색기에서 오른쪽 창에 표시 되는 빈 프로젝트를 만듭니다.

1. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭는 **소스 파일** 노드 c + + 프로젝트를 선택한 후 **추가** > **새 항목**를 선택한 후 **c + + 파일 (.cpp)** 합니다. 파일 이름 지정 **혼합 Mode.cpp**, 선택 **추가**합니다.

    Visual Studio에서 새 c + + 파일을 추가합니다.

1. 다음 코드를 복사 *혼합 Mode.cpp*:

    ```cpp
    #include "Mixed_Mode.h"
    ```
1. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭는 **헤더 파일** 노드 c + +에서 프로젝트를 선택한 후 **추가** > **새 항목**를 선택한 후  **헤더 파일 (.h)** 합니다. 파일 이름 지정 **혼합 Mode.h**, 선택 **추가**합니다.

    Visual Studio 새 헤더 파일을 추가합니다.

1. 다음 코드를 복사 *혼합 Mode.h*:

    ```cpp
    #ifndef MIXED_MODE_MULTIPLY_HPP
    #define MIXED_MODE_MULTIPLY_HPP
    
    extern "C"
    {
        __declspec(dllexport) int __stdcall mixed_mode_multiply(int a, int b) {
            return a * b;
        }
    }
    #endif
    ```

1. 디버그 도구 모음에서 선택 된 **디버그** 구성 및 **Any CPU** 의 플랫폼으로 또는.NET Core를 선택 **x64** 플랫폼으로 합니다.

    > [!NOTE]
    > .NET Core에서 선택 **x64** 플랫폼으로 합니다. .NET core는 이것이 필요 하므로 항상 64 비트 모드에서 실행 됩니다.

1. 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 (**혼합 모드 디버깅**) 선택 하 고 **속성**합니다.

1. 에 **속성** 페이지에서 선택 **구성 속성** > **링커** > **고급**, 및 그런 다음는 **진입점 없음** 드롭 다운 목록 **아니요**합니다. 그런 다음 설정을 적용 합니다.

1. 에 **속성** 페이지에서 선택 **구성 속성** > **일반**를 선택한 후 **동적 라이브러리 (.dll)** 에서 **구성 유형을** 필드입니다. 그런 다음 설정을 적용 합니다.

    ![네이티브 DLL로 전환](../debugger/media/mixed-mode-set-as-native-dll.png)

1. 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **디버그** > **빌드**합니다.

    프로젝트가 오류 없이 빌드되어야 합니다.

## <a name="create-a-simple-net-framework-or-net-core-app-to-call-the-dll"></a>DLL을 호출 하는 간단한.NET Framework 또는.NET Core 앱 만들기

1. Visual Studio에서 선택 **파일** > **새로** > **프로젝트**합니다.

1. 응용 프로그램 코드에 대 한 템플릿을 선택 합니다.

    .NET framework에 **새 프로젝트** 대화 상자에서 선택 **Visual C#**, **클래식 Windows 데스크톱** 설치 된 템플릿 섹션에서 한 다음 가운데 창에서 선택 **콘솔 응용 프로그램 (.NET Framework)** 합니다.

    .NET core에서 **새 프로젝트** 대화 상자에서 선택 **Visual C#**, **.NET Core** 설치 된 템플릿 섹션에서 한 다음 가운데 창에서 선택  **콘솔 응용 프로그램 (.NET Core)** 합니다.

1. 에 **이름** 필드를 입력 **Mixed_Mode_Calling_App** 클릭 **확인**합니다.

    Visual Studio 솔루션 탐색기의 오른쪽 창에 나타나는 콘솔 프로젝트를 만듭니다.

1. *Program.cs*, 기본 코드를 다음 코드로 바꿉니다.

    ```c#
    using System;
    using System.Runtime.InteropServices;
    
    namespace Mixed_Mode_Calling_App
    {
        public class Program
        {
            // Replace the file path shown here with the
            // file path on your computer. For .NET Core, the typical (default) path
            // for a 64-bit DLL might look like this:
            // C:\Users\username\source\repos\Mixed-Mode-Debugging\x64\Debug\Mixed-Mode-Debugging.dll
            // Here, we show a typical path for a DLL targeting the **Any CPU** option.
            [DllImport(@"C:\Users\username\source\repos\Mixed-Mode-Debugging\Debug\Mixed-Mode-Debugging.dll", EntryPoint =
            "mixed_mode_multiply", CallingConvention = CallingConvention.StdCall)]
            public static extern int Multiply(int x, int y);
            public static void Main(string[] args)
            { 
                int result = Multiply(7, 7);
                Console.WriteLine("The answer is {0}", result);
                Console.ReadKey();
            }
        }
    }
    ```

## <a name="configure-mixed-mode-debugging-net-framework"></a>혼합된 모드 디버깅 (.NET Framework) 구성

1. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭은 관리 되는 **Mixed_Mode_Calling_App** 프로젝트를 마우스 선택 **시작 프로젝트로 설정**합니다.

1. 관리 되는 마우스 오른쪽 단추로 클릭 **Mixed_Mode_Calling_App** 프로젝트를 선택한 후 **속성**를 선택한 후 **디버그** 왼쪽된 창에서. 선택 **네이티브 코드 디버깅 사용**, 한 다음 변경 내용을 저장 하는 속성 페이지를 닫습니다.

    ![혼합된 모드 디버깅을 사용 하도록 설정](../debugger/media/mixed-mode-enable-native-code-debugging.png)

## <a name="configure-mixed-mode-debugging-net-core"></a>혼합된 모드 디버깅 (.NET Core)를 구성 합니다.

혼합된 모드 디버깅을 사용 하 여.NET Core 응용 프로그램에서 네이티브 코드에 대 한 설정 해야 대부분 Visual Studio 2017의 버전에는 *launchSettings.json* 대신 파일에서 **속성** 페이지. 이 기능에 대 한 UI 업데이트를 추적 하려면이 참조 [GitHub 문제](https://github.com/dotnet/project-system/issues/1125)합니다.

1. 열기는 *launchSettings.json* 파일에 *속성* 폴더입니다. 기본적으로이 위치에 파일을 찾을 수 있습니다.

    *C:\Users\<사용자 이름 > \source\repos\Mixed_Mode_Calling_App\Properties*

    파일이 없는 경우 프로젝트 속성을 엽니다 (관리 되는 마우스 오른쪽 단추로 클릭 **Mixed_Mode_Calling_App** 솔루션 탐색기에서 프로젝트를 마우스 선택 **속성**). 임시 변경는 **디버그** 탭 하 고 프로젝트를 빌드해야 합니다. 수행한 변경 내용을 취소 합니다.

1. 에 *lauchsettings.json* 파일에서 다음 속성을 추가 합니다.

    ```
    "nativeDebugging": true
    ```
    
    따라서 예를 들어 파일에는 다음과 같습니다.
    
    ```
    {
      "profiles": {
        "Mixed_Mode_Calling_App": {
          "commandName": "Project",
          "nativeDebugging": true
        }
      }
    }
    ```

## <a name="set-a-breakpoint-and-start-the-debugger"></a>중단점을 설정 하 고 디버거를 시작

1. C# 프로젝트를 열고 *Program.cs* 왼쪽된 여백을 클릭 하 여 코드의 다음 줄에서 중단점을 설정 합니다.

    ```c#
    int result = Multiply(7, 7);
    ```

    중단점을 설정 했는지를 나타내는 데 왼쪽된 여백에 빨간색 원이 나타납니다.

1. 키를 눌러 **F5** (**디버그** > **디버깅 시작**) 디버거를 시작 합니다.

    디버거에 설정한 중단점에서 일시 중지 됩니다. 노란색 화살표는 디버거가 현재 일시 중지를 나타냅니다.

## <a name="step-into-native-code"></a>네이티브 코드를 한 단계씩

1. 관리 되는 앱에서 일시 중지 된 동안 **F11** (**디버그** > **한 단계씩 코드 실행**).

    네이티브 코드와 헤더 파일이 열리고 노란색 화살표는 디버거가 일시 중지를 참조 하십시오.

    ![네이티브 코드를 한 단계씩](../debugger/media/mixed-mode-step-into-native-code.png)

    이제, 집합 등의 작업 및 중단점을 적중할 수 있고 변수를 검사 합니다.

1. 변수 값이 해당 표시를 마우스로 가리킵니다.

1. 살펴보고는 **자동** 및 **지역** windows 변수 및 해당 값이 표시를 합니다.

    디버거에서 일시 중지 된 동안 다른 디버거 기능을와 같은 사용할 수 있습니다는 **조사식** 창 및 **호출 스택** 창.

1. 키를 눌러 **F11** 다시를 디버거 한 줄을 진행 합니다.

1. 키를 눌러 **Shift + F11** (**디버그** > **나가기**) 응용 프로그램 실행을 계속 하려면 다시 관리 되는 앱에서 일시 중지 합니다.

1. 앱을 계속하려면 **F5** 키를 누릅니다.

    지금까지 혼합된 모드 디버깅에 대 한 자습서를 완료 했습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 혼합된 모드 디버깅을 사용 하 여 관리 되는 앱에서 네이티브 코드를 디버깅 하는 방법을 배웠습니다. 간략하게 다른 디버거 기능에 대 한 다음 문서를 참조 합니다.

> [!div class="nextstepaction"]
> [디버거 소개](../debugger/debugger-feature-tour.md)