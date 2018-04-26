---
title: 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 .NET Core 개발 환경 만들기 - 3단계 - ASP.NET Core 웹앱 만들기 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: 72c7df0a82b91f7b4665b8b7e2cecdfc2eea26cf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core"></a>.NET Core를 사용하여 연결된 환경에서 시작

이전 단계: [Azure에서 Kubernetes 개발 환경 만들기](get-started-netcore-02.md)

## <a name="create-an-aspnet-core-web-app"></a>ASP.NET Core 웹앱 만들기
[.NET Core](https://www.microsoft.com/net)가 설치된 경우 `webfrontend`이라는 폴더에서 ASP.NET Core 웹앱을 빠르게 만들 수 있습니다.
```cmd
dotnet new mvc --name webfrontend
```

또는 https://github.com/Azure/vsce로 이동하여 **GitHub에서 샘플 코드를 다운로드**하고 **복제 또는 다운로드**를 선택하여 로컬 환경에 GitHub 리포지토리를 다운로드합니다. 이 가이드에 대한 코드는 `vsce/samples/dotnetcore/getting-started/webfrontend`에 있습니다.

[!INCLUDE[](includes/vsce-init.md)]

[!INCLUDE[](includes/ensure-env-created.md)]

[!INCLUDE[](includes/build-and-run-in-k8s-cli.md)]

## <a name="update-a-content-file"></a>콘텐츠 파일 업데이트
연결된 환경은 Kubernetes에서 실행되는 코드를 가져오는 방법에 대한 것이 아니라 코드 변경 내용이 클라우드의 Kubernetes 환경에 적용되는지 빠르고 반복적으로 확인할 수 있는 방법에 대한 것입니다.

1. 파일 `./Views/Home/Index.cshtml`을 찾아 HTML을 편집합니다. 예를 들어 `<h2>Application uses</h2>`이라고 쓰인 70번째 줄을 `<h2>Hello k8s in Azure!</h2>`와 같은 것으로 바꿉니다.
1. 파일을 저장합니다. 잠시 후 실행 중인 컨테이너에서 파일이 업데이트됐다는 메시지가 터미널 창에 표시됩니다.
1. 브라우저로 이동해서 페이지를 새로 고칩니다. 업데이트된 HTML을 표시하는 웹 페이지가 표시돼야 합니다.

어떻게 된 것입니까? HTML 및 CSS 같은 콘텐츠 파일에 대한 편집은 .NET Core 웹앱에서 다시 컴파일을 요구하지 않으므로 `vsce up` 활성 명령은 모든 수정된 콘텐츠 파일을 Azure에서 실행 중인 컨테이너와 자동으로 동기화합니다. 따라서 콘텐츠 편집을 확인하는 빠른 방법을 제공합니다.

## <a name="update-a-code-file"></a>코드 파일 업데이트
코드 파일 업데이트는 .NET Core 앱이 업데이트된 응용 프로그램 이진 파일을 다시 빌드하고 생성해야 하기 때문에 좀 더 많은 작업이 요구됩니다.

1. 터미널 창에서 `Ctrl+C`을 눌러(`vsce up`를 중단합니다).
1. `Controllers/HomeController.cs`이라는 코드 파일을 열고 정보 페이지가 `ViewData["Message"] = "Your application description page.";`와 같이 표시되는 메시지를 편집합니다.
1. 파일을 저장합니다.
1. 터미널 창에서 `vsce up`을 실행합니다. 

이렇게 해서 컨테이너 이미지를 다시 빌드하고 Helm 차트를 다시 배포합니다. 코드 변경 내용이 실행 중인 응용 프로그램에 적용되는지 확인하려면 웹앱의 정보 메뉴로 이동합니다.


그러나 코드를 개발하기 위해 *더 빠른 메서드*가 있습니다. 이는 다음 섹션에서 살펴보겠습니다. 
> [!div class="nextstepaction"]
> [Kubernetes에서 컨테이너 디버그](get-started-netcore-04.md)

