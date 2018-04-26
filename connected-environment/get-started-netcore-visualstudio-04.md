---
title: Visual Studio가 있는 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 .NET Core 개발 환경 만들기 - 4단계 - Kubernetes에서 컨테이터 디버그 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: 75588fcabbba739c4670da42e24665428ff89130
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>.NET Core 및 Visual Studio를 사용하여 연결된 환경에서 시작

이전 단계: [Azure에서 개발 환경 만들기](get-started-netcore-visualstudio-03.md)

## <a name="debug-a-container-in-kubernetes"></a>Kubernetes에서 컨테이너 디버그
개발 환경이 제대로 만들어지면 응용 프로그램을 디버그할 수 있습니다. 코드에 예를 들어 `Message` 변수가 설정된 파일 `HomeController.cs`에서 20번째 줄에 중단점을 설정합니다. **F5** 키를 클릭해 디버깅을 시작합니다. 

응용 프로그램을 빌드 및 배포한 다음, 실행 중인 웹앱을 사용하여 브라우저를 열기 위해 Visual Studio는 개발 환경과 통신합니다. 컨테이너가 로컬로 실행되는 것 같지만 실제로는 Azure의 개발 환경에서 실행 중입니다. Localhost 주소에 대한 이유는 연결된 환경이 Azure에서 실행 중인 컨테이너에 대해 임시로 SSH 터널을 만들기 때문입니다.

중단점을 트리거하는 페이지의 맨 위쪽에 "**정보**" 링크를 클릭합니다. 호출 스택, 지역 변수, 예외 정보 등과 같은 코드를 로컬로 실행하는 경우 마찬가지로 디버그 정보에 대한 모든 액세스 권한이 있습니다.

> [!div class="nextstepaction"]
> [다른 컨테이너 호출](get-started-netcore-visualstudio-05.md)