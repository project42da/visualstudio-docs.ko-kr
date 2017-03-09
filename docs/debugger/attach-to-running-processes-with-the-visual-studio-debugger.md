---
title: "Visual Studio 디버거에서 실행 중인 프로세스에 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.processes.attach"
  - "vs.debug.process"
  - "vs.debug.programs"
  - "vs.debug.detaching"
  - "vs.debug.processes"
  - "vs.debug.error.attach"
  - "vs.debug.remotemachine"
dev_langs: 
  - "C++"
  - "CSharp"
  - "FSharp"
  - "VB"
  - "c++"
helpviewer_keywords: 
  - "원격 디버깅, 프로그램에 연결"
  - "프로세스, 실행 중인 프로세스에 연결"
  - "프로세스에 연결 대화 상자"
  - "디버깅[Visual Studio], 프로세스에 연결"
  - "디버거, 프로세스"
ms.assetid: 27900e58-090c-4211-a309-b3e1496d5824
caps.latest.revision: 57
caps.handback.revision: 53
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Visual Studio 디버거에서 실행 중인 프로세스에 연결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 디버거 프로세스에 연결 하는 프로세스를 디버깅 하려면 하지만 Visual Studio에서 응용 프로그램을 시작 하지 않은 경우 종종 유용 합니다. 예를 들어 IIS 프로세스 또는.NET 응용 프로그램을 호스팅하는 Windows 서비스에 연결할 수 있습니다. 로컬 또는 원격 프로세스에 연결할 수 있습니다. 또 다른 예로 디버깅을 시작할 응용 프로그램을 실행 프로세스에 연결 다음 수 디버거 없이 응용 프로그램을 실행 하는 경우 예외가 발생 합니다.

일부 응용 프로그램 형식 (예: Windows 스토어 앱)에 대 한 프로세스 이름에 직접 연결 하지 않은 수 있지만를 사용 하 여는 **설치 된 응용 프로그램 패키지 디버그** 메뉴 옵션을 사용 (표 참조).

확인 하려면 해당 시나리오에 대 한 프로세스에 연결 하 든, 몇 가지 가장 일반적인 디버깅 시나리오는 다음과 같습니다. 자세한 지침을 사용할 수 있는 링크를 제공 합니다.

