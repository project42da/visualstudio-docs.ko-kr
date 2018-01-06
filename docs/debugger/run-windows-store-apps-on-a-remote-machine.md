---
title: "UWP 앱을 원격 컴퓨터에서 실행 | Microsoft Docs"
ms.custom: 
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 0f6814d6-cd0d-49f3-b501-dea8c094b8ef
caps.latest.revision: "43"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: ebae0886db71b0b06f346d6bd174951b1c5d4752
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="run-uwp-apps-on-a-remote-machine"></a>UWP 앱을 원격 컴퓨터에서 실행
![Windows에만 적용](../debugger/media/windows_only_content.png "windows_only_content")  
  
UWP 앱에서 원격 컴퓨터를 실행 하려면 Visual Studio 원격 도구를 사용 하 여 연결 해야 합니다. 원격 도구를 사용 하 여 실행, 디버깅, 프로 파일링 및 Visual Studio를 실행 하는 다른 컴퓨터에서 한 장치에서 실행 되는 UWP 앱을 테스트할 수 있습니다. 원격 장치에서 실행 되는 Visual Studio 컴퓨터에서 터치, 지리적 위치 및 실제 방향 등의 UWP 앱에 관련 된 기능을 지원 하지 않을 때 특히 효과적일 수 있습니다. 이 항목에서는 원격 세션을 구성하고 시작하는 절차에 대해 설명합니다.

일부 시나리오에서는 원격 장치에 배포할 때에 자동으로 원격 도구 설치 됩니다.

