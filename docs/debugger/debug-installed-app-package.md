---
title: "설치 된 앱 패키지 (UWP) 디버그 | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.remote.connection
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords: app package, debug
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 16f4b69fa25861d893471a161fdb7c1a6bba34e5
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="debug-an-installed-app-package-in-visual-studio-uwp"></a>Visual Studio (UWP) 설치 된 앱 패키지를 디버그 합니다.

클릭 하 여 모든 설치 된 앱 패키지를 디버깅할 수 **디버그 > 기타 디버그 대상 > 설치 된 응용 프로그램 패키지 디버그**합니다. 이 디버깅 메서드를 사용할 수에 대 한 앱 UWP (유니버설 Windows) 이러한 장치에서:

* Windows 10 (휴대폰에서 지원 되지 않음)
* XBox
* HoloLens
* IoT

이러한 기능에 대 한 자세한 내용은 블로그 게시물에 대 한 업데이트를 참조 하십시오. [설치 된 앱 패키지를 디버깅](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/30/updates-for-debugging-installed-app-packages-in-visual-studio-2015-update-2/) 및에서 post [앱 UWP (유니버설 Windows)를 구축](https://blogs.msdn.microsoft.com/visualstudio/2016/08/02/universal-windows-apps-targeting-windows-10-anniversary-sdk/)합니다.

## <a name="debug-an-installed-app-package-or-running-app-on-a-local-machine-or-device"></a>설치 된 응용 프로그램 패키지 또는 로컬 컴퓨터 또는 장치에서 실행 중인 앱 디버그

1. UWP 프로젝트를 Visual Studio에서 열기, 클릭 **디버그 > 기타 디버그 대상 > 설치 된 응용 프로그램 패키지 디버그**합니다.

2. 선택 **로컬 컴퓨터** 또는 **장치**합니다.

     선택 하면 **장치**, Windows 10 장치에 컴퓨터를 물리적으로 연결 합니다.

     ![DebugInstalledAppPackage](../debugger/media/debug-installed-app-pkg.png "DebugInstalledAppPackage")

     설치 된 응용 프로그램 패키지 표시에서 현재 실행 중인는 **실행** 노드. 아래 표시를 실행 하지 않는 응용 프로그램 패키지를 설치 **실행 되 고 있지**합니다.

3. 디버깅 하려는 응용 프로그램의 이름을 선택 **실행** 또는 **실행 되 고 있지** 선택 **시작** 또는 응용 프로그램이 이미 실행 중인 경우 선택 **연결**.

     선택 하는 경우 **시작 하지 않음 시작 시 코드 디버그**, 이렇게 하면 사용자가 지정한 시간에 실행 시 앱에 연결 하도록 Visual Studio 디버거 합니다. 이것은 제어 경로에서 디버그 하는 효과적인 방법을 [다른 시작 메서드](/windows/uwp/xbox-apps/automate-launching-uwp-apps), 같은 사용자 지정 매개 변수를 사용 하 여 프로토콜 활성화 합니다.

> [!NOTE]
> Visual Studio를 선택 하 여 실행 중인 모든 UWP 응용 프로그램 프로세스에 첨부할 수도 **디버그**, 차례로 **프로세스에 연결**합니다. 원래 Visual Studio 프로젝트 필요 하지 않은 실행 중인 프로세스에 연결 되지만 프로세스의 기호를 로드 하면 현저 하 게 지원 하지 않는 원본 코드는 프로세스를 디버깅할 때.
  
## <a name="remote"></a>원격 컴퓨터에 설치 되거나 실행 응용 프로그램 디버깅 

Visual Studio를 처음으로 원격 컴퓨터에 설치 된 응용 프로그램 패키지를 디버깅할 때 올바른 버전의 대상 장치에 대해 원격 도구를 설치 합니다. 대상 장치에 Windows 10 컴퓨터, XBox 및 HoloLens, IoT 장치 여야 합니다.

1. Windows 10 장치에서 활성화 [개발자 모드](/windows/uwp/get-started/enable-your-device-for-development)합니다.

2. 먼저 수동으로 사전-작성자의 업데이트 버전의 Windows 10을 실행 하는 원격 PC에 연결 하는 경우 [설치 하 고 원격 디버거 시작](../debugger/remote-debugging.md)합니다.

     XBox 및 HoloLens, IoT 장치 및 Windows 10 작성자의 업데이트를 실행 하는 Windows 장치에 대 한 원격 디버거를 수동으로 설치할 필요가 없습니다. 원격 도구 앱을 배포할 때 자동으로 설치 됩니다.

3. 클릭 **디버그 > 기타 디버그 대상 > 설치 된 응용 프로그램 패키지 디버그**합니다.

4. 첫 번째 드롭다운 목록에서 선택 **원격 컴퓨터**합니다.

5. 이름 또는에 연결 하려는 컴퓨터의 IP 주소에 입력 합니다.

     ![ChooseRemoteComputer](../debugger/media/debug-remote-app-pkg.png "ChooseRemoteComputer")

     컴퓨터 이름을 사용 하 여 연결 수 없는 경우 (선택한 후 **시작**), IP 주소를 대신 사용 합니다. XBox 및 HoloLens, IoT 장치에 대 한 IP 주소를 사용 합니다.

5. 옵션을 선택 하 여 인증 하는 방법을 선택 **인증 모드**합니다.

    대부분의 응용 프로그램에 대 한 기본 값을 유지 **유니버설 (암호화 되지 않은 프로토콜)**합니다.

6. 디버깅 하려는 응용 프로그램의 이름을 선택 **실행** 또는 **실행 되 고 있지** 선택 **시작** 또는 (실행 중인 응용 프로그램) **연결**합니다.

     선택 하는 경우 **시작 하지 않음 시작 시 코드 디버그**, 이렇게 하면 Visual Studio 디버거를 사용자 지정 시간에 시작 하면 응용 프로그램 패키지에 연결 합니다. 이것은 제어 경로에서 디버그 하는 효과적인 방법을 [다른 시작 메서드](/windows/uwp/xbox-apps/automate-launching-uwp-apps), 같은 사용자 지정 매개 변수를 사용 하 여 프로토콜 활성화 합니다.

     Visual Studio를 처음으로 연결된 된 XBox 및 HoloLens, IoT 장치에서 설치 된 응용 프로그램 패키지를 디버깅할 때 올바른 버전의 대상 장치에 대해 원격 디버거를 설치 합니다. 약간의 시간이 걸릴 수 있습니다 및 메시지가 표시 됩니다 ``Starting remote debugger`` 이 수행 되는 동안 합니다.

     > [!NOTE]
> 제공 하 고, XBox 또는 HoloLens 장치 디버거가 이미 실행 중인 경우 연결 된 응용 프로그램 다시 시작 됩니다.

UWP 앱의 원격 배포에 대 한 고급 옵션에 대 한 자세한 내용은 참조 [배포 및 디버깅 UWP 앱](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps.md#advanced-remote-deployment-options)합니다. 
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio의 디버깅](../debugger/index.md)  
 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)  
 [원격 디버깅](../debugger/remote-debugging.md)  
 [원격 디버깅을 위해 Windows 방화벽 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)  
 [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)