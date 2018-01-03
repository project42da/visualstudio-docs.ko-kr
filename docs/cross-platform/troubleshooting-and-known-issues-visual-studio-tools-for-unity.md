---
title: "문제 해결 및 알려진 문제(Visual Studio Tools for Unity) | Microsoft Docs"
ms.custom: 
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f5db192-8d78-4627-bd07-dbbc803ac554
caps.latest.revision: "5"
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload: unity
ms.openlocfilehash: 7ede7734ec2a8c261cce3f31e06e77f932edd326
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-and-known-issues-visual-studio-tools-for-unity"></a>문제 해결 및 알려진 문제(Visual Studio Tools for Unity)
이 섹션에서는 Visual Stuio Tools for Unity와 관련된 일반적인 문제에 대한 솔루션, 알려진 문제의 설명을 찾아보고 오류를 보고하여 Visual Studio Tools for Unity를 개선하는 데 도움이 되는 방법을 알아봅니다.  

## <a name="troubleshooting"></a>문제 해결  
Visual Studio Tools for Unity에 대한 몇 가지 일반적인 문제를 해결하려면 다음 섹션을 참조하세요.  

### <a name="visual-studio-crashes"></a>Visual Studio 크래시
Visual Studio MEF 캐시가 손상되었기 때문에 발생할 수 있습니다.

MEF 캐시를 다시 설정하려면 다음 폴더를 제거해야 합니다. 먼저 Visual Studio를 닫은 후에 이 작업을 수행하세요.

```batch
%localappdata%\Microsoft\VisualStudio\<version>\ComponentModelCache
```

이렇게 하면 문제가 해결됩니다. 문제가 여전히 발생하는 경우 관리자 권한으로 Visual Studio용 개발자 명령 프롬프트를 실행하고 다음 명령을 사용합니다.

```batch
 devenv /setup
```

### <a name="issues-with-vs2015-and-intellisense-or-code-coloration"></a>VS2015 및 Intellisense 또는 코드 색 지정 관련 문제
Visual Studio 2015를 업데이트 3으로 업그레이드해야 합니다.

### <a name="visual-studio-hangs"></a>Visual Studio 중지
Parse, FMOD, UMP(Universal Media Player), ZFBrowser 또는 Embedded Browser와 같이 몇 가지 Unity 플러그인은 네이티브 스레드를 사용합니다. 플러그인에서 네이티브 스레드를 런타임에 연결할 때 발생하는 문제이며, 이는 OS에 대한 호출을 차단합니다. 즉 Unity에서 디버거(또는 도메인 다시 로드)에 대한 해당 스레드를 중단하고 정지할 수 없습니다.

