---
title: ASP.NET 응용 프로그램에 대 한 디버깅을 활성화 | Microsoft Docs
ms.custom: H1HackMay2017
ms.date: 09/21/17
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications
- Web.config configuration file, debug mode
- debugging [Visual Studio], ASP.NET
ms.assetid: 3beed819-cece-4864-8184-bd410000973a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 397dbe26aafd7ec385e6afeb11b3ca19155dfbcc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debug-aspnet-applications-in-visual-studio"></a>Visual Studio에서 ASP.NET 응용 프로그램 디버그

Visual Studio에서 ASP.NET 응용 프로그램을 디버깅할 수 있습니다.

## <a name="requirements"></a>요구 사항

이 항목의 지침을 수행 하려면 다음을 수행 해야 합니다.

- IIS Express 이상 Visual Studio 2012에서 기본적으로 포함 되어 있습니다

    -또는-

- 로컬 IIS 웹 서버 (버전 8.0 이상)를 올바로 구성 되 고 오류 없이 ASP.NET 응용 프로그램을 실행할 수입니다.

서버가 원격 인 경우 원격 컴퓨터에서 원격 디버거를 실행 합니다. 원격 IIS 서버를 디버깅 하려면 참조 [IIS 컴퓨터에 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)합니다. 

## <a name="configure-debug-settings"></a>디버그 설정 구성

### <a name="enable-aspnet-debugging-in-the-project-properties"></a>프로젝트 속성에서 ASP.NET 디버깅 사용

1. Visual Studio에서 ASP.NET 프로젝트를 엽니다.

2. 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**, 선택 **속성**, 클릭 하 고는 **웹** 탭 합니다.

    일부 프로젝트 형식에 대 한 선택 **속성 > 디버그** 대신 합니다. ASP.NET Web Forms 프로젝트에 대 한 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성 페이지 > 시작 옵션**합니다.
  
3.  **디버거**아래에서 **ASP.NET** 확인란을 선택합니다.

    ![디버거 설정](../debugger/media/dbg-aspnet-enable-debugging.png "디버거 설정")

> [!NOTE]
> 새 ASP.NET 프로젝트를 만드는 경우 (**파일 > 새 프로젝트**), 디버그 설정이 이미 올바르게 구성 합니다.

### <a name="enable-debugging-in-the-webconfig-file"></a>Web.config 파일에 디버깅 사용  

웹 응용 프로그램을 디버깅 하려면 응용 프로그램의 web.config 파일을 올바르게 구성 되어야 합니다. Web.config 파일은 IIS 또는 IIS Express에서 응용 프로그램을 호스트 하는 경우에 필요 합니다.

ASP.NET Core에 대 한 web.config 파일도 (이 이미 있는) 하는 경우 앱을 배포할 때 자동으로 만들어집니다.

> [!TIP]
> 배포 프로세스에는 web.config 설정을 업데이트할 수 있습니다. 따라서 디버깅 하 려 하기 전에 서버에서 web.config 설정을 확인 하세요.
  
1.  Visual Studio에서 프로젝트의 web.config 파일을 엽니다.  
  
    > [!NOTE]  
    > 웹 브라우저를 사용 하 여 web.config 파일을 원격으로 액세스할 수 없습니다. 보안상의 이유로 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]는 브라우저에서 Web.config 파일에 직접 액세스할 수 없도록 Microsoft IIS를 구성합니다. 브라우저를 사용 하 여 구성 파일에 액세스 하려고 하면 HTTP 액세스 오류를 403 (사용할 수 없음)를 가져옵니다.  
  
2.  `configuration/system.web/compilation` 요소를 찾습니다. 컴파일 요소가 없는 경우 생성합니다.

    Web.config는 XML 파일이므로 태그로 표시된 중첩된 섹션을 포함합니다.
  
3.  `compilation` 요소에 `debug` 특성이 없으면 요소에 특성을 추가합니다.  
  
4.  `debug` 특성 값이 `true`을 참조하세요.  
  
Web.config 파일은 다음 예제와 같아야 합니다.