- 업데이트 작성자 및 이상 버전을 실행 중인 Windows 10 Pc를 참조 하십시오. [설치 된 응용 프로그램 패키지 디버그](debug-installed-app-package.md#remote)합니다. 원격 도구는 자동으로 설치 됩니다.
- Windows 10 Xbox, IOT 및 HoloLens 장치에 대 한 참조 [설치 된 응용 프로그램 패키지 디버그](debug-installed-app-package.md#remote)합니다. 원격 도구는 자동으로 설치 됩니다.
- Windows Phone 대 한 phone에 물리적으로 연결 해야, 설치 하거나 해야는 [개발자 라이선스가](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh974578.aspx) (Windows Phone 8 및 8.1) 또는 사용 [개발자 모드](/windows/uwp/get-started/enable-your-device-for-development) (Windows Mobile 10)을 수행 해야 하 고 선택 **장치** 디버그 대상으로 합니다. 원격 도구 필요 하거나 지원 하지 합니다.

Windows 8.1 Pc 및 Windows 10 Pc의 Windows 사전-작성자의 업데이트 버전을 실행 하면 수동으로 설치 해야 원격 도구 원격 컴퓨터에 디버그할 수 있습니다. 이 항목의 지침을 따릅니다.
  
##  <a name="BKMK_Prerequisites"></a> 필수 구성 요소  
 원격 장치에서 디버깅하려면  
  
-   원격 장치와 Visual Studio 컴퓨터는 네트워크를 통해 연결되거나 이더넷 케이블을 통해 직접 연결되어야 합니다. 인터넷을 통한 디버깅은 지원되지 않습니다.  

- 원격 장치 개발을 위한 사용 되어야 합니다.

    - Windows 8 및 Windows 8.1 장치에 대 한 한 [개발자 라이선스가](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh974578.aspx) 원격 장치에 설치 해야 합니다.
    - Windows 10 장치를 설정 해야 [개발자 모드](/windows/uwp/get-started/enable-your-device-for-development)합니다. 
  
-   Windows 10 작성자의 업데이트 보다 이전 버전의 Windows 10을 실행 중인 Windows 10 Pc에 대 한 설치 하 고 원격 디버깅 구성 요소를 실행 해야 합니다.
  
-   원격 장치의 관리자만 설치하는 동안 방화벽을 구성할 수 있습니다. 원격 장치에 대한 사용자 액세스 권한이 있어야만 원격 디버거를 실행하거나 원격 디버거에 연결할 수 있습니다.  
  
##  <a name="BKMK_Security"></a> 보안  
 기본적으로 원격 디버거는 Windows 인증을 사용합니다.  
  
> [!WARNING]
>  원격 디버거를 인증 안 함 모드에서 실행할 수도 있지만 이 모드는 사용하지 않는 것이 좋습니다. 이 모드에서 실행할 때는 네트워크 보안이 없습니다. 네트워크에 악의적인 트래픽이나 유해 트래픽 위험이 확실히 없는 경우에만 인증 안 함 모드를 선택하십시오.  
  
##  <a name="BKMK_DirectConnect"></a> 원격 장치에 직접 연결하는 방법  
 원격 장치에 직접 연결하려면 Visual Studio 컴퓨터를 표준 이더넷 케이블로 장치에 연결합니다. 장치에 이더넷 포트가 없는 경우에는 이더넷 어댑터에 USB를 사용하여 케이블에 연결할 수 있습니다.  
  
## <a name="BKMK_download"></a>원격 도구 다운로드 및 설치

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
## <a name="BKMK_setup"></a>원격 디버거 설정

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]
  
##  <a name="BKMK_ConnectVS"></a> 원격 디버깅을 위해 Visual Studio 프로젝트 구성  
 프로젝트 속성에서 연결할 원격 장치를 지정합니다. 절차는 프로그래밍 언어에 따라 다릅니다. 원격 장치의 네트워크 이름을 입력하거나 원격 디버거 연결 선택 대화 상자에서 해당 이름을 선택할 수 있습니다.  
  
 ![원격 디버거 연결 대화 상자 선택](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
 이 대화 상자에는 Visual Studio 컴퓨터의 로컬 서브넷에 있으며 원격 디버거를 실행 중인 장치만 나열됩니다.  
  
> [!TIP]
>  원격 장치에 연결하는 데 문제가 있을 경우 장치의 IP 주소를 입력해 보십시오. 장치의 IP 주소를 확인하려면 명령 창을 연 다음 **ipconfig**를 입력합니다. 그러면 IP 주소가 **IPv4 Address**로 나열됩니다.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_C__and_Visual_Basic_projects"></a> C# 및 Visual Basic 프로젝트에 사용할 원격 장치 선택  
 ![원격 디버깅에 대 한 프로젝트 속성을 관리 되는](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
1.  솔루션 탐색기에서 프로젝트 이름을 선택한 다음 바로 가기 메뉴에서 **속성** 을 선택합니다.  
  
2.  **디버그**를 선택합니다.  
  
3.  **대상 장치** 목록에서 **원격 컴퓨터** 를 선택합니다.  
  
4.  **원격 컴퓨터** 상자에 원격 장치의 네트워크 이름을 입력하거나 **찾기** 를 선택하여 **원격 디버거 연결 선택** 대화 상자에서 장치를 선택합니다.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_JavaScript_and_C___projects"></a> JavaScript 및 C++ 프로젝트에 사용할 원격 장치 선택  
 ![C# 43; &#43; 원격 디버깅에 대 한 속성을 프로젝트](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")  
  
1.  솔루션 탐색기에서 프로젝트 이름을 선택한 다음 바로 가기 메뉴에서 **속성** 을 선택합니다.  
  
2.  **구성 속성** 노드를 확장한 다음 **디버깅**을 선택합니다.  
  
3.  **실행할 디버거** 목록에서 **원격 디버거** 를 선택합니다.  
  
4.  **컴퓨터 이름** 상자에 원격 장치의 네트워크 이름을 입력하거나 해당 상자에서 아래쪽 화살표를 선택하여 **원격 디버거 연결 선택** 대화 상자에서 장치를 선택합니다.  
  
##  <a name="BKMK_RunRemoteDebug"></a> 원격 디버깅 세션 실행  
 로컬 세션의 경우와 같은 방법으로 원격 디버그 세션을 시작, 중지, 탐색할 수 있습니다. 디버깅을 시작하기 전에 원격 장치에서 원격 디버깅 모니터가 실행되고 있는지 확인합니다.  
  
 그런 다음 **디버그** 메뉴에서 **디버깅 시작** 을 선택합니다(키보드: F5). 프로젝트가 다시 컴파일된 다음 원격 장치에 배포되어 시작됩니다. 디버거는 중단점에서 실행을 일시 중단하며 사용자는 한 단계씩 코드를 실행하거나, 프로시저 단위로 실행하거나 코드를 종료하여 한 번에 한 줄씩 실행할 수 있습니다. **디버깅 중지** 를 선택하여 디버그 세션을 끝내고 원격 응용 프로그램을 종료할 수 있습니다. 자세한 내용은 참조 [Visual Studio에서 앱 디버깅](../debugger/debug-store-apps-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio로 UWP 앱 테스트](../test/testing-store-apps-with-visual-studio.md)   
 [Visual Studio에서 앱 디버깅](../debugger/debug-store-apps-in-visual-studio.md)