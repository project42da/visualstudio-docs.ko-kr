---
title: Visual Studio의 디버거를 실행 중인 프로세스에 연결 | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.processes.attach
- vs.debug.process
- vs.debug.programs
- vs.debug.detaching
- vs.debug.processes
- vs.debug.error.attach
- vs.debug.remotemachine
dev_langs:
- CSharp
- FSharp
- C++
- VB
helpviewer_keywords:
- remote debugging, attaching to programs
- processes, attaching to running processes
- Attach to Process dialog box
- debugging [Visual Studio], attaching to processes
- debugger, processes
ms.assetid: 27900e58-090c-4211-a309-b3e1496d5824
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fe345773cfa4a91789681969623e2174db60c54c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="attach-to-running-processes-with-the-visual-studio-debugger"></a>Visual Studio 디버거에서 실행 중인 프로세스에 연결
로컬 또는 원격 컴퓨터에서 실행 중인 프로세스에 Visual Studio 디버거를 연결할 수 있습니다. 프로세스를 실행 한 후 클릭 **디버그 > 프로세스에 연결** (하거나 키를 눌러 **CTRL + ALT + P**)를 열려면는 **프로세스에 연결** 대화 상자.

로컬 또는 원격 컴퓨터에서 실행 되는 응용 프로그램 디버깅, 동시에 여러 프로세스 디버깅 또는 Visual Studio에서 생성 되지 않은 응용 프로그램을 디버깅 하려면이 기능을 사용할 수 있습니다. 종종 유용는 응용 프로그램을 디버깅 하려는 경우 (어떤 이유로 든) 사용자가 시작 하지 앱 Visual Studio에서 디버거가 연결 된 하지만 합니다. 예를 들어가 디버거 없이 앱을 실행 하 고 예외를 적중 될 수 있습니다 다음에 연결 하 디버깅 하려면 응용 프로그램을 실행 하는 프로세스입니다.

