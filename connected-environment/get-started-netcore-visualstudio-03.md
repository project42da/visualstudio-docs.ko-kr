---
title: Visual Studio가 있는 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 .NET Core 개발 환경 만들기 - 3단계 - Kubernetes 개발 환경 만들기 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: 6226340b1744e95bbb375d47213ae00bb9e76565
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>.NET Core 및 Visual Studio를 사용하여 연결된 환경에서 시작

이전 단계: [ASP.NET 웹앱 만들기](get-started-netcore-visualstudio-02.md)

## <a name="create-a-dev-environment-in-azure"></a>Azure에서 개발 환경 만들기
연결된 환경을 사용하여 Azure에서 완벽히 관리되고 개발에 최적화된 Kubernetes 기반 개발 환경을 만들 수 있습니다. 방금 만든 프로젝트를 열고 아래와 같은 시작 설정 드롭다운 목록에서 **AKS에 대한 연결된 환경**을 선택합니다.

![](images/LaunchSettings.png)

다음에 표시되는 대화 상자에서 적절한 계정으로 로그인한 것을 확인한 다음, 기존 개발 환경을 선택하거나 **<AKS에 대한 새 연결된 환경 만들기...>** 를 선택해 새로 만듭니다.

![](images/ConnectedEnvDialog.png)

제공된 기본값을 사용하거나 원하는 대로 조정할 수 있습니다. 값이 적절하게 설정된 경우 **확인**을 클릭합니다.

![](images/NewEnvDialog.png)

**공간** 드롭다운 목록이 현재 `mainline`으로 기본 설정된 이전 대화 상자에서 이를 나중에 더 자세히 논의하겠습니다. 웹앱이 공용 끝점을 통해 액세스할 수 있도록 **공개적으로 액세스 가능한** 확인란을 확인합니다. 이는 필요치 않으나 나중에 이 연습에서 몇 가지 개념을 보여주기 위해서는 도움이 될 수 있습니다. 그러나 Visual Studio를 사용하여 웹 사이트를 디버그할 수 있는지 여부는 걱정하지 마십시오.

![](images/ConnectedEnvDialog2.png)

개발 환경을 선택하거나 만들려면 **확인**을 클릭합니다. 이를 완수하기 위해 백그라운드 작업이 시작되며 완료하는 데 몇 분이 걸립니다. 상태줄 왼쪽 하단 구석에 있는 **백그라운드 작업** 아이콘을 커서로 가리켜 여전히 만들어지고 있는지 확인할 수 있습니다(아래 참조).

![](images/BackgroundTasks.png)

> [!Note]
개발 환경이 제대로 만들어지기까지 응용 프로그램을 디버그할 수 없습니다.

## <a name="look-at-the-files-added-to-project"></a>프로젝트에 추가된 파일 검토
만들어질 개발 환경을 기다리는 동안 개발 환경을 사용하기 위해 선택한 경우 프로젝트에 추가된 파일을 살펴봅시다.

첫째, `charts`이라는 폴더가 추가되고 이 폴더 안에 응용 프로그램에 대한 [Helm 차트](https://docs.helm.sh)가 스캐폴드된 것을 확인할 수 있습니다. 이러한 파일은 개발 환경에 응용 프로그램을 배포하는 데 사용됩니다.

`Dockerfile`이라는 파일이 추가된 것을 확인합니다. 이 파일에는 응용 프로그램을 표준 Docker 형식으로 패키지하는 데 필요한 정보가 있습니다. `HeaderPropagation.cs` 파일도 만들어지면 나중에 연습에서 이 파일을 설명하겠습니다. 

마지막으로 응용 프로그램이 공용 끝점을 통해 액세스 가능한지 여부와 같은 개발 환경에서 필요한 구성 정보가 포함된 `vsce.yaml`이라는 파일이 표시됩니다.

![](images/ProjectFiles.png)

> [!div class="nextstepaction"]
> [Kubernetes에서 컨테이너 디버그](get-started-netcore-visualstudio-04.md)