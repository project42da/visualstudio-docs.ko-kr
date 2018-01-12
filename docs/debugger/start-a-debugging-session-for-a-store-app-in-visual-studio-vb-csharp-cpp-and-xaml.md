---
title: "Visual Studio에서 UWP 앱에 대 한 디버깅 세션을 시작 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 01/04/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.IVCAppHostRemoteDebugPageObject.MachineName
- VC.Project.IVCAppHostRemoteDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostTetheredDebugPageObject.DebuggerType
- VC.Project.IVCAppHostLocalDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostRemoteDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.DebuggerType
- ImmersiveProjects.Properties.Debug
- VC.Project.IVCAppHostTetheredDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostLocalDebugPageObject.AllowLocalNetworkLoopback
- AppPackage.Properties.Debug
- VC.Project.IVCAppHostRemoteDebugPageObject.Authentication
- VC.Project.IVCAppHostRemoteDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.BreakpointBehavior
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 66ec0e79-8261-4c19-a618-3fd1b3f71bbd
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 367fc334d0268a73e8ad1a33ebdc6e74036ddc86
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="start-a-debugging-session-for-a-uwp-app-in-visual-studio"></a>Visual Studio에서 UWP 앱에 대 한 디버깅 세션을 시작 합니다.
  
 이 항목에서는 XAML 및 Visual c + +, Visual C# 또는 Visual Basic로 작성 된 UWP 앱 및 HTML 및 JavaScript로 작성 된 UWP 앱에 대 한 디버깅 세션을 시작 하는 방법에 설명 합니다. 응용 프로그램 디버깅에는 디버깅 세션 구성과 응용 프로그램 시작 방법 선택이 모두 포함됩니다.  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a> 디버깅을 쉽게 시작하는 방법  
  
1.  Visual Studio에서 응용 프로그램 솔루션을 엽니다.  
  
2.  F5 키를 선택 합니다.  
  
 Visual Studio가 디버거가 연결된 응용 프로그램을 빌드하고 시작합니다. 중단점에 도달하거나 수동으로 실행을 일시 중단하거나 처리되지 않은 예외가 발생하거나 응용 프로그램이 끝날 때까지 계속해서 실행됩니다.  
  
##  <a name="BKMK_Choose_the_build_configuration_options"></a> 빌드 구성 옵션 선택  
  
1.   옆에 있는 드롭다운 목록에서 **디버깅 시작** 디버거 단추 **표준** 도구 모음 선택 **디버그**합니다.  
  
2.  **플랫폼** 목록에서 빌드할 대상 플랫폼을 선택합니다.  
  
##  <a name="BKMK_Choose_the_deployment_target"></a> 배포 대상 선택  
  
배포 하 고 Visual Studio 컴퓨터, 연결된 된 장치, 로컬 컴퓨터, 원격 장치 또는 에뮬레이터에서 Visual Studio 시뮬레이터에서 UWP 앱을 디버그할 수 있습니다. 오른쪽에 있는 드롭 다운 목록에서 배포 대상을 선택 된 **플랫폼** 디버거 대상 **표준** 도구 모음입니다.
  
![배포 대상 선택](../debugger/media/vsrun_select_target_device.png)  
  
다음 옵션 중 하나를 선택합니다.  
  
