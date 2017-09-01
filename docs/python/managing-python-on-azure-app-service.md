---
title: "Azure App Service에서 Python 관리 | Microsoft Docs"
ms.custom: 
ms.date: 7/12/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e56b5d55-6e6b-48af-af40-5172c768cabc
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: c00adbbabf0d3b82acb17f4a269dfc693246bc69
ms.openlocfilehash: 56fccdd5e103cf29c8ea4a93ab80de7187275642
ms.contentlocale: ko-kr
ms.lasthandoff: 08/01/2017

---

# <a name="managing-python-on-azure-app-service"></a>Azure App Service에서 Python 관리

[Azure App Service](https://azure.microsoft.com/services/app-service/)는 브라우저를 통해 액세스한 사이트, 고유한 클라이언트에서 사용된 REST API, 이벤트 트리거된 처리 등 웹앱용 Platform-as-a-Service 제품입니다. App Service는 Python을 사용한 앱 구현을 완벽하게 지원합니다.

Azure App Service의 Python 지원은 각각 특정 버전의 Python 런타임이 포함된 App Service 사이트 확장 집합으로 제공됩니다. 최신 Python 3 버전이 권장되지만, 필요한 경우 이전 버전을 선택할 수 있습니다. 이 항목에서는 원하는 패키지와 함께 사이트 확장을 설치 및 구성하는 방법을 설명합니다.

> [!Note]
> 여기서 설명한 프로세스는 변경될 수 있으며, 특히 개선될 수 있습니다. 변경 내용은 [Python Engineering at Microsoft](https://blogs.msdn.microsoft.com/pythonengineering/)(Microsoft의 Python 엔지니어링) 블로그에 공지됩니다.

## <a name="choosing-a-python-version-through-the-azure-portal"></a>Azure Portal을 통해 Python 버전 선택

Azure App Service에 사이트가 이미 배포되어 실행 중인 경우 App Service 블레이드로 이동하고 **개발 도구** 섹션으로 스크롤한 다음 **확장 > 추가**를 선택합니다. 목록을 스크롤하여 원하는 Python 버전용 특정 확장을 찾습니다. 안타깝게도, 목록을 정렬할 수 없으므로 다양한 버전이 목록에 분산되어 있는 경우가 많습니다.

![Python 확장이 표시된 Azure Portal](media/python-on-azure-extensions.png)

## <a name="choosing-a-python-version-through-the-azure-resource-manager"></a>Azure Resource Manager를 통해 Python 버전 선택

Azure Resource Manager 템플릿을 사용하여 사이트를 배포하는 경우 사이트 확장을 리소스로 추가합니다. 확장은 `siteextensions` 형식과 [siteextensions.net](https://www.siteextensions.net/packages?q=Tags%3A%22python%22)의 이름을 사용하여 사이트의 중첩된 리소스로 표시됩니다.

예를 들어 `python361x64`(Python 3.6.1 x64)에 대한 참조를 추가하면 템플릿이 다음과 같이 표시될 수 있습니다.

```json
  "resources": [
    {
      "apiVersion": "2015-08-01",
      "name": "[parameters('siteName')]",
      "type": "Microsoft.Web/sites",
      ...
      "resources": [
        {
          "apiVersion": "2015-08-01",
          "name": "python361x64",
          "type": "siteextensions",
          "properties": { },
          "dependsOn": [
            "[resourceId('Microsoft.Web/sites', parameters('siteName'))]"
          ]
        },
      ...
```

## <a name="configuring-your-site"></a>사이트 구성

포털이나 Azure Resource Manager 템플릿을 통해 사이트 확장을 설치하면 Python 설치 경로가 `d:\home\python361x64\python.exe`와 같이 표시됩니다. 특정 경로를 보려면 App Service에 대해 표시된 목록에서 확장을 선택하여 경로를 포함하는 설명 페이지를 엽니다.

![Azure App Service의 확장 목록](media/python-on-azure-extension-list.png)

![Azure App Service의 확장 세부 정보](media/python-on-azure-extension-detail.png)

다음 단계는 사이트의 `web.config` 파일에서 FastCGI 및 HTTP 플랫폼 요청 처리기 모두에 대해 Python 설치를 참조하는 것입니다.

### <a name="using-the-fastcgi-handler"></a>FastCGI 처리기 사용

FastCGI는 요청 수준에서 작동하는 인터페이스입니다. IIS는 들어오는 연결을 받은 다음 하나 이상의 영구적 Python 프로세스에서 실행되는 WSGI 앱에 각 요청을 전달합니다. [wfastcgi 패키지](https://pypi.io/project/wfastcgi)는 사전 설치되고 각 Python 사이트 확장으로 구성되어 있으므로 `web.config`에 다음 코드를 포함하여 쉽게 사용할 수 있습니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <appSettings>
    <add key="PYTHONPATH" value="D:\home\site\wwwroot"/>
    <add key="WSGI_HANDLER" value="app.wsgi_app"/>
    <add key="WSGI_LOG" value="D:\home\LogFiles\wfastcgi.log"/>
  </appSettings>
  <system.webServer>
    <handlers>
      <add name="PythonHandler" path="*" verb="*" modules="FastCgiModule" scriptProcessor="D:\home\Python361x64\python.exe|D:\home\Python361x64\wfastcgi.py" resourceType="Unspecified" requireAccess="Script"/>
    </handlers>
  </system.webServer>
</configuration>
```

`<appSettings>`은 앱에서 환경 변수로 사용할 수 있습니다.
- `PYTHONPATH` 값은 자유롭게 확장될 수 있지만 해당 사이트의 루트를 포함해야 합니다.
- `WSGI_HANDLER`는 사이트에서 가져올 수 있는 WSGI 앱을 가리켜야 합니다.
- `WSGI_LOG`는 선택 사항이지만 사이트 디버깅을 위해 권장됩니다. 

`<handlers>`에서 `<add>` 요소의 `scriptProcessor` 특성에 특정 설치의 적절한 경로가 포함되어 있는지 확인합니다. 경로는 확장의 세부 정보 블레이드에 다시 표시됩니다.

### <a name="using-the-http-platform-handler"></a>HTTP 플랫폼 처리기 사용

HttpPlatform 모듈은 소켓 연결을 독립 실행형 Python 프로세스에 직접 전달합니다. 이 전달을 통해 원하는 모든 웹 서버를 실행할 수 있지만 로컬 웹 서버를 실행하는 시작 스크립트가 필요합니다. `<httpPlatform>` 요소에 스크립트를 지정합니다. 여기서 `processPath` 특성은 Python을 가리키고, `arguments` 특성은 스크립트 및 제공하려는 모든 인수를 가리킵니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.webServer>
    <handlers>
      <add name="PythonHandler" path="*" verb="*" modules="httpPlatformHandler" resourceType="Unspecified"/>
    </handlers>
    <httpPlatform processPath="D:\home\Python361x64\python.exe"
                  arguments="D:\home\site\wwwroot\runserver.py --port %HTTP_PLATFORM_PORT%"
                  stdoutLogEnabled="true"
                  stdoutLogFile="D:\home\LogFiles\python.log"
                  startupTimeLimit="60"
                  processesPerApplication="16">
      <environmentVariables>
        <environmentVariable name="SERVER_PORT" value="%HTTP_PLATFORM_PORT%" />
      </environmentVariables>
    </httpPlatform>
  </system.webServer>
</configuration>
```

물론, 구성의 `python.exe` 경로는 설치한 버전과 관련이 있습니다.

코드에 표시된 `HTTP_PLATFORM_PORT` 환경 변수에는 로컬 서버가 localhost의 연결을 수신 대기해야 하는 포트가 포함됩니다. 이 예제에서는 원하는 경우 다른 환경 변수(이 경우 `SERVER_PORT`)를 만드는 방법도 보여 줍니다.

## <a name="installing-packages"></a>패키지 설치

앱은 다양한 패키지에 의존하기 때문에 다음 세 가지 방법 중 하나를 통해 App Service의 Python 환경에 해당 패키지가 설치되어 있는지 확인해야 합니다.

- Azure Portal의 Azure App Service 콘솔
- Kudu REST API
- 앱 소스 코드에 각 라이브러리 복사

### <a name="kudu-console"></a>Kudu 콘솔

[Kudu 콘솔](https://github.com/projectkudu/kudu/wiki/Kudu-console)은 App Service 서버와 해당 파일 시스템에 대한 직접적인 관리자 권한 명령줄 액세스를 제공합니다. 유용한 디버깅 도구일뿐만 아니라 CLI 기반 구성에도 사용할 수 있습니다.

**개발 도구 > 고급 도구**를 선택하여 App Service 블레이드에서 Kudu에 액세스한 다음 **이동**을 선택하여 `.scm`이 삽입된 것을 제외하고 기본 App Service URL과 동일한 URL로 이동합니다. 예를 들어 기준 URL이 `https://vspython-test.azurewebsites.net/`이면 Kudu는 `https://vspython-test.scm.azurewebsites.net/`에 있습니다.

![Azure App Service용 Kudu 콘솔](media/python-on-azure-console01.png)

**디버그 콘솔 > CMD**를 선택하여 콘솔을 엽니다. 여기서 Python 설치로 이동하여 어떤 라이브러리가 있는지 확인할 수 있습니다.

단일 패키지를 설치하려면

1. 패키지를 설치하려는 Python 설치 폴더(예: `d:\home\python361x64`)로 이동합니다.
1. `python.exe -m pip install <package_name>`을 사용하여 패키지를 설치합니다.

![Azure App Service용 Kudu 콘솔을 통한 matplotlib 설치의 예](media/python-on-azure-console02.png)

`requirements.txt`에서 패키지를 설치하려면(권장)

1. 패키지를 설치하려는 Python 설치 폴더(예: `d:\home\python361x64`)로 이동합니다.
1. `python.exe -m pip install --upgrade -r d:\home\site\wwwroot\requirements.txt`를 사용하여 패키지를 설치합니다.

로컬 및 서버 모두에서 정확한 패키지 집합을 쉽게 재현할 수 있기 때문에 requirements.txt를 사용하는 것이 좋습니다.

> [!Note]
> 웹 서버에는 C 컴파일러가 없으므로 기본 확장 모듈이 있는 모든 패키지에 대해 휠을 설치해야 합니다. 인기 있는 많은 패키지가 자체 휠을 제공합니다. 자체 휠을 제공하지 않는 패키지의 경우 로컬 개발 컴퓨터의 `pip wheel <package_name>`을 사용한 다음 휠을 사이트에 업로드합니다. 예를 들어 [필수 패키지 관리](python-environments.md#managing-required-packages)를 참조하세요.

### <a name="kudu-rest-api"></a>Kudu REST API

Azure Portal을 통해 Kudu 콘솔을 사용하는 대신 `https://yoursite.scm.azurewebsites.net/api/command`에 명령을 게시하여 Kudu REST API를 통해 원격으로 명령을 실행할 수 있습니다. 예를 들어 `matplotlib` 패키지를 설치하려면 다음 JSON을 `/api/command`에 게시합니다.

```json
{
    "command": 'python.exe -m pip install matplotlib',
    "dir": '\home\python361x64'
}
```

명령 및 인증에 대한 자세한 내용은 [Kudu 설명서](https://github.com/projectkudu/kudu/wiki/REST-API)를 참조하세요. Azure CLI에서 [`az webapp deployment list-publishing-profiles command`](https://docs.microsoft.com/cli/azure/webapp/deployment#list-publishing-profiles)을 사용하여 자격 증명을 확인할 수도 있습니다. Kudu 명령을 게시하는 도우미 라이브러리도 [GitHub에서 사용할 수 있습니다](https://github.com/lmazuel/azure-webapp-publish/blob/master/azure_webapp_publish/kudu.py#L42).


### <a name="copying-libraries-into-app-source-code"></a>앱 소스 코드에 라이브러리 복사

서버에 직접 패키지를 설치하는 대신 사용자 고유의 소스 코드에 라이브러리를 복사하고 앱의 일부인 것처럼 배포할 수 있습니다. 보유한 종속성 수와 업데이트 빈도에 따라 이 방법은 배포 작업을 진행하는 가장 쉬운 방법일 수 있습니다.

주의 사항은 이러한 라이브러리가 서버의 Python 버전과 정확하게 일치해야 한다는 것입니다. 일치하지 않으면 배포 후에 모호한 오류가 표시됩니다. 그러나 App Service 사이트 확장의 Python 버전은 python.org에 릴리스된 버전과 정확히 동일하기 때문에 로컬 개발에 사용할 호환되는 버전을 쉽게 얻을 수 있습니다.

### <a name="avoiding-virtual-environments"></a>가상 환경 방지

로컬에서 가상 환경을 사용할 경우 사이트에 필요한 종속성을 완전히 이해하는 데 도움이 되지만 App Service에서 가상 환경을 사용하는 것은 권장되지 않습니다. 대신, 기본 Python 폴더에 라이브러리를 설치하고 앱과 함께 배포하여 종속성 충돌을 방지합니다.

