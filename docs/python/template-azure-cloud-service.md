---
title: "Python용 Azure Cloud Service 프로젝트 템플릿 | Microsoft Docs"
ms.custom: 
ms.date: 4/10/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2ce82ee-8c73-419a-bbd2-4c3513fd394d
caps.latest.revision: 11
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 9328c347d548a03a536cea16bd5851817c03d5a2
ms.openlocfilehash: 5dd1c40c925327c9494e3a334cdf348692a4981d
ms.lasthandoff: 04/10/2017

---

# <a name="azure-cloud-service-projects-for-python"></a>Python용 Azure Cloud Service 프로젝트

Visual Studio는 Python을 사용하여 Azure Cloud Services 만들기를 시작하는 데 도움이 되는 템플릿을 제공합니다.

[Cloud Service](http://go.microsoft.com/fwlink/?LinkId=306052)는 각각 개념적으로 별개의 작업을 수행하지만 크기 조정 필요에 따라 가상 컴퓨터 간에 별도로 복제할 수 있는 여러 개의 *작업자 역할* 및 *웹 역할*로 구성됩니다. 웹 역할은 프런트 엔드 웹 응용 프로그램의 호스팅을 제공합니다. Python에 관해서는 WSGI를 지원하는 웹 프레임워크를 사용하여 이러한 응용 프로그램([웹 프로젝트 템플릿](template-web.md)에서 지원하는)을 작성할 수 있습니다. 작업자 역할은 사용자와 직접 상호 작용하지 않는 장기적으로 실행되는 프로세스 용도로 사용됩니다. 일반적으로 [데이터](http://go.microsoft.com/fwlink/?LinkId=401571) 및 [앱 서비스](http://go.microsoft.com/fwlink/?LinkId=401572) 라이브러리를 활용하며 `pip install`&nbsp;[`azure`](http://pypi.org/project/azure)와 함께 설치할 수 있습니다.

이 항목에서는 Visual Studio 2017(이전 버전과 유사하지만 몇 가지 차이점이 있음)에서 프로젝트 템플릿 및 기타 지원에 대해 자세히 알아봅니다. Python에서 Azure로 작업하는 방법에 대한 자세한 내용은 [Azure Python 개발자 센터](http://go.microsoft.com/fwlink/?linkid=254360)(영문)를 참조하세요.

## <a name="create-a-project"></a>프로젝트 만들기

1. Cloud Service 템플릿을 사용하는 데 필요한 [Visual Studio용 Azure .NET SDK](https://www.visualstudio.com/vs/azure-tools/)를 설치합니다.
1. Visual Studio에서 **파일 > 새로 만들기 > 프로젝트...**를 선택한 후 "Azure Python"을 검색하고 목록에서 **Azure Cloud Service**를 선택합니다.

    ![Python용 Azure 클라우드 프로젝트 템플릿](media/template-azure-cloud-project.png)

1. 포함할 역할을 하나 이상 선택합니다. 클라우드 프로젝트는 서로 다른 언어로 작성된 역할을 결합할 수 있으므로 가장 적합한 언어로 응용 프로그램의 각 부분을 쉽게 작성할 수 있습니다. 이 대화 상자를 완료한 후 프로젝트에 새 역할을 추가하려면 솔루션 탐색기에서 **역할**을 마우스 오른쪽 단추로 클릭하고 **추가** 아래 항목 중 하나를 선택합니다.

    ![Azure Cloud 프로젝트 템플릿에서 역할 추가](media/template-azure-cloud-service-project-wizard.png)

1. 개별 역할 프로젝트가 만들어지면 Django, Bottle 또는 Flask 프레임워크 중 하나를 사용하는 역할을 선택한 경우 이에 대한 추가 Python 패키지를 설치하라는 메시지가 표시될 수 있습니다.

1. 프로젝트에 새 역할을 추가하면 몇 가지 구성 지침이 표시됩니다. 이러한 내용은 일반적으로 불필요하지만 향후 프로젝트의 사용자 지정에 도움이 될 수 있습니다. 여러 역할을 동시에 추가할 때는 마지막 역할에 대한 지침만 열려 있습니다. 그러나 역할의 루트 또는 `bin` 폴더에 있는 각 `readme.mht` 파일에서 다른 역할에 대한 지침 및 문제 해결 팁을 찾을 수 있습니다.

1. 프로젝트의 `bin` 폴더에는 Python, 프로젝트의 [requirements.txt](#dependencies) 파일 설치 및 IIS 설정(필요한 경우)을 포함하여 원격 가상 컴퓨터를 구성하는 데 사용되는 하나 또는 두 개의 PowerShell 스크립트도 포함되어 있습니다. 대부분의 일반적인 옵션은 다른 방법으로 관리할 수 있지만 배포에 따라 원하는 대로 이러한 파일을 편집할 수 있습니다(아래 [역할 배포 구성 ](#configuring-role-deployment) 참조). 옵션을 사용할 수 없는 경우 레거시 구성 스크립트가 대신 사용되므로 이러한 파일은 제거하지 않는 것이 좋습니다.

    ![작업자 역할 지원 파일](media/template-azure-cloud-service-worker-role-support-files.png)

    이러한 구성 스크립트를 새 프로젝트에 추가하려면 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목...**을 선택하고 **웹 역할 지원 파일** 또는 **작업자 역할 지원 파일**을 선택합니다.
   

## <a name="configuring-role-deployment"></a>역할 배포 구성

역할 프로젝트의 `bin` 폴더에 있는 PowerShell 스크립트는 해당 역할의 배포를 제어하며 편집하여 구성을 사용자 지정할 수 있습니다.

- `ConfigureCloudService.ps1`은 웹 및 작업자 역할에 사용되며 일반적으로 종속성을 설치 및 구성하고 Python 버전을 설정합니다.
- `LaunchWorker.ps1`은 작업자 역할에만 사용되며 시작 동작을 변경하거나 명령줄 인수를 추가하거나 환경 변수를 추가하는 데 사용됩니다.

두 파일 모두 사용자 지정을 위한 지침을 포함합니다. 또한 주 클라우드 서비스 프로젝트의 `ServiceDefinition.csdef` 파일에 다른 작업을 추가하고 `PYTHON` 변수를 설치된 `python.exe`(또는 이와 동등한) 경로로 설정하여 사용자 고유의 Python 버전을 설치할 수도 있습니다. `PYTHON`이 설정되면 NuGet에서 Python이 설치되지 않습니다.

다음과 같이 추가 구성을 수행할 수 있습니다.

1. 프로젝트의 루트 디렉터리에 있는 `requirements.txt` 파일을 업데이트하고 `pip`를 사용하여 패키지를 설치합니다. `ConfigureCloudService.ps1` 스크립트는 이 파일을 배포에 설치합니다.
1. `web.config` 파일(웹 역할) 또는 `ServiceDefinition.csdef` 파일(작업자 역할)의 `Runtime` 섹션을 수정하여 환경 변수를 설정합니다.
1. `ServiceDefinitions.csdef` 파일의 `Runtime/EntryPoint` 섹션에서 명령줄을 수정하여 작업자 역할에 사용할 스크립트 및 인수를 지정합니다.
1. `web.config` 파일을 통해 웹 역할에 대한 기본 처리기 스크립트를 설정합니다.

## <a name="testing-role-deployment"></a>역할 배포 테스트

역할을 작성하는 동안 Cloud Service 에뮬레이터를 사용하여 클라우드 프로젝트를 로컬로 테스트할 수 있습니다. 에뮬레이터는 Azure SDK 도구에 포함되며 Cloud Service가 Azure에 게시될 때 제한된 버전의 환경이 사용됩니다.

에뮬레이터를 시작하려면 먼저 **시작 프로젝트로 설정**을 마우스 오른쪽 단추로 클릭하고 선택하여 클라우드 프로젝트가 솔루션에서 시작 프로젝트인지 확인합니다. 그런 다음 **디버그 > 디버깅 시작**(F5) 또는 **디버그 > 디버깅하지 않고 시작**(Ctrl+F5)을 선택합니다.

에뮬레이터의 제한으로 인해 Python 코드를 디버깅할 수 없습니다. 따라서 독립적으로 실행하여 역할을 디버깅한 후 게시하기 전에 통합 테스트에 대해 에뮬레이터를 사용하는 것이 좋습니다.


## <a name="deploying-a-role"></a>역할 배포

**게시** 마법사를 열려면 솔루션 탐색기에서 역할 프로젝트를 선택하고 주 메뉴에서 **빌드 > 게시**를 선택하거나 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

게시 프로세스는 두 단계로 구성됩니다. 먼저, Visual Studio에서 클라우드 서비스에 대한 모든 역할이 들어 있는 단일 패키지를 만듭니다. 이 패키지는 Azure에 배포된 것이며 각 역할에 대해 하나 이상의 가상 컴퓨터를 초기화하고 소스를 배포합니다.

각 가상 컴퓨터가 활성화되면 `ConfigureCloudService.ps1` 스크립트를 실행하고 모든 종속성을 설치합니다. 기본적으로 이 스크립트는 [nuget](https://www.nuget.org/packages?q=Tags%3A%22python%22+Authors%3A%22Python+Software+Foundation%22)에서 최신 버전의 Python과 `requirements.txt` 파일에 지정된 패키지를 설치합니다. 

마지막으로 작업자 역할은 Python 스크립트 실행을 시작하는 `LaunchWorker.ps1`을 실행하고 웹 역할은 IIS를 시작하고 웹 요청 처리를 시작합니다.


## <a name="dependencies"></a>종속성

Cloud Service의 경우 `ConfigureCloudService.ps1` 스크립트는 `pip`를 사용하여 Python 종속성 집합을 설치합니다. 이러한 내용은 `requirements.txt` 이름의 파일에 지정해야 합니다(`ConfigureCloudService.ps1`을 수정하여 사용자 지정 가능). 파일은 초기화의 일부로 `pip install -r requirements.txt`에서 실행됩니다.

Cloud Service 인스턴스는 C 컴파일러를 포함하지 않으므로 C 확장명이 있는 모든 라이브러리는 사전 컴파일된 이진 파일을 제공해야 합니다.

pip 및 해당 종속성과 `requirements.txt`의 패키지는 자동으로 다운로드되며 청구 가능한 대역폭 사용량으로 계산할 수 있습니다. `requirements.txt` 파일 관리에 대한 자세한 내용은 [필수 패키지 관리](python-environments.md#managing-required-packages)를 참조하세요.

## <a name="troubleshooting"></a>문제 해결

배포 후 웹 또는 작업자 역할이 올바르게 동작하지 않으면 다음을 확인하세요.

- Python 프로젝트는 다음 이상을 포함하는 bin\ 폴더를 포함합니다.
    - `ConfigureCloudService.ps1`
    - `LaunchWorker.ps1`(작업자 역할)
    - `ps.cmd`

- Python 프로젝트는 모든 종속성(또는 휠 파일의 컬렉션)이 나열된 `requirements.txt` 파일을 포함합니다.
- Cloud Service에서 원격 데스크톱을 사용하고 로그 파일을 조사합니다.
- `ConfigureCloudService.ps1` 및 `LaunchWorker.ps1`에 대한 로그는 원격 컴퓨터의 `C:\Resources\Directory\%RoleId%.DiagnosticStore\LogFiles` 폴더에 저장됩니다.
- 웹 역할은 `web.config`에 구성된 경로 즉, `WSGI_LOG` appSetting의 경로에 대해 추가 로그를 작성할 수 있습니다. 대부분의 일반 IIS 또는 FastCGI 로깅도 작동합니다.
- 현재는 `LaunchWorker.ps1.log` 파일이 Python 작업자 역할로 표시된 출력이나 오류를 볼 수 있는 유일한 방법입니다.
