---
title: "Visual Studio의 Python용 웹 응용 프로그램 템플릿 | Microsoft Docs"
description: "디버깅 구성 및 Azure App Service에 게시를 포함하여 Bottle, Flask 및 Django 프레임워크를 사용하는, Python으로 작성된 웹 응용 프로그램용 Visual Studio 템플릿에 대한 개요입니다."
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: b75aae5811fa2410cf169d3401184b8af7ca381d
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="python-web-application-project-templates"></a>Python 웹 응용 프로그램 프로젝트 템플릿

Visual Studio의 Python은 다양한 프레임워크를 처리하도록 구성할 수 있는 디버그 시작 관리자 및 프로젝트 템플릿을 통해 Bottle, Flask 및 Django 프레임워크에서 웹 프로젝트 개발을 지원합니다. Pyramid와 같은 다른 프레임워크에 대한 일반 **웹 프로젝트** 템플릿을 사용할 수도 있습니다.

Visual Studio는 자체 프레임워크를 포함하지 않습니다. 프레임워크는 프로젝트를 마우스 오른쪽 단추로 클릭하고 **Python > 프레임워크 설치/업그레이드...**를 선택하여 별도로 설치해야 합니다.

실행할 때 템플릿에서 만든 프로젝트(**파일 > 새로 만들기 > 프로젝트...**를 통해 액세스됨)는 임의로 선택된 로컬 포트로 웹 서버를 시작하며 디버그 시 기본 브라우저를 열고 Microsoft Azure로 직접 게시를 허용합니다.

![새 웹 프로젝트 템플릿](media/template-web-new-project.png)

