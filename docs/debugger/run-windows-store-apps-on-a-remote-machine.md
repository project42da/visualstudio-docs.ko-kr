---
title: "UWP 앱을 원격 컴퓨터에서 실행 | Microsoft Docs"
ms.custom: 
ms.date: 01/05/2018
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
ms.openlocfilehash: f9d538cbc650de2d704c885a8eff6a897c9ef68e
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="run-uwp-apps-on-a-remote-machine-in-visual-studio"></a>Visual Studio에서 원격 컴퓨터 UWP 앱 실행
  
UWP 앱에서 원격 컴퓨터를 실행 하려면 Visual Studio 용 원격 도구를 사용 하 여 연결 해야 합니다. 원격 도구를 사용 하 여 실행, 디버깅, 프로 파일링 및 Visual Studio를 실행 하는 다른 컴퓨터에서 한 장치에서 실행 되는 UWP 앱을 테스트할 수 있습니다. 원격 장치에서 실행 되는 Visual Studio 컴퓨터에서 터치, 지리적 위치 및 실제 방향 등의 UWP 앱에 관련 된 기능을 지원 하지 않을 때 특히 효과적일 수 있습니다. 이 항목에서는 원격 세션을 구성하고 시작하는 절차에 대해 설명합니다.

일부 시나리오에서는 원격 장치에 배포할 때에 자동으로 원격 도구 설치 됩니다.

- Windows 10 Pc 작성자 업데이트 및 이상 버전을 실행, 용 원격 도구를 자동으로 설치 됩니다.
- Windows 10 Xbox, IOT 및 HoloLens 장치에 대 한 원격 도구를 자동으로 설치 됩니다.
- Windows 10 Mobile phone에 물리적으로 연결 해야, 사용 하도록 설정 해야 [개발자 모드](/windows/uwp/get-started/enable-your-device-for-development) 선택 해야 **장치** 디버그 대상으로 합니다. 원격 도구 필요 하거나 지원 하지 합니다.

Windows 10 Pc의 Windows 사전-작성자의 업데이트 버전을 실행 합니다 설치 해야 원격 도구 원격 컴퓨터에 수동으로 디버그할 수 있습니다. 이 항목의 지침을 따릅니다. 
  
##  <a name="BKMK_Prerequisites"></a> 필수 구성 요소  
 원격 장치에서 디버깅하려면  
  
- 원격 장치와 Visual Studio 컴퓨터를 네트워크를 통해 연결 하거나 USB 또는 이더넷 케이블을 통해 직접 연결 해야 합니다. 인터넷을 통한 디버깅은 지원되지 않습니다.  

- 사용 하도록 설정 해야 [개발자 모드](/windows/uwp/get-started/enable-your-device-for-development)합니다. 
  
