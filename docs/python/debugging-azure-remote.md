---
title: "Visual Studio에서 Python을 사용하여 Azure 원격 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: e0cac283dacb0f63005f67dc279087726de26772
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="remotely-debugging-python-code-on-azure"></a>Azure에서 Python 코드 원격 디버깅

[Visual Studio의 Python 지원](installation.md)에는 Azure App Service에서 실행되는 Python 코드를 원격으로 디버그하는 기능이 포함되어 있습니다. 간단한 원격 디버깅과 달리 이 시나리오의 대상 컴퓨터는 TCP를 통해 직접 액세스할 수 없으므로 Visual Studio에서 HTTP를 통해 디버거 프로토콜을 제공하는 프록시를 제공합니다. 웹 템플릿을 사용하여 만든 프로젝트는 생성된 `web.debug.config` 파일에서 이 프록시를 자동으로 구성합니다. 또한 원격 디버깅은 [Azure App Service에 게시](template-web.md#publishing-to-azure-app-service)에서 설명한 대로 프로젝트의 디버그 구성을 게시할 때 사용할 수도 있습니다.

Azure 원격 디버깅에서 웹 소켓을 사용하기 때문에 [Azure Portal](https://portal.azure.com)에서 **설정 > 응용 프로그램 설정**으로 이동하고, **일반 설정 > 웹 소켓**을 **사용**으로 설정한 다음, **저장**을 선택하여 변경 내용을 적용함으로써 App Service를 사용하도록 설정해야 합니다. (**디버깅** 설정은 Python 디버깅에 적용되지 않습니다.)

![Azure Portal에서 웹 소켓을 사용하도록 설정](media/azure-remote-debugging-enable-web-sockets.png)

프로젝트가 올바르게 배포되고 웹 소켓을 사용하도록 설정한 후에는 Visual Studio의 **서버 탐색기**(**보기 > 서버 탐색기**)에서 App Service에 연결할 수 있습니다. **Azure > App Service**와 해당 리소스 그룹에서 사이트를 찾고, 마우스 오른쪽 단추로 클릭하여 **디버거 연결(Python)**을 선택합니다. **디버거 연결** 명령은 IIS에서 실행되는 .NET 응용 프로그램의 명령이므로 Python 앱과 함께 .NET 코드를 공동 호스트하는 경우에만 유용합니다.

Visual Studio는 [서버 탐색기 없이 연결](#attaching-without-server-explorer)에서 설명한 대로 직접 연결하기 위한 지침의 집합으로 바로 연결됩니다. **디버거 연결(Python)** 명령이 표시되지 않거나 Visual Studio에서 사이트에 연결되지 않으면 [Azure 원격 디버깅 문제 해결](debugging-azure-remote-troubleshooting.md)을 참조하세요.

연결이 성공하면 Visual Studio가 디버거 보기로 전환합니다. 도구 모음에 디버그 중인 프로세스가 표시됩니다(예: `wss://` URI).

![Azure App Service 웹 사이트 디버깅](media/azure-remote-debugging-attached.png)

연결되면 디버깅 환경이 일반적인 원격 디버깅과 거의 동일하지만, 여기에는 몇 가지 제약 조건이 있습니다. 특히 들어오는 요청을 처리하고 FastCGI를 통해 Python 코드에 위임하는 IIS 웹 서버에는 요청 처리에 대한 시간 초과가 있으며, 기본값은 90초입니다. 요청 처리가 해당 시간 제한보다 오래 걸리는 경우(예: 프로세스가 중단점에서 일시 중지되어 있기 때문에) IIS에서 프로세스를 종료하여 디버깅 세션을 종료합니다. 

## <a name="attaching-without-server-explorer"></a>서버 탐색기 없이 연결

App Service에 디버거를 직접 연결하려면 Visual Studio에서 `<site_url>/ptvsd`에 있는 사이트(예: `ptvsdemo.azurewebsites.net/ptvsd`)에 배포하는 WebSocket 프록시 정보 페이지의 지침을 따릅니다. 이 페이지를 방문하면 프록시가 올바르게 구성되었는지도 확인할 수 있습니다.

![Azure 원격 디버깅 프록시 정보 페이지](media/azure-remote-debugging-proxy-info-page.png)

지침에 따라 프로젝트가 게시될 때마다 다시 생성되는 `web.debug.config`의 비밀을 사용하여 URL을 생성합니다. 이 파일은 기본적으로 솔루션 탐색기에서 숨겨져 있으며, 프로젝트에 포함되어 있지 않으므로 모든 파일을 표시하거나 별도의 편집기에서 엽니다. 파일을 연 후 `WSGI_PTVSD_SECRET`이라는 appSetting의 값을 확인합니다.

![Azure App Service에서 디버거 끝점 확인](media/azure-remote-debugging-secret.png)

지금 필요한 URL은 `wss://<secret>@<site_name>.azurewebsites.net/ptvsd` 형식이며, 여기서 문자열의 &lt;secret&gt;과 &lt;site_name&gt;을 특정 값으로 바꿉니다.

디버거를 연결하려면 **디버그 > 프로세스에 연결**을 선택하고, **전송** 드롭다운에서 **Python 원격 디버깅**을 선택하고, **한정자** 텍스트 상자에서 URL을 입력한 다음, Enter 키를 누릅니다. Visual Studio에서 App Service에 성공적으로 연결할 수 있으면 목록에 단일 Python 프로세스가 표시됩니다. 이 프로세스를 선택한 다음 **연결**을 선택하여 디버깅을 시작합니다.

![프로세스에 연결 대화 상자로 Azure 웹 사이트에 연결](media/azure-remote-debugging-manual-attach.png)