> [!TIP]
> 사용 해야 할 지 여부를 모를 **프로세스에 연결** 디버깅 시나리오에 대 한? 참조 [일반적인 디버깅 시나리오](#BKMK_Scenarios)합니다. IIS에 배포 된, 참조는 ASP.NET 응용 프로그램을 디버깅 하려는 경우 [원격 IIS 컴퓨터에 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)합니다.

##  <a name="BKMK_Attach_to_a_running_process"></a> 로컬 컴퓨터에서 실행 중인 프로세스에 연결  
 프로세스에 연결 하기 위해 프로세스의 이름을 알고 있어야 (참조 [일반적인 디버깅 시나리오](#BKMK_Scenarios) 몇 가지 일반적인 프로세스 이름에 대 한).
  
1.  Visual Studio에서 선택 **디버그 > 프로세스에 연결** (하거나 키를 눌러 **CTRL + ALT + P**).

    신속 하 게 다시 연결 하는 프로세스를 대신 하는 경우 참조 [프로세스에 다시 연결](#BKMK_reattach)합니다.
  
2.  **프로세스에 연결** 대화 상자의 **사용 가능한 프로세스** 목록에서 연결할 프로그램을 찾습니다.  

     원하는 프로세스를 신속 하 게 선택 하려면 프로세스 이름의 첫 글자를 입력 합니다. 프로세스 이름을 모르면 참조 [일반적인 디버깅 시나리오](#BKMK_Scenarios)합니다.
     
     ![DBG_Basics_Attach_To_Process](../debugger/media/DBG_Basics_Attach_To_Process.png "DBG_Basics_Attach_To_Process") 
  
     프로세스가 다른 사용자 계정으로 실행되고 있으면 **모든 사용자의 프로세스 표시** 확인란을 선택합니다.
  
3.  **연결 대상** 상자에서 디버깅할 코드 형식이 표시되어 있는지 확인합니다. 기본 **자동** 설정은 디버깅할 코드 형식을 결정합니다. 코드 형식을 수동으로 설정하려면, 다음을 수행합니다.  
  
    1.  **연결 대상** 상자에서 **선택**을 클릭합니다.  
  
    2.  **코드 형식 선택** 대화 상자에서 **다음 코드 형식 디버깅** 을 클릭하고 디버깅할 형식을 선택합니다.  
  
    3.  **확인**을 클릭합니다.  
  
4.  **연결**을 클릭합니다.

##  <a name="BKMK_Attach_to_a_process_on_a_remote_computer"></a> 원격 컴퓨터의 프로세스에 연결  
 프로세스에 연결 하기 위해 프로세스의 이름을 알고 있어야 (참조 [일반적인 디버깅 시나리오](#BKMK_Scenarios) 몇 가지 일반적인 프로세스 이름에 대 한). IIS에 배포 된 ASP.NET 응용 프로그램에 대 한 자세한 지침에 대 한 참조 [원격 IIS 컴퓨터에 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)합니다. 다른 앱은 작업 관리자에서 프로세스 이름을 찾을 수 있습니다.
  
 **프로세스에 연결** 대화 상자를 사용할 때 원격 디버깅용으로 설정된 다른 컴퓨터를 선택할 수 있습니다. 자세한 내용은 참조 [원격 디버깅](../debugger/remote-debugging.md)합니다. 원격 컴퓨터를 선택하면 해당 컴퓨터에서 실행되는 사용 가능한 프로세스의 목록을 볼 수 있고 디버깅을 위해 하나 이상의 프로세스에 연결할 수 있습니다.
  
 **원격 컴퓨터를 선택 하려면**  

1. Visual Studio에서 선택 **디버그 > 프로세스에 연결** (하거나 키를 눌러 **CTRL + ALT + P**).

    신속 하 게 다시 연결 하는 프로세스를 대신 하는 경우 참조 [프로세스에 다시 연결](#BKMK_reattach)합니다.

2.  **프로세스에 연결** 대화 상자의 **전송** 목록에서 적합한 연결 형식을 선택합니다. 대부분의 경우에는**기본값** 이 올바른 설정입니다.

    **전송** 설정은 디버깅 세션에 상관없이 유지됩니다. 
  
3.  **한정자** 목록 상자를 사용하여 다음 방법 중 하나로 원격 컴퓨터 이름을 선택합니다.  
  
    1.  **한정자** 목록 상자에 이름을 입력합니다.
    
        >**참고** 경우 이후 단계에서 원격 컴퓨터 이름을 사용 하 여 연결할 수 없습니다, IP 주소를 사용 합니다. (포트 번호는 프로세스를 선택한 후 자동으로 나타날 수 있습니다. 또한이 직접 입력 합니다. 다음 그림에서는 4020 이지만 원격 디버거에 대 한 기본 포트)  

        사용 하려는 경우는 **찾을** 단추를 해야 할 수 있습니다 [UDP 포트 3702 열고](../debugger/remote-debugger-port-assignments.md) 서버의 합니다.
  
    2.  **한정자** 목록 상자 옆에 있는 드롭다운 화살표를 클릭하고 드롭다운 목록에서 컴퓨터 이름을 선택합니다.  
  
    3.  **한정자** 목록 옆에 있는**찾기** 단추를 클릭하여 **원격 디버거 연결 선택** 대화 상자를 엽니다. **원격 디버거 연결 선택** 대화 상자에는 로컬 서브넷에 있는 모든 장치와 이더넷 케이블을 통해 컴퓨터에 직접 연결된 모든 장치가 나열됩니다. 원하는 컴퓨터 또는 장치를 클릭한 다음 **선택**을 클릭합니다. 
  
     **한정자** 설정은 해당 한정자를 사용하여 디버깅 연결에 성공한 경우에만 디버깅 세션 간에 유지됩니다.
     
4.  **새로 고침**가 있어야 합니다.

      **사용 가능한 프로세스** 목록은 **프로세스** 대화 상자를 열 때 자동으로 표시됩니다. 대화 상자가 열려 있는 동안 백그라운드에서 프로세스를 시작하고 중지할 수 있습니다. 그러나 내용이 현재 상태가 아닐 수 있습니다. 언제든지 **새로 고침**을 클릭하여 목록을 새로 고치고 현재 프로세스 목록을 확인할 수 있습니다. 
     
4.  **프로세스에 연결** 대화 상자의 **사용 가능한 프로세스** 목록에서 연결할 프로그램을 찾습니다.

     원하는 프로세스를 신속 하 게 선택 하려면 프로세스 이름의 첫 글자를 입력 합니다. 프로세스 이름을 모르면 참조 [일반적인 디버깅 시나리오](#BKMK_Scenarios)합니다.
  
     프로세스가 다른 사용자 계정으로 실행되고 있으면 **모든 사용자의 프로세스 표시** 확인란을 선택합니다.
     
5.  **연결**을 클릭합니다.

## <a name="BKMK_reattach"></a> 프로세스에 다시 연결

선택 하 여에 이전에 연결 된 프로세스에 신속 하 게 다시 연결할 수 **디버그 > 프로세스에 다시 연결 중...** (**Shift + Alt + P**). 이 명령을 선택할 때 디버거는 즉시 연결 하려고 마지막으로 사용 하 여 연결 프로세스는 **프로세스에 연결** 대화 상자.

디버거에서 이전 프로세스 ID와 일치 하도록 처음 시도 하 여 다시 연결 됩니다 한 다음 경우는 실패 하면 이전 프로세스 이름으로 비교 하 여 합니다. 일치 하는 경우 또는 여러 프로세스를 같은 이름의 찾을 수 없는 경우 하면 **프로세스에 연결** 올바른 프로세스를 선택할 수 있도록 대화 상자가 표시 됩니다.

> [!NOTE]
> **프로세스에 다시 연결** 명령 Visual Studio 2017의 새로운 기능입니다.

## <a name="additional-info"></a>추가 정보

디버깅하는 동안 여러 프로그램에 연결할 수 있지만 언제든지 디버거에서 활성화되는 프로그램은 한 개뿐입니다. **디버그 위치** 도구 모음이나 **프로세스** 창에서 활성 프로그램을 설정할 수 있습니다.  
  
신뢰할 수 없는 사용자 계정에서 소유한 프로세스에 연결하면 보안 경고 확인 대화 상자가 나타납니다. 자세한 내용은 참조 하십시오. [보안 경고: 신뢰할 수 없는 사용자가 소유한 프로세스에 연결 위험할 수 있습니다. 다음 정보가 의심 스 럽 확실 하지 않은 경우이 프로세스에 연결 하지 마십시오](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process.md)합니다.  
  
원격 데스크톱(터미널 서비스) 세션에서 디버그할 때 **사용 가능한 프로세스** 목록에 사용 가능한 프로세스 중 일부가 표시되지 않는 경우가 있습니다. 제한된 사용자 계정의 사용자로 Visual Studio를 실행하는 경우 서비스 및 w3wp.exe를 비롯한 다른 서버 프로세스에 사용되는 세션 0에서 실행되는 프로세스는 **사용 가능한 프로세스** 목록에 표시되지 않습니다. 관리자 계정으로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 실행하거나 터미널 서비스 세션 대신 서버 콘솔에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 실행하여 이 문제를 해결할 수 있습니다. 이러한 해결 방법을 둘 다 사용할 수 없는 경우 세 번째 방법으로 Windows 명령줄에서 `vsjitdebugger.exe -p` *ProcessId* 를 실행하여 프로세스에 연결합니다. 프로세스 ID는 tlist.exe를 사용하여 확인할 수 있습니다. tlist.exe를 얻으려면  [WDK 및 WinDbg 다운로드](http://go.microsoft.com/fwlink/?LinkId=168279)에서 Debugging Tools for Windows를 다운로드하여 설치합니다.

## <a name="BKMK_Scenarios"></a> 일반적인 디버깅 시나리오

사용 해야 하는지 여부를 확인할 수 있도록 **프로세스에 연결** 및 프로세스에 연결 하는 몇 가지 일반적인 디버깅 시나리오 여기에 표시 됩니다 (목록은 완전 한 목록이 아님). 자세한 지침을 사용할 수 있는 링크를 제공 합니다.

일부 응용 프로그램 형식 (예: UWP 앱)에 대 한 프로세스 이름에 직접 연결 하지 않은 수 있지만를 사용 하 여는 **설치 된 응용 프로그램 패키지 디버그** 메뉴 옵션을 사용 (표 참조).

> [!NOTE]
> Visual Studio에서 기본 디버깅에 대 한 정보를 참조 하십시오. [디버거 시작](../debugger/getting-started-with-the-debugger.md)합니다.

|시나리오|메서드를 디버그 합니다.|프로세스 이름|정보 및 링크|
|-|-|-|-|
|로컬 컴퓨터에서 관리 또는 네이티브 응용 프로그램을 디버깅|사용 하 여 프로세스에 연결 또는 [표준 디버깅](../debugger/getting-started-with-the-debugger.md)|*appname*.exe|대화 상자에 신속 하 게 액세스를 사용 하 여 **CTRL + ALT + P** 프로세스 이름의 첫 글자를 입력 합니다.|
|디버거 없이 앱을 시작한 후 로컬 컴퓨터에 ASP.NET 응용 프로그램을 디버깅 합니다.|프로세스에 사용 하 여 연결|iiexpress.exe|이 로드 하는 응용 프로그램을 만들 유용할 수 속도가 더와 같은 (예) 프로 파일링 할 경우. |
|원격 디버깅 ASP.NET 4 또는 4.5는 IIS 서버에|원격 도구를 사용 하 고 프로세스에 연결|w3wp.exe|참조 [원격 IIS 컴퓨터에 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|IIS 서버에서 ASP.NET Core 원격 디버그|원격 도구를 사용 하 고 프로세스에 연결|dotnet.exe|응용 프로그램 배포에 대 한 참조 [IIS에 게시](https://docs.asp.net/en/latest/publishing/iis.html)합니다. 디버깅을 위해 참조 [원격 IIS 컴퓨터에 있는 원격 디버깅 ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)|
|서버 프로세스에서 다른 지원 되는 응용 프로그램 형식을 디버그합니다|(원격 서버 경우) 원격 도구를 사용 하 고 프로세스에 연결|iexplore.exe 또는 다른 프로세스|필요한 경우 작업 관리자를 사용 하 여 프로세스를 식별할 수 있도록 합니다. 참조 [원격 디버깅](../debugger/remote-debugging.md) 및이 항목의 뒷부분에 나오는 섹션|
|Windows 데스크톱 응용 프로그램 원격 디버그|원격 도구와 F5|N/A| 참조 [원격 디버깅](../debugger/remote-debugging.md)|
|UWP (유니버설), OneCore 및 HoloLens, IoT 응용 프로그램을 디버깅 하는 원격|설치 된 응용 프로그램 패키지 디버그|N/A|참조 [설치 된 응용 프로그램 패키지 디버그](debug-installed-app-package.md) 사용 하는 대신 **프로세스에 연결**|
|Visual Studio에서 시작 하지 않은 앱 UWP (유니버설 Windows), OneCore 및 HoloLens, IoT 앱을 디버그|설치 된 응용 프로그램 패키지 디버그|N/A|참조 [설치 된 응용 프로그램 패키지 디버그](debug-installed-app-package.md) 사용 하는 대신 **프로세스에 연결**|  
  
> [!NOTE]
>  디버거에서 C++로 작성된 코드에 연결하려면 코드에 `DebuggableAttribute`가 있어야 합니다. 이 특성은 [/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute) 링커 옵션으로 링크하여 자동으로 코드에 추가할 수 있습니다.

## <a name="what-debugger-features-can-i-use"></a>디버거 기능을 사용할 수 있습니까?

Visual Studio 디버거 (예: 중단점을 적중)의 전체 기능을 사용 하려면 로컬 소스 및 기호 파일을 실행 정확히 일치 해야 프로세스에 연결 하는 경우 (즉, 디버거가 올바른 로드할 수 여야 합니다 [기호 (.pbd) 파일 ](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)). 기본적으로 디버그 빌드를 필요합니다.

원격 디버깅 시나리오에 대 한 Visual Studio에서 열려 있는 소스 코드 (또는 소스 코드의 복사본)이 있어야 합니다. 원격 컴퓨터에서 컴파일된 응용 프로그램 이진 파일은 로컬 컴퓨터에서와 같이 동일한 빌드에서 가져와야 합니다.

일부 로컬 디버깅 시나리오에서 디버그할 수 Visual Studio에서 원본에 액세스할 수 없는 앱 올바른 기호 파일이 있는 경우 (기본적으로이에서는 디버그 빌드에서). 자세한 내용은 참조 하십시오. [지정 기호 및 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)합니다.
  
##  <a name="BKMK_Troubleshoot_attach_errors"></a> 문제를 해결 연결 오류  
 실행 중인 프로세스에 디버거를 연결할 때 이 프로세스에는 한 가지 이상의 코드 형식이 포함될 수 있습니다. 디버거가 연결될 수 있는 코드 형식이 **코드 형식 선택** 대화 상자에서 표시되고 선택됩니다.  
  
 때로는 디버거가 한 코드 형식에는 연결되고 다른 코드 형식에는 연결되지 않을 수도 있습니다. 이러한 문제는 원격 컴퓨터에서 실행 중인 프로세스에 연결하려 할 때 발생할 수 있습니다. 원격 컴퓨터에 설치된 원격 디버깅 구성 요소가 일부 코드 형식만 지원하고 다른 코드 형식은 지원하지 않을 수도 있습니다. 데이터베이스를 직접 디버깅하기 위해 두 개 이상의 프로세스에 연결하려는 경우에도 이 문제가 발생할 수 있습니다. SQL 디버깅은 단일 프로세스에 대한 연결만 지원합니다.  
  
 디버거를 일부 코드 형식에 연결할 수 있지만 모든 코드 형식에 연결할 수는 없는 경우 연결할 수 없는 형식을 알려 주는 메시지가 나타납니다.  
  
 적어도 하나의 코드 형식에 디버거가 성공적으로 연결되면 프로세스 디버깅을 진행할 수 있습니다. 이 경우 성공적으로 연결된 코드 형식만 디버깅할 수 있습니다. 위 예제 메시지에서는 스크립트 코드 형식에 연결하지 못했음을 보여 줍니다. 따라서 이 프로세스 내의 스크립트 코드는 디버깅할 수 없습니다. 스크립트 코드는 프로세스 내에서 계속 실행되지만 스크립트에서 중단점을 설정하거나 데이터를 보거나 기타 디버깅 작업을 수행할 수는 없습니다.  
  
 디버거가 연결되지 않는 특정 코드 형식에만 다시 연결을 시도하면 해당 코드 형식에 디버거가 연결되지 않는 이유를 더 구체적으로 확인할 수 있습니다.  
  
 **코드 형식 연결 하지 못한 이유에 대 한 자세한 정보를 얻으려면**  
  
1.  프로세스에서 분리합니다. **디버그** 메뉴에서 **모두 분리**를 클릭합니다.  
  
2.  프로세스에 다시 연결하여 한 코드 형식만 선택합니다.  
  
    1.  **프로세스에 연결** 대화 상자의 **사용 가능한 프로세스** 목록에서 프로세스를 선택합니다.  
  
    2.  **선택**을 클릭합니다.  
  
    3.  **코드 형식 선택** 대화 상자에서 **다음 코드 형식 디버깅** 을 선택하고 연결에 실패한 코드 형식을 선택합니다. 다른 코드는 모두 선택 해제합니다.  
  
    4.  **확인**을 클릭합니다. **코드 형식 선택** 대화 상자가 닫힙니다.  
  
    5.  **프로세스에 연결** 대화 상자에서 **연결**을 클릭합니다.  
  
     이렇게 하면 연결이 완전히 실패하고 자세한 오류 메시지가 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [여러 프로세스 디버깅](../debugger/debug-multiple-processes.md)   
 [Just-in-time 디버깅](../debugger/just-in-time-debugging-in-visual-studio.md)   
 [원격 디버깅](../debugger/remote-debugging.md)