|||  
|-|-|  
|**로컬 컴퓨터**|로컬 컴퓨터의 현재 세션에서 응용 프로그램을 디버깅합니다.|  
|**시뮬레이터**|Visual Studio 시뮬레이터에서 앱을 UWP에 대 한 디버깅 및 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 앱. 시뮬레이터는 장치 기능을 디버깅할 수 있도록 하는 데스크톱 창-터치 제스처 및 장치 회전과 같은-로컬 컴퓨터에서 사용할 수 없습니다. 이 옵션은 사용할 수만 하는 경우 앱의 **대상 플랫폼 최소 합니다. 버전** 하려면 개발 컴퓨터에 운영 체제 보다 이전입니다. 참조 [시뮬레이터에서 실행 하는 UWP 앱](../debugger/run-windows-store-apps-in-the-simulator.md)합니다.|  
|**원격 컴퓨터**|인트라넷을 통해 로컬 컴퓨터에 연결되거나 이더넷 케이블을 사용하여 직접 연결된 장치에서 응용 프로그램을 디버깅합니다. 원격으로 디버깅 하려면 Visual Studio 용 원격 도구에 원격 장치에 설치 및 실행 해야 합니다. 참조 [원격 컴퓨터에서 실행 하는 UWP 앱](../debugger/run-windows-store-apps-on-a-remote-machine.md)합니다.|  
|**장치**|USB로 연결 된 장치에 응용 프로그램을 디버깅 합니다. 장치가 개발자 잠금 해제 하 고 화면을 잠금 해제 해야 합니다.|  
|**모바일 에뮬레이터**|에뮬레이터에 지정 된 구성을 사용 하 여 에뮬레이터를 부팅, 앱을 배포 하 고 디버깅을 시작 합니다. 에뮬레이터는 Windows 8.1 이상을 실행 하는 Hyper-v 사용 컴퓨터에서 사용할 수만 있습니다.|  

##  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a>추가 디버깅 옵션을 선택 합니다.  

추가 디버깅 옵션을 구성 해야 할 경우에 프로젝트에 대 한 속성 페이지를 엽니다.
  
1.  솔루션 탐색기에서 프로젝트를 선택합니다. 바로 가기 메뉴에서 **속성**을 선택합니다.  
  