|시나리오|메서드를 디버그 합니다.|프로세스 이름|참고 및 링크|
|-|-|-|-|
|Visual Studio에서 시작 하 여 로컬 컴퓨터의 모든 지원 되는 응용 프로그램 형식을 디버그합니다|표준 F5 디버깅|N/A|참조 [디버거 시작](../debugger/getting-started-with-the-debugger.md)|
|원격 디버그 ASP.NET 4 또는 4.5는 IIS 서버에|원격 도구를 사용 하 고 프로세스에 연결|w3wp.exe|참조 [원격 IIS 컴퓨터에 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|IIS 서버에 원격 디버그 ASP.NET 코어|원격 도구를 사용 하 고 프로세스에 연결|dnx.exe|응용 프로그램 배포에 대 한 참조 [IIS에 게시](https://docs.asp.net/en/latest/publishing/iis.html)합니다. 디버깅을 위한 참조 [원격 IIS 컴퓨터에 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|서버 프로세스에서 다른 지원 되는 응용 프로그램 형식을 디버그합니다|(원격 서버 경우) 원격 도구를 사용 하 고 프로세스에 연결|iexplore.exe 또는 다른 프로세스|필요한 경우 작업 관리자를 사용 하 여 프로세스를 식별할 수 있습니다. 참조 [원격 디버깅](../debugger/remote-debugging.md) 및이 항목의 뒷부분에 나오는 섹션|
|Windows 데스크톱 응용 프로그램 원격 디버깅|원격 도구와 F5|N/A| 참조 [원격 디버깅](../debugger/remote-debugging.md)|
|Windows 유니버설 UWP (), OneCore, HoloLens, 또는 IoT 응용 프로그램을 디버깅 하는 원격|설치 된 응용 프로그램 패키지 디버그|N/A|사용 하 여 **디버그 / 기타 대상 디버그 / 설치 된 응용 프로그램 패키지 디버그** 대신 **프로세스에 연결**|
|Visual Studio에서 시작 하지 않은 하는 Windows 유니버설 UWP (), OneCore, HoloLens, 또는 IoT 응용 프로그램을 디버깅|설치 된 응용 프로그램 패키지 디버그|N/A|사용 하 여 **디버그 / 기타 대상 디버그 / 설치 된 응용 프로그램 패키지 디버그** 대신 **프로세스에 연결**|
  
> [!WARNING]
>  JavaScript로 작성된 Windows 유니버설 앱에 연결하려면 먼저 앱에 디버깅을 사용하도록 설정해야 합니다. Windows 개발자 센터에서 [Attach the debugger](../debugger/start-a-debugging-session-for-store-apps-in-visual-studio-javascript.md#BKMK_Attach_the_debugger) 을 참조하세요.  
  
> [!NOTE]
>  디버거에서 C++로 작성된 코드에 연결하려면 코드에 `DebuggableAttribute`가 있어야 합니다. 이 특성은 [/ASSEMBLYDEBUG](/visual-cpp/build/reference/assemblydebug-add-debuggableattribute) 링커 옵션으로 링크하여 자동으로 코드에 추가할 수 있습니다.

## <a name="what-debugger-features-can-i-use"></a>디버거 기능을 사용할 수 있습니까?

Visual Studio 디버거 (예: 중단점에 도달)의 전체 기능을 사용 하려면 실행 파일 정확히 일치 해야 로컬 소스 및 기호 (즉, 디버거 올바른 로드 하는 일을 할 수 있어야 [기호 파일 (.pbd)](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)). 기본적으로 디버그 빌드를이 필요합니다.

원격 디버깅 시나리오 중 하나는 소스 코드의 소스 코드의 복사본 Visual Studio에서 열려 있는 있어야 합니다. 원격 컴퓨터에서 컴파일된 응용 프로그램 이진 파일은 로컬 컴퓨터에서와 같은 build에서 가져와야 합니다.

일부 로컬 디버깅 시나리오에서 디버깅할 수 Visual Studio에서 원본에 액세스할 수 없으며 올바른 기호 파일은 앱과 함께 하는 경우 (기본적으로이 필요 디버그 빌드). 자세한 내용은 참조 하십시오. [지정 기호 및 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)합니다.

Windows 데스크톱 앱에 대 한도 (Visual Studio 열리고 오류가 발생 한 후 응용 프로그램 코드를 중단 하면) JIT 디버거를 사용 하 여 실행 중인 응용 프로그램을 디버깅할 수 있습니다.

##  <a name="a-namebkmkattachtoaprocessonaremotecomputera-attach-to-a-process-on-a-remote-computer"></a><a name="BKMK_Attach_to_a_process_on_a_remote_computer"></a> 원격 컴퓨터에서 프로세스에 연결  
 프로세스에 연결하려면 프로세스의 이름을 알아야 합니다. IIS에 배포 된 ASP.NET 응용 프로그램에 대 한 참조 [원격 IIS 컴퓨터에 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md) 또는 [IIS에 게시](https://docs.asp.net/en/latest/publishing/iis.html) ASP.NET 핵심 응용 프로그램입니다. 다른 앱은 작업 관리자에서 프로세스 이름을 찾을 수 있습니다.
  
 **프로세스에 연결** 대화 상자를 사용할 때 원격 디버깅용으로 설정된 다른 컴퓨터를 선택할 수 있습니다. 자세한 내용은 참조 [원격 디버깅](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)합니다. 원격 컴퓨터를 선택하면 해당 컴퓨터에서 실행되는 사용 가능한 프로세스의 목록을 볼 수 있고 디버깅을 위해 하나 이상의 프로세스에 연결할 수 있습니다.
  
 **원격 컴퓨터를 선택 하려면**  

1. Visual Studio에서 **디버그/프로세스에 연결**을 선택합니다.

2.  **프로세스에 연결** 대화 상자의 **전송** 목록에서 적합한 연결 형식을 선택합니다. 대부분의 경우에는**기본값** 이 올바른 설정입니다.

    **전송** 설정은 디버깅 세션에 상관없이 유지됩니다. 
  
3.  **한정자** 목록 상자를 사용하여 다음 방법 중 하나로 원격 컴퓨터 이름을 선택합니다.  
  
    1.  **한정자** 목록 상자에 이름을 입력합니다.
    
        >**참고** 경우 이후 단계에서 원격 컴퓨터 이름을 사용 하 여 연결할 수 없는, IP 주소를 사용 합니다. (포트 번호는 프로세스를 선택한 후 자동으로 표시 될 수 있습니다. 또한 수동으로 입력할 수 있습니다 것입니다. 아래 그림에 4020는 기본 포트는 원격 디버거에.)  
  
    2.  **한정자** 목록 상자 옆에 있는 드롭다운 화살표를 클릭하고 드롭다운 목록에서 컴퓨터 이름을 선택합니다.  
  
    3.  **한정자** 목록 옆에 있는**찾기** 단추를 클릭하여 **원격 디버거 연결 선택** 대화 상자를 엽니다. **원격 디버거 연결 선택** 대화 상자에는 로컬 서브넷에 있는 모든 장치와 이더넷 케이블을 통해 컴퓨터에 직접 연결된 모든 장치가 나열됩니다. 원하는 컴퓨터 또는 장치를 클릭한 다음 **선택**을 클릭합니다. 
    
    ![DBG_Basics_Attach_To_Process](../debugger/media/dbg_basics_attach_to_process.png "DBG_Basics_Attach_To_Process") 
  
     **한정자** 설정은 해당 한정자를 사용하여 디버깅 연결에 성공한 경우에만 디버깅 세션 간에 유지됩니다.
     
4.   **새로 고침**가 있어야 합니다.

      **사용 가능한 프로세스** 목록은 **프로세스** 대화 상자를 열 때 자동으로 표시됩니다. 대화 상자가 열려 있는 동안 백그라운드에서 프로세스를 시작하고 중지할 수 있습니다. 그러나 내용이 현재 상태가 아닐 수 있습니다. 언제든지 **새로 고침**을 클릭하여 목록을 새로 고치고 현재 프로세스 목록을 확인할 수 있습니다. 
     
4.  **프로세스에 연결** 대화 상자의 **사용 가능한 프로세스** 목록에서 연결할 프로그램을 찾습니다.  
  
     프로세스가 다른 사용자 계정으로 실행되고 있으면 **모든 사용자의 프로세스 표시** 확인란을 선택합니다.
     
5.  **연결**을 클릭합니다.  
  
##  <a name="a-namebkmkattachtoarunningprocessa-attach-to-a-running-process-on-the-local-machine"></a><a name="BKMK_Attach_to_a_running_process"></a> 로컬 컴퓨터에서 실행 중인 프로세스에 연결  
 프로세스에 연결하려면 프로세스의 이름을 알아야 합니다.  프로세스 이름은 작업 관리자에서 찾을 수 있습니다.  
  
1.  Visual Studio에서 **디버그/프로세스에 연결**을 선택합니다.
  
2.  **프로세스에 연결** 대화 상자의 **사용 가능한 프로세스** 목록에서 연결할 프로그램을 찾습니다.  
  
     프로세스가 다른 사용자 계정으로 실행되고 있으면 **모든 사용자의 프로세스 표시** 확인란을 선택합니다.
  
3.  **연결 대상** 상자에서 디버깅할 코드 형식이 표시되어 있는지 확인합니다. 기본 **자동** 설정은 디버깅할 코드 형식을 결정합니다. 코드 형식을 수동으로 설정하려면, 다음을 수행합니다.  
  
    1.  **연결 대상** 상자에서 **선택**을 클릭합니다.  
  
    2.  **코드 형식 선택** 대화 상자에서 **다음 코드 형식 디버깅** 을 클릭하고 디버깅할 형식을 선택합니다.  
  
    3.  **확인**을 클릭합니다.  
  
4.  **연결**을 클릭합니다.

## <a name="additional-info"></a>추가 정보

디버깅하는 동안 여러 프로그램에 연결할 수 있지만 언제든지 디버거에서 활성화되는 프로그램은 한 개뿐입니다. **디버그 위치** 도구 모음이나 **프로세스** 창에서 활성 프로그램을 설정할 수 있습니다. 자세한 내용은 [방법: 현재 프로세스 설정](http://msdn.microsoft.com/ko-kr/7e1d7fa5-0e40-44cf-8c41-d3dba31c969e)을 참조하세요.  
  
신뢰할 수 없는 사용자 계정에서 소유한 프로세스에 연결하면 보안 경고 확인 대화 상자가 나타납니다. 자세한 내용은 참조 [보안 경고: 신뢰할 수 없는 사용자가 소유한 프로세스에 연결 위험할 수 있습니다. 다음 정보가 의심 스 럽 확실 하지 않은 경우이 프로세스에 연결 하지 않는](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process.md)합니다.  
  
원격 데스크톱(터미널 서비스) 세션에서 디버그할 때 **사용 가능한 프로세스** 목록에 사용 가능한 프로세스 중 일부가 표시되지 않는 경우가 있습니다. 제한된 사용자 계정의 사용자로 Visual Studio를 실행하는 경우 서비스 및 w3wp.exe를 비롯한 다른 서버 프로세스에 사용되는 세션 0에서 실행되는 프로세스는 **사용 가능한 프로세스** 목록에 표시되지 않습니다. 관리자 계정으로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 를 실행하거나 터미널 서비스 세션 대신 서버 콘솔에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 를 실행하여 이 문제를 해결할 수 있습니다. 이러한 해결 방법을 둘 다 사용할 수 없는 경우 세 번째 방법으로 Windows 명령줄에서 `vsjitdebugger.exe -p` *ProcessId* 를 실행하여 프로세스에 연결합니다. 프로세스 ID는 tlist.exe를 사용하여 확인할 수 있습니다. tlist.exe를 얻으려면  [WDK 및 WinDbg 다운로드](http://go.microsoft.com/fwlink/?LinkId=168279)에서 Debugging Tools for Windows를 다운로드하여 설치합니다.
  
##  <a name="a-namebkmktroubleshootattacherrorsa-troubleshoot-attach-errors"></a><a name="BKMK_Troubleshoot_attach_errors"></a> 문제를 해결 연결 오류  
 실행 중인 프로세스에 디버거를 연결할 때 이 프로세스에는 한 가지 이상의 코드 형식이 포함될 수 있습니다. 디버거가 연결될 수 있는 코드 형식이 **코드 형식 선택** 대화 상자에서 표시되고 선택됩니다.  
  
 때로는 디버거가 한 코드 형식에는 연결되고 다른 코드 형식에는 연결되지 않을 수도 있습니다. 이러한 문제는 원격 컴퓨터에서 실행 중인 프로세스에 연결하려 할 때 발생할 수 있습니다. 원격 컴퓨터에 설치된 원격 디버깅 구성 요소가 일부 코드 형식만 지원하고 다른 코드 형식은 지원하지 않을 수도 있습니다. 데이터베이스를 직접 디버깅하기 위해 두 개 이상의 프로세스에 연결하려는 경우에도 이 문제가 발생할 수 있습니다. SQL 디버깅은 단일 프로세스에 대한 연결만 지원합니다.  
  
 디버거를 일부 코드 형식에 연결할 수 있지만 모든 코드 형식에 연결할 수는 없는 경우 연결할 수 없는 형식을 알려 주는 메시지가 나타납니다.  
  
 적어도 하나의 코드 형식에 디버거가 성공적으로 연결되면 프로세스 디버깅을 진행할 수 있습니다. 이 경우 성공적으로 연결된 코드 형식만 디버깅할 수 있습니다. 위 예제 메시지에서는 스크립트 코드 형식에 연결하지 못했음을 보여 줍니다. 따라서 이 프로세스 내의 스크립트 코드는 디버깅할 수 없습니다. 스크립트 코드는 프로세스 내에서 계속 실행되지만 스크립트에서 중단점을 설정하거나 데이터를 보거나 기타 디버깅 작업을 수행할 수는 없습니다.  
  
 디버거가 연결되지 않는 특정 코드 형식에만 다시 연결을 시도하면 해당 코드 형식에 디버거가 연결되지 않는 이유를 더 구체적으로 확인할 수 있습니다.  
  
 **코드 형식 연결에 실패 한 이유는 방법에 대 한 자세한 정보를 얻으려면**  
  
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