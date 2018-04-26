---
title: Visual Studio가 있는 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 .NET Core 개발 환경 만들기 - 1단계 - 도구 설치 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 04/05/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: b2edc476ffd4648f9ddb0e3d076f8eb400458242
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>.NET Core 및 Visual Studio를 사용하여 연결된 환경에서 시작

이 가이드에서는 다음 방법을 알아봅니다.

1. 개발에 최적화된 Azure에서 Kubernetes 기반 환경을 만듭니다.
1. Visual Studio을 사용하여 컨테이너에서 코드를 반복해서 개발합니다.
1. 다른 서비스를 호출하려면 두 개의 별도 서비스 및 Kubernetes DNS 서비스 검색을 독립적으로 개발합니다.
1. 팀 환경에서 코드를 생산적으로 개발하고 테스트합니다.

[!INCLUDE[](includes/see-troubleshooting.md)]

## <a name="install-the-connected-environment-cli"></a>연결된 환경 CLI 설치
연결된 환경에는 최소한 로컬 컴퓨터 설치가 필요합니다. 대부분의 개발 환경의 구성은 클라우드에 저장되며 다른 사용자와 공유할 수 있습니다.

1. [연결된 환경 CLI 설치관리자](https://aka.ms/get-vsce-windows)를 다운로드하고 실행합니다. 

## <a name="get-kubernetes-debugging-tools"></a>Kubernetes 디버깅 도구 가져오기
연결된 환경 CLI를 독립 실행형 도구로 사용할 수 있지만 **VS Code** 또는 **Visual Studio**를 사용하는 .NET Core 및 Node.js 개발자는 **Kubernetes 디버깅** 같은 다양한 기능을 사용할 수 있습니다.

### <a name="visual-studio-debugging"></a>Visual Studio 디버깅 
1. 최신 버전의 [Visual Studio 2017](https://www.visualstudio.com/vs/) 설치
1. Visual Studio 설치 관리자는 다음 워크로드가 선택됐는지 확인합니다.
    * ASP.NET 및 웹 개발
1. [연결된 환경에 대한 Visual Studio 확장](https://aka.ms/get-vsce-visualstudio) 설치

Visual Studio를 사용하여 ASP.NET 웹앱 만들 준비가 됐습니다.

> [!div class="nextstepaction"]
> [ASP.NET 웹앱 만들기](get-started-netcore-visualstudio-02.md)
