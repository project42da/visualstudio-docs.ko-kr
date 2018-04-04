---
title: Visual Studio 연결된 환경 | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: ghogen
ms.openlocfilehash: c1ce010b6ab36c1577953ab527f3c17d5e68def8
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="vs-connected-environment-for-azure-container-service-aks-preview"></a>AKS(Azure Container Service)(미리 보기)에 대한 VS 연결된 환경
VS 연결된 환경은 Kubernetes에서 빠르게 개발하도록 도와줍니다. Azure에서 전격 관리되고 개발에 최적화된 Kubernetes 기반 환경을 만든 다음, VS Code, Visual Studio 또는 명령줄 같은 친숙한 도구를 사용하여 클라우드에서 컨테이너를 반복적으로 개발합니다.

이 방식에는 여러 이점이 있습니다.

* 클라우드 리소스에 대한 모든 액세스 권한을 사용하여 프로덕션을 대표하는 인프라 기반 개발 환경을 가져옵니다.
* VS Code 또는 Visual Studio를 사용하여 Kubernetes에서 직접 Node.js 및 .NET Core 컨테이너를 디버그합니다. 명령줄 인터페이스를 사용하여 다른 모든 언어를 개발할 수 있습니다.
* 비용을 절약하고 새로운 팀 구성원에 대한 로컬 컴퓨터 설치를 최소화하려면 개발 팀에서 Kubernetes 인스턴스를 공유합니다.
* 격리되어 코드를 개발하고, 종속성을 복제 또는 모의하지 않고 다른 구성 요소를 사용하여 종단 간 테스트를 수행합니다.


> [!div class="nextstepaction"]
> [시작](get-started.md)


![](media/vscode-overview.png)