2.  프로젝트에 대 한 디버그 속성 페이지를 열려면이 작업을 수행 합니다.  
  
    -   Visual C# 및 Visual Basic 응용 프로그램의 경우 **디버그**를 선택합니다.  
  
         ![&#35; &#47; VB 프로젝트 디버그 속성 페이지](../debugger/media/dbg_csvb_debugpropertypage.png)  
  
    -   Visual c + + 및 JavaScript 앱에 대 한 확장 된 **구성 속성** 노드를 선택한 후 **디버깅**합니다.  
  
         ![C# 43; &#43; UWP 앱 디버깅 속성 페이지](../debugger/media/dbg_cpp_debugpropertypage.png)  

###  <a name="BKMK_Choose_the_debugger_to_use"></a> 사용할 디버거 선택  
기본적으로 Visual Studio는 C# 및 Visual Basic 응용 프로그램에서 관리 코드를 디버깅합니다. C# 및 Visual Basic 응용 프로그램의 경우 응용 프로그램에서 관리 코드 및 네이티브 C/C++ 코드를 디버깅하도록 선택할 수 있습니다. C + + 앱의 Visual Studio는 기본적으로 네이티브 코드를 디버깅합니다. JavaScript 앱에서 Visual Studio는 기본적으로 스크립트를 디버깅 합니다. 
  
C + + 앱과 JavaScript에 대 한 위치 대신 또는 네이티브 코드 뿐 아니라 응용 프로그램의 구성 요소에 있는 특정 형식의 코드를 디버깅 하도록 선택할 수 있습니다. 응용 프로그램 프로젝트의 **디버깅** 속성 페이지에 있는 **디버거 형식** 목록에서 디버깅할 코드를 지정합니다.  
  
**응용 프로그램 프로세스** 목록에서 아래 디버거 중 하나를 선택합니다.  
  
|||  
|-|-|  
|**관리 전용**|응용 프로그램에서 관리 코드를 디버깅합니다. JavaScript 코드와 네이티브 C/C++ 코드는 무시됩니다.|  
|**네이티브 전용**|응용 프로그램에서 네이티브 C/C++ 코드를 디버깅합니다. 관리 코드와 JavaScript 코드는 무시됩니다.|  
|**혼합(관리/네이티브)**|응용 프로그램에서 네이티브 C/C++ 코드 및 관리 코드를 디버깅합니다. JavaScript 코드는 무시됩니다. C + + 프로젝트에서이 옵션을 라고 **(관리 / 네이티브)**합니다.|  
|**스크립트만**|응용 프로그램에서 JavaScript 코드를 디버깅합니다. 관리 코드와 네이티브 코드는 무시됩니다.|  
|**네이티브 및 스크립트**|네이티브 C/c + + 코드와 응용 프로그램에서 JavaScript 코드를 디버깅 합니다. 관리 되는 코드는 무시 됩니다. C + + 프로젝트에만 사용할 수 있습니다.|  
|**GPU 전용 (c + + AMP)**|GPU(그래픽 처리 장치)에서 실행되는 네이티브 C++ 코드를 디버깅합니다. C + + 프로젝트에만 사용할 수 있습니다.|  

C# 및 Visual Basic 응용 프로그램에서 설정할 수도 있습니다 동일한 **디버거 형식** 프로젝트의 일부인 모든 백그라운드 작업에 대 한 값입니다.
  
###  <a name="BKMK__Optional__Delay_starting_the_debug_session"></a> (선택 사항) 디버그 세션 시작 지연  
 기본적으로 디버깅을 시작하면 바로 응용 프로그램이 시작됩니다. 디버그 세션을 시작하되 응용 프로그램 시작을 지연할 수도 있습니다. 이 옵션을 선택하는 경우 시작 화면 또는 활성화 계약을 통해 응용 프로그램이 시작되거나 다른 프로세스 또는 메서드를 통해 응용 프로그램이 시작되면 디버거에서 응용 프로그램이 시작됩니다. 응용 프로그램 자체가 실행되지 않는 경우 백그라운드 작업을 디버깅하려면 응용 프로그램의 시작을 지연할 수도 있습니다.  
  
 다음 작업을 통해 응용 프로그램 시작을 지연할 수 있습니다.  
  
-   Visual C# 및 Visual Basic 응용 프로그램의 경우 **디버그** 속성 페이지에서 **시작하지 않음(시작 시 코드 디버그)** 을 선택합니다.  
  
-   Visual c + + 및 JavaScript 앱에 대 한 선택 **예** 에서 **응용 프로그램 시작** 목록에 **디버깅** 속성 페이지.  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a> (선택 사항) 네트워크 루프백 비활성화  
  
 보안상의 이유로 일반적인 방식으로 설치 된 UWP 앱은에 설치 된 장치에 대 한 네트워크 호출을 수행할 수 없습니다. 기본적으로 Visual Studio를 배포하면 배포된 응용 프로그램에 대한 이 규칙의 예외가 만들어 집니다. 이 예외로 인해 사용자는 단일 컴퓨터에서 통신 프로시저를 테스트할 수 있습니다. Microsoft 스토어에 앱을 제출 하기 전에 예외 없이 앱을 테스트 해야 합니다.  
  
 네트워크 루프백 예외를 제거하려면  
  
-   Visual C# 및 Visual Basic 응용 프로그램의 선택을 취소는 **로컬 네트워크 루프백 허용** 확인란은 **디버그** 속성 페이지.  
  
-   Visual c + + 및 JavaScript 앱에 대 한 선택 **아니요** 에서 **로컬 네트워크 루프백 허용** 목록에 **디버깅** 속성 페이지.  
  
###  <a name="BKMK__Optional__Reinstall_the_app_when_you_start_debugging"></a> (선택 사항) 디버깅을 시작할 때 응용 프로그램 다시 설치  
 Visual C# 또는 Visual Basic 응용 프로그램의 설치 및 초기 구성에서 문제를 진단하려면 **디버그** 속성 페이지에서 **패키지 제거 후 다시 설치**  를 선택하여 디버깅을 시작할 때 원래 설치를 다시 만듭니다. 이 옵션은 Visual c + + 및 JavaScript 프로젝트에 사용할 수 없습니다.  
  
###  <a name="BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger"></a> (선택 사항) 원격 디버거 시작을 위한 인증 요구 비활성화  
  
 기본적으로 선택 하면 원격 디버거를 실행 하려면 자격 증명이 제공 해야 **원격 컴퓨터** 배포 대상으로 합니다.
  
> [!IMPORTANT]
>  인증 안 함 원격 디버거를 실행 하도록 선택할 수 있지만이 모드 것이 좋습니다. 이 모드에서 실행할 때는 네트워크 보안이 없습니다. 네트워크를 악의적인 코드 또는 유해 트래픽이 위험에 노출 되지 않는 경우에 인증 안 함을 선택 합니다.  
  
 인증 요구를 제거하려면  
  
1.  Visual C# 및 Visual Basic 응용 프로그램에 대 한 선택 **원격 컴퓨터** 로 **대상 장치** 에 **디버그** 속성 페이지를 제거한 다음 설정 **인증 모드**  를 **None** 또는 **유니버설 (암호화 되지 않은 프로토콜)**합니다.
  
2.  Visual c + + 및 JavaScript 앱에 대 한 선택 **원격 컴퓨터** 로 **대상 장치** 에 **디버깅** 속성 페이지를 제거한 다음 설정 **필요 인증** 를 **None** 또는 **유니버설 (암호화 되지 않은 프로토콜)**합니다.  

    **유니버설 (암호화 되지 않은 프로토콜)** 원격 장치에 배포할 때 사용 하기 위한 것입니다. 현재이 IoT 장치, Xbox 장치 및 HoloLens 장치 뿐만 아니라 작성자가 업데이트 또는 최신 Pc입니다. 유니버설 (암호화 되지 않은 프로토콜)는 신뢰할 수 있는 네트워크만 사용 해야 합니다. 디버깅 연결이 악의적인 사용자가 가로채 고 개발 및 원격 컴퓨터 사이 전달 되는 데이터를 변경할 수에 취약 합니다.  
  
##  <a name="BKMK_Start_the_debugging_session"></a> 디버깅 세션을 시작합니다.  
  
###  <a name="BKMK_Start_debugging__F5_"></a> 디버깅 시작(F5)  
 선택 하는 경우 **디버깅 시작** (키보드: F5)에 **디버그** 메뉴에서 Visual Studio는 디버거가 연결 된 앱을 시작 합니다. 중단점에 도달하거나 수동으로 실행을 일시 중단하거나 예외가 발생하거나 응용 프로그램이 끝날 때까지 계속해서 실행됩니다.  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a> 디버깅을 시작하되F5) 응용 프로그램 시작 지연  
 디버그 모드에서 실행되도록 응용 프로그램을 설정할 수 있지만 디버거가 아닌 방법으로 응용 프로그램을 시작할 수 있습니다. 예를 들어 시작 메뉴에서 응용 프로그램 시작을 디버깅 하거나 응용 프로그램을 시작 하지 않고 앱에서 백그라운드 프로세스를 디버깅 하려면 원하는 수 있습니다. 앱 시작을 지연 하려면이 수행 합니다.  
  
-   에 **디버그** 응용 프로그램의 속성 페이지 (**디버깅** Visual c + + 및 JavaScript)  
  
    -   Visual C# 및 Visual Basic 응용 프로그램의 경우 **시작하지 않음(시작 시 코드 디버그)**을 선택합니다.  
  
    -   Visual c + + 및 JavaScript 앱에 대 한 선택 **예** 에서 **응용 프로그램 시작** 목록입니다.  
  
-   선택 **디버깅 시작** 에 **디버그** 메뉴 (키보드: F5).  
  
-   시작 메뉴, 실행 계약 또는 다른 프로시저를 통해 응용 프로그램을 시작합니다.  
  
 디버그 모드에서 응용 프로그램이 시작됩니다. 중단점에 도달하거나 수동으로 실행을 일시 중단하거나 처리되지 않은 예외가 발생하거나 응용 프로그램이 끝날 때까지 계속해서 실행됩니다.  
  
 이어야 합니다. 백그라운드 작업 디버깅에 대 한 자세한 내용은 참조 [트리거 일시 중단, 다시 시작 및 백그라운드 이벤트를 UWP 앱 용)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)합니다.  
  
