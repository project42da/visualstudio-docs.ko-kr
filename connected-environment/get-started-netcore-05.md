---
title: 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 .NET Core 개발 환경 만들기 - 5단계 - 다른 컨테이너 호출 | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: ghogen
ms.openlocfilehash: 15ca1db26bc57aafa704a57b4464b31a1ada8c92
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-net-core"></a>.NET Core를 사용하여 연결된 환경에서 시작

이전 단계: [Kubernetes 컨테이너 디버그](get-started-netcore-04.md)

이 섹션에서는 두 번째 서비스 `mywebapi`을 만들고 `webfrontend`가 이 서비스를 호출하도록 하겠습니다. 각 서비스는 별도 컨테이너에서 실행됩니다. 그런 다음, 두 컨테이너에서 디버그하게 됩니다.

![](media/multi-container.png)

## <a name="download-sample-code-for-mywebapi"></a>*mywebapi*에 대한 샘플 코드 다운로드
시간 관계상 GitHub 리포지토리에서 샘플 코드를 다운로드합시다. https://github.com/Azure/vsce로 이동해 **복제 또는 다운로드**를 선택해 GitHub 리포지토리를 다운로드합니다. 이 섹션에 대한 코드는 `vsce/samples/dotnetcore/getting-started/mywebapi`에 있습니다.


## <a name="run-mywebapi"></a>*mywebapi* 실행
1. *별도 VS Code 창*에서 폴더 `mywebapi`을 엽니다.
1. F5 키를 누르고 서비스가 빌드 및 배포되는 것을 기다립니다. VS Code 디버그 표시줄이 표시되는 경우 준비된 것을 알 수 있습니다.
1. 끝점 URL을 유의하십시오. http://localhost:\<portnumber\> 같이 표시됩니다. **팁: VS Code 상태 표시줄에 클릭 가능한 URL이 표시됩니다.** 컨테이너가 로컬로 실행되는 것 같지만 실제로는 Azure의 개발 환경에서 실행 중입니다. localhost 주소에 대한 이유는 `mywebapi`이 모든 공용 끝점을 정의하지 않았고 Kubernetes 인스턴스 내에서부터 액세스될 수 있기 때문입니다. 사용자 편의를 위해 그리고 로컬 컴퓨터에서 개인 서비스와 상호 작용을 활성화하려면 연결된 환경이 Azure에서 실행 중인 컨테이너에 임시로 SSH 터널을 만듭니다.
1. `mywebapi`이 준비되면 localhost 주소에서 브라우저를 엽니다. `ValuesController`에 대한 기본 GET API를 호출하려면 URL에 `/api/values` 추가 
1. 모든 단계가 정상적인 경우 `mywebapi` 서비스에서 응답을 확인할 수 있어야 합니다.


## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>*webfrontend*에서 *mywebapi*로 요청하기
이제 `mywebapi`에 요청하는 `webfrontend`에서 코드를 작성해봅시다.
1. `webfrontend`에 대한 VS Code 창으로 전환합니다.
1. 정보 메서드에 대한 코드를 *바꿉니다*.

```csharp
public async Task<IActionResult> About()
{
    ViewData["Message"] = "Hello from webfrontend";
    
    // Use HeaderPropagatingHttpClient instead of HttpClient so we can propagate
    // headers in the incoming request to any outgoing requests
    using (var client = new HeaderPropagatingHttpClient(this.Request))
    {
        // Call *mywebapi*, and display its response in the page
        var response = await client.GetAsync("http://mywebapi/api/values/1");
        ViewData["Message"] += " and " + await response.Content.ReadAsStringAsync();
    }

    return View();
}
```

`http://mywebapi`로서 서비스를 참조하려면 Kubernetes의 DNS 서비스 검색이 사용되는 방법을 참고하십시오. **코드가 프로덕션에서 실행되는 것과 동일한 방식으로 개발 환경에서 실행됩니다**.

위의 코드 예제에서는 또한 `HeaderPropagatingHttpClient` 클래스를 활용합니다. `vsce init`을 실행할 때 이 도우미가 코드 폴더에 추가됩니다. `HeaderPropagatingHttpClient`은 잘 알려진 `HttpClient` 클래스에서 파생됐으며 기존 ASP.NET HttpRequest 개체에서 나가는 HttpRequestMessage 개체로 특정 헤더를 전파하는 기능을 추가합니다. 이렇게 함으로써 팀 시나리오에서 보다 생산적인 개발 환경을 활성화하는 방법을 나중에 알아봅니다.


## <a name="debug-across-multiple-services"></a>여러 서비스에서 디버그
1. 이 시점에서 `mywebapi`은 디버거가 연결된 상태로 계속 실행돼야 합니다. 그렇지 않은 경우 `mywebapi` 프로젝트에서 F5 키를 누릅니다.
1. `api/values/{id}` 가져오기 요청을 처리하는 `Get(int id)` 메서드에서 중단점을 설정합니다.
1. `webfrontend` 프로젝트에서 `mywebapi/api/values`에 가져오기 요청을 보내기 바로 전에 중단점을 설정합니다.
1. `webfrontend` 프로젝트에서 F5 키를 누릅니다.
1. 웹앱을 호출해 두 서비스의 코드를 단계별로 실행합니다.
1. 웹앱의 정보 페이지에는 "Hello from webfrontend 및 Hello from mywebapi" 등의 두 서비스에서 연결한 메시지가 표시됩니다.


훌륭합니다! 각 컨테이너가 별도로 개발되고 배포될 수 있는 다중 컨테이너 응용 프로그램이 있습니다.

> [!div class="nextstepaction"]
> [팀 개발에 대해 알아보기](get-started-netcore-06.md)

