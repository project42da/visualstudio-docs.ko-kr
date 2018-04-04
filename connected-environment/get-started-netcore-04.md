---
title: 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 .NET Core 개발 환경 만들기 - 4단계 - Kubernetes에서 컨테이터 디버그 | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: ghogen
ms.openlocfilehash: f06489194f70a3e7e617f4022917cd1d4a96337f
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-net-core"></a>.NET Core를 사용하여 연결된 환경에서 시작
 
이전 단계: [ASP.NET Core 웹앱 만들기](get-started-netcore-03.md)

[!INCLUDE[](includes/debug-intro.md)]

[!INCLUDE[](includes/init-debug-assets-vscode.md)]


## <a name="select-the-vsce-debug-configuration"></a>VSCE 디버그 구성 선택
1. 디버그 보기를 열려면 VS Code의 측면에서 **작업 모음**에서 디버그 아이콘을 클릭합니다.
1. **.NET Core 시작(VSCE)**을 활성 디버그 구성으로 선택합니다.

![](media/debug-configuration.png)

> [!Note]
> 명령 팔레트에 모든 연결된 환경 명령이 표시되지 않는 경우 [연결된 환경에 대해 VS Code 확장을 설치](get-started-netcore-01.md#get-kubernetes-debugging-for-vs-code)했는지 확인합니다.


## <a name="debug-the-container-in-kubernetes"></a>Kubernetes에서 컨테이너 디버그
**F5** 키를 눌러 Kubernetes에서 코드를 디버그합니다.

`up` 명령에서처럼 코드는 개발 환경과 동기화되고 컨테이너는 빌드되어 Kubernetes에 배포됩니다. 이 번에는 물론 원격 컨테이너에 디버거가 연결됩니다.

[!INCLUDE[](includes/tip-vscode-status-bar-url.md)]

서버 쪽 코드 파일에서, 예를 들어 `Controllers/HomeController.cs` 소스 파일의 `Index()` 함수 내에 중단점을 설정합니다. 브라우저 페이지를 새로 고치면 중단점이 적중될 수 있습니다.

호출 스택, 지역 변수, 예외 정보 등과 같은 코드를 로컬로 실행하는 경우 마찬가지로 디버그 정보에 대한 모든 액세스 권한이 있습니다.

## <a name="edit-code-and-refresh"></a>코드 편집 및 새로 고침
디버거를 사용하여 코드를 편집합니다. 예를 들어 `Controllers/HomeController.cs`에서 정보 페이지의 메시지를 수정합니다. 

```csharp
public IActionResult About()
{
    ViewData["Message"] = "My custom message in the About page.";
    return View();
}
```

파일을 저장하고 **디버그 작업 창**에서 **새로 고침** 단추를 클릭합니다. 

![](media/debug-action-refresh.png)

종종 상당한 시간이 걸리는 코드를 편집할 때마다 새 컨테이너 이미지를 다시 빌드하고 배포하는 대신 연결된 환경은 더 빠른 편집/디버그 반복을 제공하기 위해 기존 컨테이너 내에서 점진적으로 코드를 다시 컴파일합니다.

브라우저에서 웹앱을 새로 고치고 정보 페이지로 이동합니다. UI에 표시된 사용자 지정 메시지를 확인해야 합니다.

**이제 신속하게 코드에서 반복하고 Kubernetes에서 직접 디버깅하기 위한 메서드가 있습니다!** 다음으로 어떻게 두 번째 컨테이너를 만들고 호출할 수 있는지 알아보겠습니다.

> [!div class="nextstepaction"]
> [별도 컨테이너에서 실행되는 서비스 호출](get-started-netcore-05.md)