###  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a> 디버거에서 설치된 응용 프로그램 시작  
F5 키를 사용하여 디버깅을 시작할 때 Visual Studio에서는 응용 프로그램을 빌드 및 배포하고 디버그 모드에서 실행되도록 응용 프로그램을 설정한 다음 응용 프로그램을 시작합니다. 장치에 이미 설치 되어 있는 앱을 시작 하려면 사용 된 **설치 된 응용 프로그램 패키지 디버그** 대화 상자. 이 절차의 소스 파일은 앱의 경우 하지만 응용 프로그램에 대 한 Visual Studio 프로젝트를 포함 하지 않는 또는 Microsoft 스토어에서 설치 된 응용 프로그램 디버깅을 할 때 유용 합니다. 예를 들어 Visual Studio 프로젝트 또는 솔루션을 사용하지 않는 사용자 지정 빌드 시스템이 있을 수 있습니다.  
  
응용 프로그램은 로컬 장치에 설치되거나 원격 장치에 있을 수 있습니다.  응용 프로그램을 즉시 시작하거나 시작 메뉴나 활성화 계약 등의 다른 프로세스나 방법으로 시작될 때 디버거에서 실행되도록 응용 프로그램을 설정할 수 있습니다. 응용 프로그램을 시작하지 않고 백그라운드 프로세스를 디버깅하려는 경우에도 디버그 모드에서 실행되도록 응용 프로그램을 설정할 수 있습니다. 자세한 내용은 참조 [트리거 일시 중단, 다시 시작 및 백그라운드 이벤트를 UWP 앱 용)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)합니다.  
  
