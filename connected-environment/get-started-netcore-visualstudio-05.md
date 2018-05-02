---
title: Visual Studio가 있는 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 .NET Core 개발 환경 만들기 - 5단계 - 다른 컨테이너 호출 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: ab3934e6f7f013dd21309dc8c98461983bdfe30a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>.NET Core 및 Visual Studio를 사용하여 연결된 환경에서 시작

이전 단계: [Kubernetes 컨테이너 디버그](get-started-netcore-visualstudio-04.md)

## <a name="call-another-container"></a>다른 컨테이너 호출
이 섹션에서는 두 번째 서비스 `mywebapi`을 만들고 `webfrontend`가 이 서비스를 호출하도록 하겠습니다. 각 서비스는 별도 컨테이너에서 실행됩니다. 그런 다음, 두 컨테이너에서 디버그하게 됩니다.

![](media/multi-container.png)

## <a name="download-sample-code-for-mywebapi"></a>*mywebapi*에 대한 샘플 코드 다운로드
시간 관계상 GitHub 리포지토리에서 샘플 코드를 다운로드합시다. https://github.com/Azure/vsce로 이동해 **복제 또는 다운로드**를 선택해 GitHub 리포지토리를 다운로드합니다. 이 섹션에 대한 코드는 `vsce/samples/dotnetcore/getting-started/mywebapi`에 있습니다.

## <a name="run-mywebapi"></a>*mywebapi* 실행
1. *별도 Visual Studio 창*에서 프로젝트 `mywebapi`을 엽니다.
1. 이전에 `webfrontend` 프로젝트에 대해 그랬던 것처럼 시작 설정 드롭다운 목록에서 **AKS에 대한 연결된 환경**을 선택합니다. 이번에 새 개발 환경을 만들기보다는 이미 만든 동일한 환경을 선택합니다. 전과 마찬가지로 공간이 `mainline`로 기본 설정되게 하고 **확인**을 클릭합니다. 디버깅을 시작하면 작업 속도를 높이기 위해 Visual Studio가 개발 환경에서 이 새로운 서비스 "준비"를 시작하는 것이 출력 창에 표시됩니다.
1. F5 키를 누르고 서비스가 빌드 및 배포되는 것을 기다립니다. Visual Studio 상태줄이 주황색으로 변할 때 준비가 된 것이 표시됨
1. **출력** 창의 **AKS에 대해 연결된 환경** 창에 표시된 엔드포인트 URL에 유의하십시오. 이는 http://localhost:\<portnumber\> 같이 나타납니다. 컨테이너가 로컬로 실행되는 것 같지만 실제로는 Azure의 개발 환경에서 실행 중입니다.
1. `mywebapi`이 준비된 경우 브라우저를 localhost 주소에서 열고 `/api/values`를 URL에 추가해 `ValuesController`에 대한 기본 API 가져오기를 호출합니다. 
1. 모든 단계가 정상적인 경우 이와 같이 보이는 `mywebapi` 서비스에서 응답을 확인할 수 있어야 합니다.

    ![](images/WebAPIResponse.png)

## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>*webfrontend*에서 *mywebapi*로 요청하기
이제 `mywebapi`에 요청하는 `webfrontend`에서 코드를 작성해봅시다. `webfrontend` 프로젝트가 있는 Visual Studio 창으로 전환합니다. `HomeController.cs` 파일에서 정보 메서드의 코드를 다음 코드로 *바꿉니다*.

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

위의 코드 예제에서는 또한 `HeaderPropagatingHttpClient` 클래스를 활용합니다. 이 도우미 클래스는 연결된 환경을 사용하도록 구성된 경우 프로젝트에 추가된 파일 `HeaderPropagation.cs`입니다. `HeaderPropagatingHttpClient`은 잘 알려진 `HttpClient` 클래스에서 파생됐으며 기존 ASP.NET HttpRequest 개체에서 나가는 HttpRequestMessage 개체로 특정 헤더를 전파하는 기능을 추가합니다. 이렇게 함으로써 팀 시나리오에서 보다 생산적인 개발 환경을 활성화하는 방법을 나중에 알아봅니다.

## <a name="debug-across-multiple-services"></a>여러 서비스에서 디버그
1. 이 시점에서 `mywebapi`은 디버거가 연결된 상태로 계속 실행돼야 합니다. 그렇지 않은 경우 `mywebapi` 프로젝트에서 F5 키를 누릅니다.
1. `api/values/{id}` 가져오기 요청을 처리하는 `ValuesController.cs` 파일의 `Get(int id)` 메서드에서 중단점을 설정합니다.
1. 위의 코드를 붙여넣기한 `webfrontend` 프로젝트에서 가져오기 요청을 `mywebapi/api/values`로 보내기 바로 전에 중단점을 설정합니다.
1. `webfrontend` 프로젝트에서 F5 키를 누릅니다. Visual Studio가 적절한 localhost 포트에서 브라우저를 다시 열면 웹앱이 표시됩니다.
1. `webfrontend` 프로젝트에서 중단점을 트리거하려면 페이지의 상단에 있는 "**정보**" 링크를 클릭합니다. 
1. F10 키를 눌러 계속 진행합니다. `mywebapi` 프로젝트에서 이제 중단점을 트리거합니다.
1. F5 키를 눌러 계속 진행하면 `webfrontend` 프로젝트의 코드로 다시 돌아오게 됩니다.
1. 한 번 더 F5 키를 누르면 요청이 완료되고 브라우저에서 페이지가 반환됩니다. 웹앱의 정보 페이지에는 "Hello from webfrontend 및 Hello from mywebapi" 등의 두 서비스에서 연결한 메시지가 표시됩니다.

훌륭합니다! 각 컨테이너가 별도로 개발되고 배포될 수 있는 다중 컨테이너 응용 프로그램이 있습니다.

> [!div class="nextstepaction"]
> [팀 개발에 대해 알아보기](get-started-netcore-visualstudio-06.md)