Bottle, Flask 및 Django의 각 템플릿은 몇 가지 페이지 및 정적 파일이 있는 시작 사이트를 포함합니다. 이 코드를 통해 서버를 로컬(일부 설정을 해당 환경에서 가져와야 함)에서 충분히 실행하고 디버깅하며 Microsoft Azure에 배포([WSGI 앱](http://www.python.org/dev/peps/pep-3333/) 개체에 제공해야 함)할 수 있습니다.

프레임워크별 템플릿에서 프로젝트를 만들 때 pip를 사용하여 필요한 패키지를 설치할 수 있는 대화 상자가 나타납니다. 웹 프로젝트에 대해 [가상 환경](selecting-a-python-environment-for-a-project.md#using-virtual-environments)을 사용하여 웹 사이트를 게시할 때 올바른 종속성이 포함되도록 하는 것이 좋습니다.

![프로젝트 템플릿에 대해 필요한 패키지를 설치하는 대화 상자](media/template-web-requirements-txt-wizard.png)

Microsoft Azure App Service에 배포할 때는 [사이트 확장](https://aka.ms/PythonOnAppService)으로 Python 버전을 선택하고 패키지를 수동으로 설치합니다. 또한 Azure App Service는 Visual Studio에서 배포할 때 `requirements.txt` 파일에서 패키지를 자동으로 설치하지 **않으므로** [aka.ms/PythonOnAppService](https://aka.ms/PythonOnAppService)의 구성 세부 정보를 따릅니다.

Microsoft Azure Cloud Services는 `requirements.txt` 파일을 *지원합니다*. 자세한 내용은 [Azure Cloud Service 프로젝트](python-azure-cloud-service-project-template.md)를 참조하세요.

## <a name="debugging"></a>디버깅

디버깅을 위해 웹 프로젝트가 시작되면 Visual Studio는 로컬에서 웹 서버를 시작하고 해당 주소 및 포트에 기본 브라우저를 엽니다. 추가 옵션을 지정하려면 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**를 선택하고 **웹 시작 관리자** 탭을 선택합니다.

  ![일반 웹 템플릿에 대한 웹 시작 관리자 속성](media/template-web-launcher-properties.png)

**디버그** 그룹에서:

- **경로 검색**, **스크립트 인수**, **인터프리터 인수** 및 **인터프리터 경로**: 이러한 옵션은 [일반 디버깅](debugging-python-in-visual-studio.md)과 동일합니다.
- **URL 시작**: 브라우저에서 열리는 URL을 지정합니다. 기본값은 `localhost`입니다.
- **포트 번호**: URL에 지정되지 않은 경우 사용할 포트입니다(기본적으로 Visual Studio에서 자동으로 선택). 이 설정을 사용하면 로컬 디버그 서버에서 수신 대기하는 포트를 구성하기 위해 템플릿에서 사용하는 `SERVER_PORT` 환경 변수의 기본값을 재정의할 수 있습니다.

**서버 실행 명령** 및 **서버 디버그 명령** 그룹의 속성(후자는 아래 이미지에 표시됨)에 따라 웹 서버가 시작되는 방식이 결정됩니다. 많은 프레임워크에서는 현재 프로젝트 외부에서 스크립트를 사용해야 하기 때문에 여기에서 스크립트를 구성할 수 있으며 시작 모듈의 이름을 매개 변수로 전달할 수 있습니다.

- **명령**: Python 스크립트(`*.py` 파일), 모듈 이름(`python.exe -m module_name`에서와 같이) 또는 코드 한 줄 (`python.exe -c "code"`에서와 같이)일 수 있습니다. 드롭다운의 값은 이러한 형식 중 어떤 것이 의도되었는지를 나타냅니다.
- **인수**: 이러한 인수는 명령줄에서 명령 다음에 전달됩니다.
- **환경**: 환경 변수를 지정하는 줄 바꿈 문자로 구분된 `NAME=VALUE` 쌍 목록입니다. 이러한 변수는 포트 번호 및 검색 경로 등 환경을 수정할 수 있는 모든 속성 뒤에 설정되므로 이러한 값을 덮어쓸 수 있습니다.

MSBuild 구문으로 모든 프로젝트 속성 또는 환경 변수를 지정할 수 있습니다. 예를 들면 `$(StartupFile) --port $(SERVER_PORT)`입니다.
`$(StartupFile)`은 시작 파일에 대한 상대 경로이며 `{StartupModule}`은 시작 파일의 가져올 수 있는 이름입니다. `$(SERVER_HOST)` 및 `$(SERVER_PORT)`는 **시작 URL** 및 **포트 번호** 속성으로 자동으로 설정되거나 **환경** 속성으로 설정되는 일반 환경 변수입니다.

> [!Note]
> **서버 실행 명령**의 값은 **디버그 > 서버 시작** 명령이나 Ctrl-F5에 사용되며 **서버 디버그 명령** 그룹의 값은 **디버그 > 서버 디버그 시작** 명령이나 F5에 사용됩니다.

### <a name="sample-bottle-configuration"></a>샘플 Bottle 구성

**Bottle 웹 프로젝트** 템플릿은 필요한 구성을 수행하는 상용구 코드를 포함합니다. 그러나 가져온 bottle 앱에는 이 코드가 포함되어 있지 않을 수 있으며 이 경우 다음 설정으로 설치된 `bottle` 모듈을 사용하여 앱을 시작합니다.

- **서버 실행 명령** 그룹:
  - **명령**: `bottle`(모듈)
  - **인수**: `--bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

- **서버 디버그 명령** 그룹:
  - **명령**: `bottle`(모듈)
  - **인수** `--debug --bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

`--reload` 옵션은 디버깅에 Visual Studio를 사용할 때는 권장되지 않습니다.

### <a name="sample-pyramid-configuration"></a>샘플 Pyramid 구성

Pyramid 앱은 현재 `pcreate` 명령줄 도구를 사용하여 최적으로 만들어집니다. 앱을 만들었으면 [기존 Python 코드에서](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) 템플릿을 사용하여 가져올 수 있습니다. 그런 다음 **일반 웹 프로젝트** 사용자 지정을 선택하여 옵션을 구성합니다. 이러한 설정은 가상 환경의 `..\env`에 Pyramid가 설치되어 있다고 가정합니다.

- **디버그** 그룹:
  - **서버 포트**: 6543(또는.ini 파일에 구성된 모든 항목)

- **서버 실행 명령** 그룹:
  - 명령: `..\env\scripts\pserve-script.py`(스크립트)
  - 인수: `Production.ini`

- **서버 디버그 명령** 그룹:
    - 명령: `..\env\scripts\pserve-script.py`(스크립트)
    - 인수: `Development.ini`

> [!Tip]
> 일반적으로 Pyramid 앱은 소스 트리의 최상위 디렉터리보다 한 수준 더 깊기 때문에 프로젝트의 **작업 디렉터리** 속성을 구성해야 합니다.

### <a name="other-configurations"></a>기타 구성

공유하려는 다른 프레임워크 설정이 있거나 다른 프레임워크 설정을 요청하려면 [GitHub에서 문제](https://github.com/Microsoft/PTVS/issues)를 엽니다.

## <a name="publishing-to-azure-app-service"></a>Azure App Service에 게시

Azure App Service에 게시하는 기본적인 두 가지 방법이 있습니다. 첫째, [Azure 설명서](http://azure.microsoft.com/en-us/documentation/articles/web-sites-publish-source-control/)에 설명된 대로 소스 제어에서 배포를 다른 언어와 동일한 방식으로 사용할 수 있습니다. Visual Studio에서 직접 게시하려면 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

![프로젝트의 상황에 맞는 메뉴에서 게시 명령](media/template-web-publish-command.png)

명령을 선택하면 마법사가 웹 사이트 만들기 또는 게시 설정 가져오기, 수정된 파일 미리 보기 및 원격 서버에 게시 과정을 안내합니다.

App Service에서 사이트를 만들 때는 Python 및 사이트가 종속된 모든 패키지를 설치해야 합니다. 사이트를 먼저 게시할 수 있지만 Python을 구성할 때까지는 실행되지 않습니다.

App Service에 Python을 설치하려면 [사이트 확장](http://www.siteextensions.net/packages?q=Tags%3A%22python%22)(siteextensions.net)을 사용하는 것이 좋습니다. 이러한 확장은 Python [공식 릴리스](https://www.python.org)의 복사본이며 Azure App Service용으로 최적화되어 다시 패키지되었습니다.

[Azure Portal](https://portal.azure.com/)을 통해 사이트 확장을 배포할 수 있습니다. App Service에 대한 **개발 도구 > 확장** 블레이드를 선택하고 **추가**를 선택한 다음 목록을 스크롤하여 Python 항목을 찾습니다.

![Azure Portal에서 사이트 확장 추가](media/template-web-site-extensions.png)

JSON 배포 템플릿을 사용하는 경우 사이트 리소스로 사이트 확장을 지정할 수 있습니다.

```json
{
    "resources": [
    {
        "apiVersion": "2015-08-01",
        "name": "[parameters('siteName')]",
        "type": "Microsoft.Web/sites",
        ...
    },
    "resources": [
    {
        "apiVersion": "2015-08-01",
        "name": "python352x64",
        "type": "siteextensions",
        "properties": { },
        "dependsOn": [
            "[resourceId('Microsoft.Web/sites', parameters('siteName'))]"
        ]
    },
    ...
}
```

마지막으로, [개발 콘솔](https://github.com/projectkudu/kudu/wiki/Kudu-console)을 통해 로그인하고 여기에서 사이트 확장을 설치할 수 있습니다.

현재, 패키지 설치에 권장되는 방법은 사이트 확장을 설치하고 pip를 직접 실행한 후 배포 콘솔을 사용하는 것입니다. Python의 전체 경로를 사용하는 것이 중요하며, 그렇지 않으면 잘못된 경로를 실행할 수 있으며 일반적으로 가상 환경을 사용할 필요가 없습니다. 예:

```command
c:\Python35\python.exe -m pip install -r D:\home\site\wwwroot\requirements.txt

c:\Python27\python.exe -m pip install -r D:\home\site\wwwroot\requirements.txt
```

Azure App Service에 배포하면 사이트가 Microsoft IIS 뒤에서 실행됩니다. 사이트가 IIS와 함께 작동하도록 하려면 최소한 `web.config` 파일을 추가해야 합니다. 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목...**(아래 대화 상자 참조)을 선택하면 사용할 수 있는 일반적인 배포 대상에 제공되는 템플릿이 있으며 이러한 구성을 다른 용도로 쉽게 수정할 수 있습니다. 사용 가능한 구성 설정에 대한 자세한 내용은 [IIS 구성 참조](https://www.iis.net/configreference)를 참조하세요.

![Azure 항목 템플릿](media/template-web-azure-items.png)

사용 가능한 항목은 다음과 같습니다.

- Azure web.config(FastCGI): 앱이 들어오는 연결을 처리하기 위해 [WSGI](https://wsgi.readthedocs.io/en/latest/) 개체를 제공할 때 `web.config` 파일을 추가합니다.
- Azure web.config(HttpPlatformHandler): 앱이 들어오는 연결에 대한 소켓을 수신할 때 `web.config` 파일을 추가합니다.
- Azure 정적 파일 web.config: 위의 `web.config` 파일 중 하나가 있을 경우 해당 파일을 하위 디렉터리에 추가하여 앱에서 처리하지 않도록 합니다.
- Azure의 원격 디버깅 web.config: WebSocket을 통해 원격 디버깅에 필요한 파일을 추가합니다.
- 웹 역할 지원 파일: Cloud Service 웹 역할에 대한 기본 배포 스크립트를 포함합니다.
- 작업자 역할 지원 파일: Cloud Service 작업자 역할에 대한 기본 배포 및 시작 스크립트를 포함합니다.

프로젝트에 디버깅 `web.config` 템플릿을 추가하고 Python 원격 디버깅을 사용하려는 경우 “디버그” 구성에서 사이트를 게시해야 합니다. 이 설정은 현재 활성 솔루션 구성과 별개이며 항상 기본값인 “릴리스”로 설정됩니다. 이를 변경하려면 게시 마법사에서 **설정** 탭을 열고 **구성** 콤보 상자를 사용합니다(Azure Web Apps를 만들고 배포하는 방법에 대한 자세한 내용은 [Azure 설명서](https://azure.microsoft.com/develop/python/) 참조).

![게시 구성 변경](media/template-web-publish-config.png)

**Microsoft Azure 클라우드 서비스 프로젝트로 변환** 명령(아래 이미지)은 클라우드 서비스 프로젝트를 솔루션에 추가합니다. 이 프로젝트에는 사용되는 가상 컴퓨터 및 서비스에 대한 배포 설정 및 구성이 포함됩니다. 클라우드 서비스에 배포하려면 클라우드 프로젝트에서 **Publish** 명령을 사용합니다. Python 프로젝트에서 **Publish** 명령을 사용하면 여전히 웹 사이트에 배포됩니다. 자세한 내용은 [Azure Cloud Service 프로젝트](python-azure-cloud-service-project-template.md)를 참조하세요.

![Microsoft Azure Cloud Service 프로젝트 명령으로 변환](media/template-web-convert-menu.png)