디버거에서 설치 된 응용 프로그램을 시작 하려면 선택 **디버그**, 다음 **기타 디버그 대상**, 차례로 **설치 된 응용 프로그램 패키지 디버그**합니다. 자세한 내용은 참조 하십시오. [설치 된 응용 프로그램 패키지 디버그](../debugger/debug-installed-app-package.md)합니다.

> [!NOTE]
> Windows 8.1 대 한 선택 **디버그**를 선택한 후 **설치 된 응용 프로그램 패키지 디버그**합니다.

###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a>실행 중인 UWP 앱에 디버거 연결  

실행 중인 UWP 앱을 디버깅 하려면 선택 **디버그**, 다음 **기타 디버그 대상**, 차례로 **설치 된 응용 프로그램 패키지 디버그**합니다. 자세한 내용은 참조 하십시오. [설치 된 응용 프로그램 패키지 디버그](../debugger/debug-installed-app-package.md)합니다.
  
###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a>실행 중인 Windows 8.x 앱에 디버거 연결
 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 응용 프로그램에 디버거를 연결하려면 디버깅 가능 패키지 관리자를 사용하여 응용 프로그램이 디버그 모드에서 실행되도록 설정합니다. 디버깅 가능 패키지 관리자 Visual Studio 원격 도구가 설치 되어 있습니다.  
  
 응용 프로그램에 디버거를 연결하는 기능은 [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]에서 설치된 응용 프로그램과 같은 이미 설치된 응용 프로그램을 디버깅해야 하는 경우 유용합니다. 응용 프로그램의 소스 파일은 있지만 응용 프로그램에 대한 Visual Studio 프로젝트가 없는 경우 연결해야 합니다. 예를 들어 Visual Studio 프로젝트 또는 솔루션을 사용하지 않는 사용자 지정 빌드 시스템이 있을 수 있습니다.  
  
 응용 프로그램에 디버거를 연결하려면 아래와 같은 단계를 수행해야 합니다.  
  
1.  응용 프로그램이 디버그 모드에서 실행되도록 설정합니다. 이 작업은 응용 프로그램이 실행되고 있지 않을 때 수행해야 합니다.  
  