FMOD의 경우 일시적인 해결 방법이 있습니다. 즉 FMOD_STUDIO_INIT_SYNCHRONOUS_UPDATE 초기화 [플래그](https://www.fmod.org/docs/content/generated/FMOD_STUDIO_INITFLAGS.html)를 전달하여 비동기 처리를 비활성화하고 주 스레드에서 모든 처리를 수행할 수 있습니다.

### <a name="incompatible-project-in-visual-studio"></a>Visual Studio에서 호환되지 않는 프로젝트
먼저 Unity에서 Visual Studio가 외부 스크립트 편집기로 설정되어 있는지 확인합니다(편집/기본 설정/외부 도구). 다음으로 Unity에 Visual Studio 플러그인이 설치되어 있는지 확인합니다(도움말/정보에 Microsoft Visual Studio Tools for Unity와 같은 메시지가 표시되어야 함). 다음으로 확장이 Visual Studio에 제대로 설치되어 있는지 확인합니다(도움말/정보).

### <a name="assembly-reference-issues"></a>어셈블리 참조 문제
프로젝트가 복잡한 전체 참조이거나 이 생성 단계를 더 잘 제어하려는 경우 [API](../cross-platform/customize-project-files-created-by-vstu.md)를 사용하여 생성된 프로젝트 또는 솔루션 콘텐츠를 조작할 수 있습니다. Unity 프로젝트에서 [응답 파일](https://docs.unity3d.com/Manual/PlatformDependentCompilation.html)을 사용할 수도 있으며, 이렇게 처리할 예정입니다.

### <a name="breakpoints-with-a-warning"></a>경고가 있는 중단점
Visual Studio에서 특정 중단점에 대한 원본 위치를 찾을 수 없는 경우 중단점 주변에 경고가 표시됩니다. 사용하는 동작이 현재 Unity 장면에 제대로 로드/사용되었는지 확인합니다.

### <a name="breakpoints-not-hit"></a>적중되지 않는 중단점
 사용하는 동작이 현재 Unity 장면에 제대로 로드/사용되었는지 확인합니다. Visual Studio와 Unity를 모두 종료한 다음 생성된 모든 파일(*.csproj, *.sln)과 전체 라이브러리 폴더를 삭제합니다.

### <a name="unable-to-attach"></a>연결할 수 없음
-   VS 및 Unity 모두에 대해 바이러스 백신을 일시적으로 사용하지 않도록 설정하거나 제외 규칙을 만들어 봅니다.
-   방화벽을 일시적으로 사용하지 않도록 설정하거나 VS와 Unity 간에 TCP/UDP 네트워킹을 허용하는 규칙을 만들어 봅니다.
-   팀 뷰어와 같은 프로그램이 프로세스 검색을 방해하고 있음을 확인했습니다. 모든 추가 소프트웨어를 일시적으로 중지하여 변경된 소프트웨어가 있는지 확인해 볼 수도 있습니다.
-   VSTU가 "Unity.exe" 프로세스를 모니터링하는 경우 기본 Unity 실행 파일의 이름을 바꾸지 않습니다.

### <a name="unable-to-debug-android-players"></a>Android 플레이어를 디버그할 수 없음
플레이어 검색(Unity에서 사용하는 기본 메커니즘)에 멀티캐스트를 사용하지만, 이후에는 일반 TCP 연결을 사용하여 디버거를 연결합니다. 검색 단계는 Android 장치에 대한 주요 문제입니다.

USB는 디버깅에서 매우 빠르지만 Unity 플레이어 검색 메커니즘과 호환되지 않습니다.
Wi-Fi는 대기 시간 때문에 USB에 비해 유연성이 뛰어나지만 속도가 느립니다. 일부 라우터 또는 장치에 대해 적절한 멀티캐스트 지원이 부족하다는 것을 확인했습니다(Nexus 시리즈는 이에 대해 잘 알려져 있음).

USB를 통해 다음을 시도하여 연결된 장치에서 열려 있는 포트를 확인할 수도 있습니다(디버깅 포트를 확인할 수 있도록 플레이어를 가동 및 실행함, 항상 56xxx 형식으로 표시).

```shell  
adb shell netstat
```  

로컬 PC에 포트를 전달합니다.

```shell  
adb forward tcp:56xxx tcp:56xxx
```  

그런 다음 전달된 127.0.0.1:56xxx 포트를 사용하여 VSTU를 연결합니다.

### <a name="migrating-from-unityvs-to-visual-studio-tools-for-unity"></a>UnityVS에서 Visual Studio Tools for Unity로 마이그레이션  
 UnityVS에서 Visual Studio Tools for Unity로 마이그레이션하려면 Unity 프로젝트에 대한 새로운 Visual Studio 솔루션을 생성해야 합니다.  

##### <a name="to-migrate-your-unity-project-from-unityvs-18-to-visual-studio-tools-for-unity-19"></a>UnityVS 1.8에서 Visual Studio Tools for Unity 1.9로 Unity 프로젝트를 마이그레이션하려면  

1.  Unity 프로젝트에서 이전 솔루션 및 프로젝트 파일을 삭제합니다. Unity 프로젝트의 루트 디렉터리에서 Visual Studio .sln 및 .* proj 파일을 찾아 모두 삭제합니다.  

2.  Visual Studio Tools for Unity 패키지를 Unity 프로젝트로 가져옵니다. VSTU 패키지를 가져오는 방법에 대한 자세한 내용은 [시작](../cross-platform/getting-started-with-visual-studio-tools-for-unity.md) 페이지에서 Visual Studio Tools for Unity 구성을 참조하세요.  

3.  새 솔루션 및 프로젝트 파일을 생성합니다. 지금 생성하려면 Unity 편집기의 주 메뉴에서 **Visual Studio Tools**, **프로젝트 파일 생성**을 선택합니다. 그렇지 않으면 원하는 경우 이 단계를 건너뛸 수 있습니다. **Visual Studio Tools**, **Visual Studio에서 열기**를 선택하면 Visual Studio Tools for Unity에서 새 파일을 자동으로 생성합니다.  

### <a name="on-windows-visual-studio-asks-to-download-the-unity-target-framework"></a>Windows에서 Visual Studio는 Unity 대상 프레임워크를 다운로드하도록 요청합니다.  
 Visual Studio Tools for Unity를 사용하려면 Windows 8 또는 10에 기본적으로 설치되지 않는 .NET Framework 3.5가 필요합니다. 이 문제를 해결하려면 지침에 따라 .net framework 3.5를 다운로드하고 설치하세요.  

## <a name="known-issues"></a>알려진 문제  
 Visual Studio Tools for Unity에는 디버거가 C# 컴파일러의 Unity 이전 버전과 상호작용하는 방법에서 발생하는 알려진 문제가 있습니다. 문제를 해결하기 위해 노력 중이지만 해결하기 전까지 다음과 같은 문제가 발생할 수 있습니다.  

-   디버그할 때 Unity가 충돌되는 경우가 있습니다.  

-   디버그할 때 Unity가 중지되는 경우가 있습니다.  

-   특히 반복기 또는 switch 문 내에서 경우에 따라 메서드를 한 단계씩 코드 실행하고 메서드의 프로시저에서 나가는 동작이 제대로 작동하지 않습니다.  

## <a name="reporting-errors"></a>오류 보고  
 충돌, 고정 또는 기타 오류가 발생하는 경우 오류 보고서를 전송하여 Visual Studio Tools for Unity의 품질을 개선할 수 있도록 도와주시기 바랍니다. Visual Studio Tools for Unity의 문제를 조사하고 해결하는 데 도움이 됩니다. 감사합니다!  

### <a name="how-to-report-an-error-when-visual-studio-freezes"></a>Visual Studio가 고정될 때 오류를 보고하는 방법  
 Visual Studio가 Visual Studio Tools for Unity로 디버그할 때 중지되는 경우가 있다는 보고가 있지만 이 문제를 파악하려면 더 많은 데이터가 필요합니다. 아래의 단계를 따라 이 문제를 조사하는 데 도움을 주실 수 있습니다.  

##### <a name="to-report-that-visual-studio-freezes-while-debugging-with-visual-studio-tools-for-unity"></a>Visual Studio가 Visual Studio Tools for Unity로 디버그할 때 중지되는 문제를 보고하려면

*Windows:*  

1.  새 Visual Studio 인스턴스를 엽니다.

2.  프로세스에 연결 대화 상자를 엽니다. Visual Studio의 새 인스턴스에 있는 주 메뉴에서 **디버그**, **프로세스에 연결**을 선택합니다.  

3.  Visual Studio의 중지된 인스턴스에 디버거를 연결합니다. **프로세스에 연결** 대화 상자에서 **사용 가능한 프로세스** 테이블로부터 Visual Studio의 중지된 인스턴스를 선택한 다음 **연결** 단추를 선택합니다.  

4.  디버거를 일시 중지합니다. Visual Studio의 새 인스턴스에 있는 주 메뉴에서 **디버그**, **모두 중단**을 차례로 선택하거나 **Ctrl+Alt+Break**를 누르기만 하면 됩니다.  

5.  스레드 덤프를 만듭니다. [명령] 창에서 다음 명령을 입력하고 **Enter** 키를 누릅니다.  

    ```powershell  
    Debug.ListCallStack /AllThreads /ShowExternalCode  
    ```  

    **명령** 창이 먼저 표시되도록 해야 할 수 있습니다. Visual Studio의 주 메뉴에서 **보기**, **다른 창**, **명령 창**을 선택합니다.  

*Mac:*

1. 터미널을 열고 Mac용 Visual Studio의 PID를 가져옵니다.

    ```shell  
    ps aux | grep "[V]isual Studio.app"
    ```

1. lldb 디버거를 시작합니다.

    ```shell  
    lldb
    ```

1. PID를 사용하여 Mac용 Visual Studio 인스턴스에 연결합니다.

    ```shell  
    process attach --pid THE_PID_OF_THE_VSFM_PROCESS
    ```

1. 모든 스레드에 대한 스택 추적을 검색합니다.

    ```shell  
    bt all
    ```

마지막으로 Visual Studio가 중지되었을 때 수행한 작업에 대한 설명과 함께 스레드 덤프를 [vstusp@microsoft.com](mailto:vstusp@microsoft.com)으로 보냅니다.
