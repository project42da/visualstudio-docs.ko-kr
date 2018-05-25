---
title: Visual Studio에서 원격 디버깅 | Microsoft Docs
ms.custom: remotedebugging
ms.date: 05/21/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.remote.overview
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: db20b62c5ef409f523253c5ba19e2c68213743be
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2018
---
# <a name="remote-debugging"></a>Remote Debugging
다른 컴퓨터에 배포된 Visual Studio 응용 프로그램을 디버그할 수 있습니다. 이렇게 하려면 Visual Studio 원격 디버거를 사용합니다.

원격 디버깅에 대 한 자세한 내용은 다음이 항목을 참조 하십시오.

|시나리오|링크|
|-|-|-|
|Azure App Service|[디버거를 스냅숏](../debugger/debug-live-azure-applications.md) 또는 [원격 Azure에서 ASP.NET 디버깅](../debugger/remote-debugging-azure.md)|
|Azure VM|[Azure의 원격 디버그 ASP.NET](../debugger/remote-debugging-azure.md)|
|Azure Service Fabric|[Azure 서비스 패브릭 응용 프로그램 디버깅](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application)|
|ASP.NET|[원격 디버깅 ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md) 또는 [원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|C# 또는 Visual Basic|[C# 또는 Visual Basic 프로젝트](../debugger/remote-debugging-csharp.md) 원격 디버그|
|C++|[C++ 프로젝트 원격 디버그](../debugger/remote-debugging-cpp.md)|
|유니버설 Windows 앱 (UWP)|[UWP 앱을 원격 컴퓨터에서 실행](../debugger/run-windows-store-apps-on-a-remote-machine.md) 또는 [설치 된 응용 프로그램 패키지 디버그](../debugger/debug-installed-app-package.md)|

방금 다운로드 하 고 원격 디버거를 설치 하 고 시나리오에 대 한 추가 지침에 필요 하지 않습니다,이 문서의 단계를 수행 합니다.
  
## <a name="download-and-install-the-remote-tools"></a>원격 도구 다운로드 및 설치  

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

## <a name="unblock_msvsmon"></a> Windows Server에서 원격 도구를 다운로드 하는 차단 해제

Windows Server에서 Internet Explorer의 기본 보안 설정 하기가 더 원격 도구와 같은 구성 요소를 다운로드 하는 데 많은 시간이 소요 됩니다.

* 향상 된 보안 구성을 사용할 것을 방지 하는 리소스를 포함 하는 도메인 명시적으로 허용 하지 않는 한 웹 리소스에 액세스 하 고 웹 사이트를 열어 Internet Explorer에서 (즉, 신뢰할 수 있음).

* Windows Server 2016에서 설정 하는 기본 **인터넷 옵션** > **보안** > **인터넷**  >   **사용자 지정 수준** > **다운로드** 도 다운로드 파일을 사용 하지 않도록 설정 합니다. Windows 서버에서 직접 원격 도구를 다운로드 하려는 파일을 다운로드 사용 하도록 설정 해야 합니다.

Windows Server에서 도구를 다운로드 하려면 권장 다음 중 하나:

* 하나의 실행 중인 Visual Studio와 같은 다른 컴퓨터에서 원격 도구를 다운로드 한 후 복사는 *.exe* 파일을 Windows 서버입니다.

* 원격 디버거 실행 [파일 공유에서](#fileshare_msvsmon) Visual Studio 컴퓨터에 있습니다.

* Windows 서버에서 직접 원격 도구를 다운로드 하 고 신뢰할 수 있는 사이트를 추가 하려면 표시 되는 메시지를 적용 합니다. 최신 웹 사이트 종종 많은 타사 리소스를 포함 시켜 서이 많이 표시 되는 메시지에서 발생할 수 있습니다. 또한 모든 리디렉션된 링크를 수동으로 추가 해야 합니다. 다운로드를 시작 하기 전에 신뢰할 수 있는 사이트의 일부를 추가할 수 있습니다. 로 이동 **인터넷 옵션 > 보안 > 신뢰할 수 있는 사이트 > 사이트** 다음 사이트를 추가 합니다.

  * visualstudio.com
  * download.visualstudio.microsoft.com
  * 에 대 한: 빈

  My.visualstudio.com에 디버거의 이전 버전에 대 한 해당 로그인이 성공 하 고 있는지 확인 하기 위해 이러한 추가 사이트를 추가 합니다.

  * microsoft.com
  * go.microsoft.com
  * download.microsoft.com
  * my.visualstudio.com
  * login.microsoftonline.com
  * login.live.com
  * secure.aadcdn.microsoftonline p.com
  * msft.sts.microsoft.com
  * auth.gfx.ms
  * app.vssps.visualstudio.com
  * vlscppe.microsoft.com
  * query.prod.cms.rt.microsoft.com

    원격 도구를 다운로드 하는 동안 이러한 도메인을 추가 하도록 선택 하면 다음 선택 하는 경우 **추가** 대화 상자가 나타나면 합니다.

    ![차단 된 콘텐츠 대화 상자](../debugger/media/remotedbg-blocked-content.png)

    소프트웨어를 다운로드 하는 경우 다양 한 웹 사이트 스크립트 및 리소스를 로드할 수 있는 권한을 부여 요청을 일부 추가적인 가져옵니다. My.visualstudio.com, 해당 로그인이 성공 되도록 추가 도메인을 추가 하는 것이 좋습니다.

### <a name="fileshare_msvsmon"></a> (선택 사항) 파일 공유에서 원격 디버거를 실행 하려면

원격 디버거를 찾을 수 있습니다 (*msvsmon.exe*) Visual Studio Community, Professional 또는 Enterprise를 이미 설치 된 컴퓨터에 있습니다. 일부 시나리오에 대 한 원격 디버깅을 설정 하는 가장 쉬운 방법은 파일 공유에서 원격 디버거 (msvsmon.exe)를 실행 하는 합니다. 사용 제한 사항에 대 한 원격 디버거의 도움말 페이지를 참조 (**도움말 > 사용량** 원격 디버거에서).

1. 찾을 *msvsmon.exe* Visual Studio 버전에 일치 하는 디렉터리에 있습니다. Visual Studio Enterprise 2017에 대 한:

      *Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x86\msvsmon.exe*
      
      *Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x64\msvsmon.exe*

2. 공유는 **원격 디버거** Visual Studio 컴퓨터의 폴더에 있습니다.

3. 원격 컴퓨터에서 실행 *msvsmon.exe*합니다. 에 따라는 [설정 지침](#bkmk_setup)합니다.

> [!TIP] 
> 명령줄 설치 및 명령줄 참조에 대 한 도움말 페이지를 참조 하십시오. *msvsmon.exe* 입력 하 여 ``msvsmon.exe /?`` Visual Studio가 설치 된 컴퓨터에서 명령 줄에서 (하거나 **도움말 >사용**원격 디버거에서).
  
## <a name="requirements_msvsmon"></a> 요구 사항

[!INCLUDE [remote-debugger-requirements](../debugger/includes/remote-debugger-requirements.md)]
  
## <a name="set-up-the-remote-debugger"></a>원격 디버거 설치  

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

### <a name="configure_msvsmon"></a> 원격 디버거 구성  
원격 디버거를 처음으로 시작한 후에 원격 디버거 구성의 일부 측면을 변경할 수 있습니다.
  
-   다른 사용자가을 원격 디버거 연결 선택에 대 한 사용 권한을 추가 해야 할 경우 **도구 > 권한을**합니다. 사용 권한을 부여하거나 거부하려면 관리자 권한이 있어야 합니다.

     > [!IMPORTANT] 
     > Visual Studio 컴퓨터에서 사용 하는 사용자 계정에서 다른 사용자 계정으로 원격 디버거를 실행할 수 있지만 원격 디버거의 사용 권한에 다른 사용자 계정을 추가 해야 있습니다. 

     또는 사용 하 여 명령줄에서 원격 디버거를 시작할 수 있습니다는 **허용 / \<사용자 이름 >** 매개 변수: **msvsmon /allow \< username@computer>** 합니다.
  
-   인증 모드 또는 포트 번호를 변경 하거나 원격 도구에 대 한 제한 시간 값을 지정 해야 할 경우: 선택 **도구 > 옵션**합니다.  
  
     기본적으로 사용 되는 포트 번호의 목록을 보려면 [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)합니다.  
  
     > [!WARNING]
     >  원격 도구를 인증 안 함 모드에서 실행할 수도 있지만 이 모드는 사용하지 않는 것이 좋습니다. 이 모드에서 실행할 때는 네트워크 보안이 없습니다. 네트워크에 악의적인 트래픽이나 유해 트래픽 위험이 확실히 없는 경우에만 인증 안 함 모드를 선택하세요.

##  <a name="bkmk_configureService"></a> (선택 사항) 원격 디버거를 서비스로 구성
ASP.NET 및 기타 서버 환경에서 디버깅을 관리자 권한으로 원격 디버거를 실행 하거나, 항상 실행 하려는 경우 원격 디버거 서비스를 실행 합니다.
  
 원격 디버거를 서비스로 구성 하려면 다음이 단계를 수행 합니다.  
  
1.  **원격 디버거 구성 마법사** (rdbgwiz.exe)를 찾습니다. 이는 원격 디버거와 별도의 응용 프로그램입니다. 원격 도구를 설치한 경우에만 사용할 수 있습니다. Visual Studio와 함께 설치되지 않습니다.  
  
2.  구성 마법사 실행을 시작합니다. 첫 페이지가 표시되면 **다음**을 클릭합니다.  
  
3.  **Visual Studio 2015 원격 디버거를 서비스로 실행** 확인란을 선택합니다.  
  
4.  사용자 계정 및 암호의 이름을 추가합니다.  
  
     추가 해야 할 수는 **서비스로 로그온** 권한을이 계정에는 사용자 (찾기 **로컬 보안 정책** (secpol.msc)에 **시작** 페이지 또는 창 (또는 형식  **secpol을** 명령 프롬프트에서). 창이 나타나면 **사용자 권한 할당**을 두 번 클릭한 다음 오른쪽 창에서 **서비스로 로그온** 을 찾습니다. 폴더를 두 번 클릭합니다. 에 사용자 계정을 추가 **속성** 창과 클릭 **확인**). **다음**을 클릭합니다.  
  
5.  원격 도구가 통신하는 데 사용할 네트워크 유형을 선택합니다. 하나 이상의 네트워크 형식을 선택해야 합니다. 컴퓨터가 도메인을 통해 연결된 경우 첫 번째 항목을 선택해야 합니다. 컴퓨터가 작업 그룹 또는 홈 그룹을 통해 연결된 경우 두 번째 또는 세 번째 항목을 선택해야 합니다. **다음**을 클릭합니다.  
  
6.  서비스를 시작할 수 있는 경우 **Visual Studio 원격 디버거 구성 마법사를 성공적으로 완료했습니다.** 가 표시됩니다. 서비스를 시작할 수 없는 경우 **Visual Studio 원격 디버거 구성 마법사 완료 실패**가 표시됩니다. 이 페이지에서는 서비스를 시작하기 위해 수행할 몇 가지 팁도 제공합니다.  
  
7.  **마침**을 클릭합니다.  
  
 이제 원격 디버거가 서비스로 실행됩니다. 로 이동 하 여이 확인할 수 있습니다 **제어판 > 서비스** 하 고 찾고 **Visual Studio 2015 원격 디버거**합니다.  
  
 중지 하 고에서 원격 디버거 서비스를 시작할 수 **제어판 > 서비스**합니다.

## <a name="set-up-debugging-with-remote-symbols"></a>원격 기호를 사용한 디버깅 설정 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]
  
## <a name="see-also"></a>참고 항목  
 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)   
 [원격 디버깅용 Windows 방화벽 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)   
 [원격 디버깅 ASP.NET Core 원격 IIS 컴퓨터에](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)