2.  응용 프로그램을 시작합니다. 시작 화면, 실행 계약 또는 다른 메서드를 통해 응용 프로그램을 시작할 수 있습니다.  
  
3.  실행 중인 응용 프로그램에 디버거 연결합니다.  
  
####  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a> 응용 프로그램이 디버그 모드에서 실행되도록 설정  
  
1.  앱을 설치 하는 장치에 Visual Studio 용 원격 도구를 설치 합니다. 참조 [원격 도구 설치](../debugger/remote-debugging.md)합니다.  
  
2.  시작 화면에서 `Debuggable Package Manager` 를 검색한 다음 시작합니다.  
  
     AppxDebug cmdlet에 맞게 올바르게 구성된 PowerShell 창이 나타납니다.  
  
3.  응용 프로그램의 디버깅을 사용하도록 설정하려면 응용 프로그램의 PackageFullName 식별자를 지정해야 합니다. PackageFullName이 포함되어 있는 모든 응용 프로그램의 목록을 보려면 PowerShell 프롬프트에서 `Get-AppxPackage` 를 입력합니다.  
  
4.  PowerShell 프롬프트에서 `Enable-AppxDebug` *PackageFullName* 을 입력합니다. 여기서 *PackageFullName* 은 앱의 PackageFullName 식별자입니다.  
  
####  <a name="BKMK_Attach_the_debugger"></a> 디버거 연결  
 디버거를 연결하려면 다음을 수행합니다.  
  
1.  **디버그** 메뉴에서 **프로세스에 연결**을 선택합니다.  
  
     **프로세스에 연결** 대화 상자가 나타납니다.  
  
2.  원격 장치의 응용 프로그램에 연결하려면 **한정자** 상자에 원격 장치를 지정합니다. 다음과 같은 작업을 수행할 수 있습니다.  
  
    -   **한정자** 상자에 이름을 입력합니다.  
  
    -   **한정자** 상자에서 아래쪽 화살표를 선택한 다음 앞에서 연결한 장치의 목록에서 장치를 선택합니다.  
  
    -   **찾기** 를 선택하여 로컬 서브넷의 장치 목록에서 장치를 선택합니다.  
  
3.  **연결 대상** 상자에서 디버깅할 코드의 형식을 지정합니다.  
  
     **선택** 을 선택한 후 다음 중 하나를 수행합니다.  
  
    -   **디버깅할 코드 형식을 자동으로 결정**을 선택합니다.  
  
    -   **다음 코드 형식 디버깅** 을 선택한 다음 목록에서 하나 이상의 형식을 선택합니다.  
  
4.  **사용 가능한 프로세스**  목록에서 응용 프로그램 프로세스를 선택합니다.  

    > [!NOTE]
    >  다른 응용 프로그램 종류와 달리 JavaScript 앱은 wwahost.exe 프로세스의 인스턴스에서 실행 됩니다. 앱에 연결할 때 다른 JavaScript 앱이 실행 중인 경우 해당 앱이 실행 중인 wwahost.exe의 숫자 PID(프로세스 ID)를 알아야 합니다.  
    >   
    >  이러한 상황을 처리하는 가장 쉬운 방법은 다른 JavaScript 앱을 모두 닫는 것입니다. 그렇지 않으면 앱을 시작하기 전에 Windows 작업 관리자를 열고 wwahost.exe 프로세스의 ID를 메모해 두면 됩니다. 연결할 프로세스를 지정 하는 경우는 **사용 가능한 프로세스** 대화 상자에서 앱의 wwahost.exe id는 기록한 것과 다른 id를 해야 합니다.  
  
5.  **연결**을 선택합니다.  
  
 프로세스에 디버거가 연결됩니다. 중단점에 도달하거나 수동으로 실행을 일시 중단하거나 처리되지 않은 예외가 발생하거나 응용 프로그램이 끝날 때까지 계속해서 실행됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 앱 디버깅](../debugger/debug-store-apps-in-visual-studio.md)   