> [!NOTE]
> 이 예제에서는 부분 web.config 파일입니다. 추가 XML 섹션 구성 요소와 system.web 요소 사이 일반적으로 제공 됩니다. 컴파일 요소는 다른 특성 및 요소를 포함할 수도 있습니다.
  
#### <a name="example"></a>예제  
  
```  
<configuration>  
    ...  
    <system.web>  
        <compilation  
            debug="true"  
            ...  
        >  
        ...  
        </compilation>  
    </system.web>  
</configuration>  
```

외부 서버를 기본 IIS Express 서버 대신 사용 하는 경우도 확인 해야 하는 `targetFramework` 특성 값은 서버에서 구성을 일치 합니다.

> [!IMPORTANT]
> 최상의 성능을 위해서는 프로덕션 앱으로 설정 `debug=false` 하 고 작성 하 고 응용 프로그램을 게시 하는 경우 릴리스 빌드를 지정 합니다.

## <a name="configure-project-settings-for-the-server"></a>서버에 대 한 프로젝트 설정 구성

로컬 웹 서버에서 디버깅을 위해 프로젝트 속성을 설정 합니다. 원격 서버에서 디버깅을 위해에 설명 된 보다 포괄적인 지침을 따라 [IIS에서 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md) 대신 합니다.

1. 에 **웹** 프로젝트 탭 속성 중 하나를 선택 합니다. **IIS Express** 또는 **외부 서버** 아래는 **서버** 설정 합니다. (일부 프로젝트 형식에 대 한 이러한 설정은 아래에 표시 된 **디버그** 대신 탭 합니다.)

    ![서버 설정](../debugger/media/dbg-aspnet-server-settings.png "서버 설정")

    IIS Express는 ASP.NET에 대 한 기본 서버 및 특별 한 구성이 일반적으로 필요 하지 않습니다. 이 ASP.NET 응용 프로그램을 디버깅 하는 가장 쉬운 방법은 합니다.

    프로젝트를 마우스 오른쪽 단추로 클릭 ASP.NET Web Forms 프로젝트를 선택 **속성 페이지 > 시작 옵션**, 선택 **기본 웹 서버 사용** 또는 **사용자 지정 서버 사용** 드 ( 대신 **외부 서버**).

    ![Web Forms 응용 프로그램에 대 한 서버 설정을](../debugger/media/dbg-aspnet-server-settings-webforms.png "Web Forms 응용 프로그램에 대 한 서버 설정")

2. 외부 (사용자 지정) 서버를 선택한 경우에 올바른 URL을 입력 합니다.는 **프로젝트 URL** (또는 **기준 URL**) 필드입니다.

    외부 서버가 로컬 IIS 경우 IIS는 설치 하 고 올바르게 구성 해야 합니다. 예를 들어 IIS에서 올바른 버전의 ASP.NET 구성 되어야 합니다. 자세한 내용은 참조 [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)합니다. 디버깅 뿐만 아니라 배포를 테스트 하려는 경우 참조 [테스트 배포](/aspnet/web-forms/overview/deployment/visual-studio-web-deployment/deploying-to-iis)합니다.

    외부 서버가 경우 [원격](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)대신, 프로세스에 연결 하 고 디버깅을 위해 이러한 프로젝트 설정은 사용 되지 않습니다.

## <a name="local-iis-web-server-configure-iis"></a>(로컬 IIS 웹 서버) IIS 구성

IIS express 웹 서버를 구성할 필요가 없습니다 (이 섹션 생략). 초기 테스트를 위해 IIS Express 것이 좋습니다.

로컬 IIS 웹 서버를 사용 하는 경우 다음이 단계를 수행 합니다.

