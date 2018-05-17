---
title: Azure Functions 소개
description: Mac용 Visual Studio에서 Azure Functions 사용
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 25CD47A4-5B32-4734-8EF3-E24A02AABF29
ms.openlocfilehash: 5d787efbd09ad7f2d4a1f5f72b8f1493d8c6c587
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="introduction-to-azure-functions"></a>Azure Functions 소개

Azure Functions는 클라우드에서 명시적인 인프라 프로비전이나 관리 없이 이벤트 중심 코드 조각을 만들고 실행하는 방법입니다. Azure Functions에 대한 자세한 내용은 [Azure Functions 설명서](https://docs.microsoft.com/azure/azure-functions/)를 참조하세요.

## <a name="requirements"></a>요구 사항

Azure 함수 도구는 **Mac용 Visual Studio 7.5**에 포함됩니다.

함수를 만들어 배포하려면 [https://azure.com/free](https://azure.com/free)에서 무료로 제공하는 Azure 구독도 필요합니다.

## <a name="creating-your-first-azure-functions-project"></a>Azure Functions 프로젝트 처음 만들기

1. Mac용 Visual Studio에서 **파일 > 새 솔루션...** 을 선택합니다. 
2. 새 프로젝트 대화 상자에서 **클라우드 > 일반**의 Azure Functions 템플릿을 선택하고 **다음**을 클릭합니다.

    ![Azure Functions 옵션을 표시하는 새 프로젝트 대화 상자](media/azure-functions-image1.png)

3. **프로젝트 이름**을 입력하고 **만들기**를 선택합니다.

Mac용 Visual Studio가 기본 HttpTrigger 함수가 포함된 .NET Standard 프로젝트를 만듭니다. 여기에는 **Newtonsoft.Json** 패키지뿐 아니라 여러 **AzureWebJobs** 패키지에 대한 NuGet 참조가 포함됩니다.

![템플릿의 새 Azure 함수를 표시하는 Mac용 Visual Studio 편집기](media/azure-functions-newproj.png)

새 프로젝트는 다음 파일을 포함합니다.

* **HttpTrigger.cs** – 이 클래스는 HTTP 트리거 함수에 대한 상용구 코드를 포함합니다. 여기에는 함수 이름이 있는 **FunctionName** 특성과, 이 함수가 HTTP 요청에서 트리거됨을 지정하는 **HttpTrigger** 트리거 특성이 포함됩니다. 함수 메서드에 대한 자세한 내용은 [Azure Functions C# 개발자 참조](https://docs.microsoft.com/azure/azure-functions/functions-dotnet-class-library) 문서를 참조하세요.
* **host.json** – 이 파일은 함수 호스트에 대한 전역 구성 옵션을 설명합니다. 이 파일의 예제 파일과 사용 가능한 설정 정보는 [Azure Functions에 대한 host.json 참조](https://docs.microsoft.com/azure/azure-functions/functions-host-json)를 참조하세요.
* **local.settings.json** – 이 파일은 함수를 로컬로 실행하기 위한 모든 설정을 포함합니다. 이러한 설정은 Azure Functions Core Tools에서 사용됩니다. 자세한 내용은 Azure Functions Core Tools 문서의 [로컬 설정 파일](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local#local-settings-file)을 참조하세요.

Mac용 Visual Studio에서 새 Azure Functions 프로젝트를 만들었으므로 이제 로컬 컴퓨터에서 기본 HTTP 트리거 함수를 테스트할 수 있습니다.

<!--
## Create an Azure storage account

[Describe why this step is necessary and what it does]

1. Log on to your account at [https://portal.azure.com](https://portal.azure.com).
2. Under the **Favorites** section, located on the left of the screen, select **Storage Accounts**:
    ![]()
3. Select **Add** to create a new storage account:
    ![]()
4. Enter a globally unique name for the **Name** and reuse it for the **Resource group**. You can keep all the other items as their default.
    ![]()
5. Click **Create**. It might take a few minutes to create the storage account. You'll get a notification once it has been successfully created.
6. Select the **Go to resource** button from the notification:
    ![]()
-->

## <a name="testing-the-function-locally"></a>로컬로 함수 테스트

Mac용 Visual Studio에서 Azure Functions 지원을 통해 로컬 개발 컴퓨터에서 함수틀 테스트 및 디버그할 수 있습니다.

1. 함수를 로컬로 테스트하려면 Mac용 Visual Studio에서 **실행** 단추를 누릅니다.

    ![Mac용 Visual Studio에서 디버그 시작](media/azure-functions-run.png)

1. Azure Functions에서 프로젝트를 실행하면 로컬 디버그가 시작되고 다음 이미지에서처럼 새 터미널 창이 열립니다. 

    ![함수 출력을 표시하는 터미널 창 ](media/azure-functions-terminal.png) 

    출력에서 URL을 복사합니다.

3. 브라우저의 주소 표시줄에 HTTP 요청에 대한 URL을 붙여 넣습니다. `?name=<yourname>` 쿼리 문자열을 URL의 마지막에 추가하고 요청을 실행합니다. 다음 이미지에서는 함수가 반환한 로컬 GET 요청에 대한 응답을 브라우저에 보여 줍니다.

    ![브라우저의 http 요청](media/azure-functions-httpreq.png)

## <a name="creating-a-new-function"></a>새 함수 만들기

함수 템플릿을 사용하면 가장 일반적인 트리거 및 템플릿을 통해 새 함수를 신속하게 만들 수 있습니다. 새 Azure Functions 프로젝트를 만들 때는 HttpTrigger 함수가 자동으로 포함됩니다. 다른 유형의 함수를 만들려면 다음을 수행합니다.

1. **HttpTrigger.cs** 파일을 마우스 오른쪽 단추로 클릭하고 **제거**를 선택하여 제거합니다. 다음 경고에서 **삭제**를 선택하여 프로젝트에서 제거합니다.

    ![프로젝트에서 파일을 제거하는 대화 상자](media/azure-functions-remove.png)

2. 새 함수를 추가하려면 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고**추가 > 함수 추가...** 를 선택합니다.

    ![새 함수를 추가하기 위한 컨텍스트 작업](media/azure-functions-addnew.png)

3. **새 Azure 함수** 대화 상자에서 필요한 함수를 선택합니다.

    ![새 Azure 함수 대화 상자](media/azure-functions-newfunction.png)

    다음 섹션에 Azure 함수 템플릿 목록이 제공됩니다.

## <a name="available-function-templates"></a>사용 가능한 함수 템플릿

- **HTTP** – HTTP 요청을 사용하여 코드 실행을 트리거합니다. 다음 HTTP 트리거에 대한 명시적 템플릿이 있습니다.
    - Http GET CRUD
    - Http POST CRUD
    - 매개 변수가 있는 http 트리거
    - HTTP 트리거
- **Timer** - 미리 정의된 일정에 따라 정리 또는 기타 일괄 처리 작업을 실행합니다. 이 템플릿에는 이름과 일정 등 두 필드가 있고 6개 필드 CRON 식입니다. 자세한 내용은 [Azure functions 문서의 Timer 부분](https://docs.microsoft.com/azure/azure-functions/functions-create-scheduled-function)을 참조하세요.
- **GitHub 트리거** - GitHub 리포지토리에서 발생하는 이벤트에 응대합니다. 자세한 내용은 [Azure functions 문서의 GitHub 부분](https://docs.microsoft.com/azure/azure-functions/functions-create-github-webhook-triggered-function)을 참조하세요.
    - GitHub commenter – 문제 또는 끌어오기 요청에 대한 GitHub 웹후크를 받고 주석을 추가할 때 실행되는 함수입니다.
    - GitHub WebHook – 이 함수는 GitHub 웹후크 요청을 받을 때 실행됩니다.
- **Blob Trigger** – 컨테이너에 추가되는 Azure Storage BLOB를 처리합니다. 함수 이름 외에도 이 템플릿은 경로 및 연결 속성을 사용합니다. 경로 속성은 트리거가 모니터링할 저장소 계정 내의 경로입니다. 연결 계정은 저장소 계정 연결 문자열을 포함하는 앱 설정의 이름입니다. 자세한 내용은 [Azure Functions BLOB 저장소 문서](https://docs.microsoft.com/azure/azure-functions/functions-create-storage-blob-triggered-function)를 참조하세요.
- **Queue Trigger** – Azure Storage 큐에 도착하면 메시지에 응답하는 함수입니다. 함수 이름 외에도 이 템플릿은 **경로**(메시지를 읽을 큐의 이름)와 저장소 계정 **연결**(저장소 계정 연결 문자열을 포함하는 앱 설정의 이름)을 사용합니다. 자세한 내용은 [Azure Functions 문서의 큐 저장소 부분](https://docs.microsoft.com/azure/azure-functions/functions-create-storage-queue-triggered-function)을 참조하세요.
- **일반 웹후크** – 웹후크를 지원하는 서비스에서 요청을 수신할 때마다 실행되는 간단한 함수입니다. 자세한 내용은 [Azure Functions 문서의 일반 웹후크 부분](https://docs.microsoft.com/azure/azure-functions/functions-create-generic-webhook-triggered-function)을 참조하세요.
- **Image Resizer** - Blob가 컨테이너에 추가될 때마다 크기 조정된 이미지를 만드는 함수입니다. 이 템플릿은 트리거, 소형 이미지 출력, 중간 이미지 출력을 위해 경로 및 연결을 사용합니다.
- **SAS token** – 지정된 Azure Storage 컨테이너 및 Blob 이름에 대한 SAS 토큰을 생성하는 함수입니다. 함수 이름 외에도 이 템플릿은 경로 및 연결 속성을 사용합니다. 경로 속성은 트리거가 모니터링할 저장소 계정 내의 경로입니다. 연결 계정은 저장소 계정 연결 문자열을 포함하는 앱 설정의 이름입니다. **액세스 권한**도 설정해야 합니다. 권한 부여 수준은 함수에 API 키가 필요한지 여부, 사용할 키, 함수의 함수 키 사용, 관리자의 마스터 키 사용을 제어합니다. 자세한 내용은 [SAS 토큰을 생성하기 위한 C# Azure 함수](https://azure.microsoft.com/resources/samples/functions-dotnet-sas-token/) 샘플을 참조하세요.
- **영속 함수 오케스트레이션** – 영속 함수를 사용하면 서버가 없는 환경에서 상태 저장 함수를 작성할 수 있습니다. 이 확장은 상태, 검사점, 다시 시작을 관리합니다. 자세한 내용은 Azure Functions 설명서의 [영속 함수](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview) 부분을 참조하세요.