- Windows 10 Pc를 Windows 10 작성자의 업데이트 보다 이전 버전의 Windows 10 실행을 사용 해야 [설치 하 고 원격 디버깅 구성 요소 실행](#BKMK_download)합니다.
  
##  <a name="BKMK_Security"></a> 보안  
기본적으로 **유니버설 (암호화 되지 않은 프로토콜)** Windows 10에서 사용 됩니다. 이 프로토콜은 신뢰할 수 있는 네트워크만 사용 해야 합니다. 디버깅 연결이 악의적인 사용자가 가로채 고 개발 및 원격 컴퓨터 사이 전달 되는 데이터를 변경할 수에 취약 합니다.
  
> [!WARNING]
>  인증 모드를 설정 하면 네트워크 보안이 없습니다 없는 **유니버설 (암호화 되지 않은 프로토콜)** 또는 **None**합니다. 네트워크를 악의적인 트래픽이나 유해 트래픽에서 위험이 없는 경우에 이러한 모드를 선택 합니다.  
  
##  <a name="BKMK_DirectConnect"></a>USB 케이블을 사용 하 여 직접 연결 하는 방법 

Windows 10에서 배포할 수 있습니다는 USB로 연결 된 장치를 선택 하 여 **장치** 대신 **원격 컴퓨터** 배포 대상으로 (에서 수행할 수 있습니다는 **표준** 도구 모음 또는 디버깅 속성 페이지에서).

##  <a name="BKMK_ConnectVS"></a>원격 디버깅을 위해 Visual Studio 프로젝트 구성  
 프로젝트 속성에서 연결할 원격 장치를 지정합니다. 절차는 프로그래밍 언어에 따라 다릅니다. 원격 장치의 네트워크 이름을 입력 하거나에서 선택할 수는 **원격 연결** 대화 상자.  
  
 ![원격 디버거 연결 대화 상자 선택](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
 이 대화 상자에는 Visual Studio 컴퓨터의 로컬 서브넷에 있으며 원격 디버거를 실행 중인 장치만 나열됩니다.  
  
> [!TIP]
>  원격 장치에 연결하는 데 문제가 있을 경우 장치의 IP 주소를 입력해 보십시오. 장치의 IP 주소를 확인하려면 명령 창을 연 다음 **ipconfig**를 입력합니다. 그러면 IP 주소가 **IPv4 Address**로 나열됩니다.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_C__and_Visual_Basic_projects"></a>C# 및 Visual Basic 프로젝트에 사용할 원격 장치 선택  
  
1.  솔루션 탐색기에서 프로젝트 이름을 선택한 다음 바로 가기 메뉴에서 **속성** 을 선택합니다.  
  
2.  **디버그**를 선택합니다.  
  
3.  **대상 장치** 목록에서 **원격 컴퓨터** 를 선택합니다.  
  
4.  **원격 컴퓨터** 상자에 원격 장치의 네트워크 이름을 입력하거나 **찾기** 를 선택하여 **원격 디버거 연결 선택** 대화 상자에서 장치를 선택합니다. 

    ![원격 디버깅에 대 한 프로젝트 속성을 관리 되는](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
###  <a name="BKMK_Choosing_the_remote_device_for_JavaScript_and_C___projects"></a>JavaScript 및 c + + 프로젝트에 사용할 원격 장치 선택  
  
1.  솔루션 탐색기에서 프로젝트 이름을 선택한 다음 바로 가기 메뉴에서 **속성** 을 선택합니다.  
  
2.  **구성 속성** 노드를 확장한 다음 **디버깅**을 선택합니다.  
  
3.  **실행할 디버거** 목록에서 **원격 디버거** 를 선택합니다.  
  
4.  **컴퓨터 이름** 상자에 원격 장치의 네트워크 이름을 입력하거나 해당 상자에서 아래쪽 화살표를 선택하여 **원격 디버거 연결 선택** 대화 상자에서 장치를 선택합니다.  

    ![C# 43; &#43; 원격 디버깅에 대 한 속성을 프로젝트](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")
  
## <a name="BKMK_download"></a>원격 도구 다운로드 및 설치 (사전 작성자 업데이트)

이전 작성자의 업데이트 버전의 Windows 10을 사용 하는 경우 이러한 지침을 따릅니다. 그렇지 않으면이 섹션을 건너뛸 수 있습니다.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a>원격 디버거 설정

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]  
  
##  <a name="BKMK_RunRemoteDebug"></a>원격 디버깅 세션 시작  
 로컬 세션의 경우와 같은 방법으로 원격 디버그 세션을 시작, 중지, 탐색할 수 있습니다. Pre-작성자의 업데이트 버전의 Windows 10에서 원격 장치에서 원격 디버깅 모니터가 실행 되 고 있는지 확인 합니다.  
  
 그런 다음 **디버그** 메뉴에서 **디버깅 시작** 을 선택합니다(키보드: F5). 프로젝트가 다시 컴파일된 다음 원격 장치에 배포되어 시작됩니다. 디버거는 중단점에서 실행을 일시 중단하며 사용자는 한 단계씩 코드를 실행하거나, 프로시저 단위로 실행하거나 코드를 종료하여 한 번에 한 줄씩 실행할 수 있습니다. **디버깅 중지** 를 선택하여 디버그 세션을 끝내고 원격 응용 프로그램을 종료할 수 있습니다.
  
## <a name="see-also"></a>참고 항목  
 [고급 원격 배포 옵션](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)  
 [Visual Studio로 UWP 앱 테스트](../test/testing-store-apps-with-visual-studio.md)   
 [Visual Studio에서 앱 디버깅](../debugger/debug-store-apps-in-visual-studio.md)