1. IIS가 올바르게 설치 되었는지 확인 합니다. 자세한 내용은 참조 [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)합니다.

    * 서버에 올바른 버전의 ASP.NET 설치 하 고 있는지 확인 합니다. 웹 플랫폼 설치 관리자 (WebPI)를 사용 하 여 ASP.NET 4.5를 설치 하려면 (Windows Server 2012 r 2의 서버 노드에서 선택 **새 웹 플랫폼 구성 요소 가져오기** ASP.NET 검색할). ASP.NET Core를 설치 하려면 [를 IIS에 게시](https://docs.asp.net/en/latest/publishing/iis.html#iis-configuration)합니다.

    > [!NOTE]
    > Windows Server 2008 r 2를 사용 하는 경우이 명령을 사용 하는 ASP.NET 4를 설치 합니다.

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. 열기는 **인터넷 정보 서비스 (IIS) 관리자**합니다. (서버 관리자의 왼쪽된 창에서 선택 **IIS**합니다. 서버를 마우스 오른쪽 단추로 클릭 하 고 선택 **인터넷 정보 서비스 (IIS) 관리자**.)

3. 아래 **연결** 왼쪽된 창에서로 이동 **사이트**합니다.

4. **기본 웹 사이트** 노드를 마우스 오른쪽 단추로 클릭하고 **응용 프로그램 추가**를 선택합니다.

5. 설정의 **별칭** 필드를 **MyASPApp**, 응용 프로그램 풀 기본값을 그대로 (**DefaultAppPool**)을 설정 하 고는 **실제 경로** 를 **C:\inetpub\myNewFolder** (응용 프로그램에 대 한 새 폴더 만들기).

6. 아래 **연결**선택, **응용 프로그램 풀**합니다. 열기 **DefaultAppPool** 응용 프로그램 풀 필드 (ASP.NET 4에 ASP.NET 4.5를 사용 응용 프로그램에 대 한 올바른 값으로 설정 합니다. 사용 하 여 **관리 코드가 없는** ASP.NET Core에 대 한).

## <a name="local-iis-web-server-deploy-the-app"></a>(로컬 IIS 웹 서버) 앱 배포

IIS express 웹 앱은 자동으로 배포 디버깅을 시작할 때 (이 섹션 생략).

로컬 IIS 웹 서버를 사용 하는 경우 다음이 단계를 수행 합니다. 여러 가지 방법으로 IIS에 응용 프로그램을 게시 합니다. 다음이 단계에서는 만들고 파일 시스템을 사용 하 여 배포할 수 있도록 게시 프로필을 사용 하는 방법을 보여 줍니다.

1. 관리자 권한으로 Visual Studio를 다시 시작 합니다.

    이 메서드를 사용 하 여를 배포 하려면 관리자 권한이 필요 합니다.

2. Visual Studio에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시** (Web Forms를 사용 하 여 **웹 응용 프로그램 게시**).

3. 선택 **IIS, FTP, 등** 클릭 **게시**합니다.

    ![IIS에 게시](../debugger/media/dbg-aspnet-local-iis.png "IIS에 게시")

    Web Forms 앱에 대 한 선택 **사용자 지정** 게시 대화 상자에서 프로필 이름을 입력 하 고 선택 **확인**합니다.

4. 에 **게시 방법** 필드에서 선택 **파일 시스템**합니다.

5. 에 대 한는 **대상 위치**, 클릭는 **찾아보기** 단추입니다.

6. (ASP.NET 코어) 선택 **파일 시스템** 를 이전에 만든 응용 프로그램에 대 한 폴더를 선택 합니다.

6. (ASP.NET) 선택 **로컬 IIS**, 이전에 만든 하 고 클릭 한 다음 웹 사이트를 선택 하 고 **열려**합니다.

    ![IIS에 게시](../debugger/media/dbg-aspnet-local-iis-select-site.png "IIS에 게시")

    > [!TIP]
    > 웹 서버를 알리는 메시지를 올바르게 구성 되지 않았습니다. 표시 되 면 IIS에 대 한 올바른 버전의 ASP.NET가 설치 되어 있는지 확인 합니다.

7. 클릭 **다음** 선택 하 고는 **디버그** 구성 합니다.

    > [!NOTE]
    > 릴리스 구성으로 배포 하는 경우이 설정 `debug=false` 서버의 web.config 파일에 있습니다.

8. 클릭 **저장** 게시 설정을 저장 한 다음 클릭 **게시**합니다.

    > [!CAUTION]
    >  변경 하려면 코드 또는 다시 작성 해야 할 경우에 다시 게시 하 고이 단계를 반복 해야 합니다. 원격 컴퓨터에 복사한 실행 파일은 로컬 소스 및 기호와 정확히 일치해야 합니다.

## <a name="set-a-breakpoint-and-start-debugging"></a>중단점을 설정 하 고 디버깅 시작

1. Visual Studio에서 프로젝트를 사용자가 알고 있는 일부 코드에 중단점 설정 실행 됩니다.

2. 키를 눌러 디버깅을 시작 하려면 **F5** (**디버그 > 디버깅 시작**).

3. 중단점을 포함 하는 코드를 실행 하는 작업을 수행 합니다.

    중단점을 설정 하면 디버거에서 일시 중지 합니다.

### <a name="local-iis-troubleshooting-cannot-hit-the-breakpoint"></a>(로컬 IIS) 문제 해결: 중단점이 적중 수 없습니다.

1. IIS에서 웹 응용 프로그램을 시작 하 고 올바르게 실행 되는지 확인 합니다. 웹 앱이 실행 중인 상태로 둡니다.

2. Visual Studio에서 선택 **디버그 > 프로세스에 연결** ASP.NET 프로세스에 연결 하 고 (일반적으로 **w3wp.exe** 또는 **dotnet.exe**). 자세한 내용은 참조 [프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다.

    사용 하 여 연결할 수 있는 경우 **프로세스에 연결** 하 고 중단점을 적중할 수 있지만 사용 하 여 디버깅을 시작할 수 없습니다 **F5**, 가능성이 설정이 프로젝트 속성에 올바르지 않습니다. 호스트 파일을 사용 하는 경우 올바르게 구성 되어 있는지 확인 합니다.

  
## <a name="robust-programming"></a>강력한 프로그래밍  
[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]가 Web.config 파일의 변경 내용을 자동으로 검색하고 새 구성 설정을 적용합니다. 변경 내용을 적용하기 위해 컴퓨터를 다시 시작하거나 IIS 서버를 다시 시작할 필요가 없습니다.  
  
웹 사이트에는 여러 개의 가상 디렉터리 및 하위 디렉터리가 포함될 수 있으며 각 디렉터리에 Web.config 파일이 있을 수도 있습니다. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램은 URL 경로의 상위 수준에 있는 Web.config 파일에서 설정을 상속합니다. 계층적 구성 파일을 사용하면 계층 구조의 모든 하위 응용 프로그램 등 여러 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램에 대한 설정을 동시에 변경할 수 있습니다. 그러나 경우 `debug` 설정 된 값을 높게 계층 구조의 하위 파일에서 재정의 합니다.  
  
예를 들어, 지정할 수 `debug="true"` www.microsoft.com/aaa/Web.config, 및 모든 응용 프로그램 aaa 폴더 또는 aaa의 모든 하위 폴더는 해당 설정을 상속 합니다. 따라서 프로그램 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] www.microsoft.com/aaa/bbb는 응용 프로그램, 상속 해당 설정을 하나 됩니다 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] www.microsoft.com/aaa/ccc, www.microsoft.com/aaa/ddd, 및 등의 응용 프로그램입니다. 단, 해당 응용 프로그램 중 하나가 고유한 하위 Web.config 파일을 통해 설정을 재정의하는 경우는 예외입니다.  
  
> [!IMPORTANT]
> 성능 영향을 크게 디버그 모드를 사용 하도록 설정 하면 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램입니다. 릴리스 응용 프로그램을 배포하거나 성능을 측정하기 전에 디버그 모드를 사용하지 않도록 설정해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
[ASP.NET 디버깅: 시스템 요구 사항](aspnet-debugging-system-requirements.md)   
[방법: 사용자 계정으로 작업자 프로세스를 실행 합니다.](how-to-run-the-worker-process-under-a-user-account.md)   
[방법: ASP.NET 프로세스의 이름 찾기](how-to-find-the-name-of-the-aspnet-process.md)   
[배포 된 웹 응용 프로그램 디버그](debugging-deployed-web-applications.md)   
[연습: Web Form 디버깅](walkthrough-debugging-a-web-form.md)   
[방법: ASP.NET 예외 디버깅](how-to-debug-aspnet-exceptions.md)   
[웹 응용 프로그램 디버그: 오류 및 문제 해결](debugging-web-applications-errors-and-troubleshooting.md)
  