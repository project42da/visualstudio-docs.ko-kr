---
title: Visual Studio를 사용하여 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 .NET Core 개발 환경 만들기 - 6단계 - 팀 개발 알아보기 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 04/05/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: b4bc1f44e63614346f4e2d149e76becabdcb8c71
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>.NET Core 및 Visual Studio를 사용하여 연결된 환경에서 시작

이전 단계: [다른 컨테이너 호출](get-started-netcore-visualstudio-05.md)

## <a name="learn-about-team-development"></a>팀 개발에 대해 알아보기

지금까지 앱에서 작업하는 유일한 개발자인 것처럼 응용 프로그램의 코드를 실행했습니다. 이 섹션에서는 연결된 환경을 통해 팀 개발을 간소화하는 방법을 배우게 됩니다.
* 동일한 개발 환경에서 작업하는 개발자 팀을 사용하도록 설정합니다.
* 각 개발자가 다른 코드의 중단 걱정 없이 격리된 해당 코드에 대한 반복을 지원합니다.
* 종속성을 시뮬레이션하거나 모의 개체를 만들 필요 없이 코드 커밋에 앞서 코드를 종단 간 테스트합니다.

## <a name="challenges-with-developing-microservices"></a>마이크로 서비스 개발의 당면과제
샘플 응용 프로그램은 현재 매우 복잡하지 않습니다. 하지만 실제 개발 과정에서 더 많은 서비스가 추가되고 개발 팀이 성장하면서 곧 당면 과제가 나타납니다.

다양한 다른 서비스와 상호 작용하는 서비스에서 작업하는 자신을 상상해보세요.

1. 개발에 대한 모든 것이 현지에서 실행되는 것은 비현실적일 수 있습니다. 개발 컴퓨터에는 전체 앱을 실행하기에 충분한 리소스가 없을 수 있습니다. 또는 아마도 앱에 공개적으로 연결할 수 있어야 하는 끝점이 있습니다(예를 들어 앱이 SaaS 앱에서 웹후크에 응답하는 경우입니다).
1. 종속된 서비스의 실행을 시도할 수 있습니다만 이는 종속성의 전체 클로저를 알어야 한다는 의미입니다(예를 들어 종속성의 종속성입니다). 종속성에서 작업하지 않았기 때문에 종속성을 빌드하고 실행하는 방법을 아는 것은 쉽지 않은 문제입니다.
1. 일부 개발자는 많은 서비스 종속성을 시뮬레이션 또는 모킹업에 의존합니다. 이는 때로는 도움이 될 수 있지만 이러한 모의 개체를 관리하는 것은 곧 자체 개발 노력을 떠맡을 수 있습니다. 게다가 이는 생산과 매우 다른 개발 환경으로 이끌며 미묘한 버그가 서서히 생겨날 수 있습니다.
1. 따라서 모든 유형의 종단 간 테스트 수행이 어렵게 됩니다. 통합 테스트는 현실적으로 커밋 후에 발생할 수 있는데 이는 개발 주기에서 나중에 문제를 확인한다는 의미입니다.

    ![](media/microservices-challenges.png)

## <a name="work-in-a-shared-development-environment"></a>공유 개발 환경에서 작업
연결된 환경을 통해 Azure에서 *공유된* 개발 환경을 설정할 수 있습니다. 각 개발자는 응용 프로그램에서 자신이 맡은 부분에만 집중할 수 있으며 자신의 시나리오에 의존하는 다른 모든 서비스 및 클라우드 리소스가 포함된 환경에서 *커밋 전 코드*를 반복해서 개발할 수 있습니다. 종속성은 항상 최신 상태로 유지되며 개발자가 생산을 미러링하는 방식으로 작업합니다.

## <a name="work-in-your-own-space"></a>사용자 고유의 공간에서 작업
서비스에 대한 코드를 개발할 경우 코드를 체크인할 준비가 되기 전에 코드는 종종 양호한 상태가 아닙니다. 여전히 반복적으로 솔루션을 셰이핑, 테스트 및 시험합니다. 연결된 환경은 팀 구성원과 분리될 걱정 없이 격리되어 작업할 수 있는 **공간**의 개념을 제공합니다.

`webfrontend` 및 `mywebapi` 서비스 모두가 우리의 개발 환경  **및 `mainline`공간**에서 실행되고 있는지 확인하려면 다음을 수행합니다.
1. 두 서비스에 대한 모든 F5/디버그 세션을 닫고 그러나 해당 프로젝트는 Visual Studio 창에서 열린 상태로 유지합니다.
2. 디버거를 연결하지 않은 상태로 서비스를 실행하려면 `mywebapi` 프로젝트를 사용하여 Visual Studio 창으로 전환하고 Ctrl+F5 키를 누름
3. `webfrontend` 프로젝트를 사용하여 Visual Studio 창으로 전환하고 Ctrl+F5 키를 눌러 서비스를 실행합니다.

> [!Note]
웹 페이지가 Ctrl+F5에 이어 초기에 표시된 후 브라우저를 새로 고침할 필요도 있습니다.

두 서비스를 통해 실행하는 URL가 열고 웹앱으로 이동하는 모든 사용자는 기본 `mainline` 공간을 사용하여 두 서비스를 통해 실행되도록 작성한 코드 경로를 호출합니다. `mywebapi`을 계속 개발하려는 경우를 가정해봅시다 - 개발 환경을 사용하는 다른 개발자를 방해하지 않고 어떻게 개발을 계속할 수 있습니까? 그러기 위해서는 자신만의 공간을 설정합니다.

### <a name="create-a-new-space"></a>새 공간 만들기
Visual Studio에서 서비스를 F5 또는 Ctrl+F5 키를 누를 때 사용될 추가 공간을 만들 수 있습니다. 공간을 원하는 모든 것으로 호출할 수 있으며 그 의미에 대해서는 유연할 수 있습니다(예: `sprint4` 또는 `demo`).

새 공간 만들려면 다음을 수행합니다.
1. `mywebapi` 프로젝트가 있는 Visual Studio 창으로 전환합니다.
2. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.
3. 연결된 환경 설정을 표시하려면 왼쪽의 **디버그** 탭을 선택합니다.
4. 여기에서 F5 또는 Ctrl+F5 키를 누를 경우 사용될 연결된 환경 및/또는 공간을 만들거나 변경할 수 있습니다. *앞에서 만든 연결된 환경이 선택됐는지 확인합니다*.
5. **공간** 드롭다운 목록에서 **<새 공간 만들기...>** 를 선택합니다.

    ![](images/Settings.png)

6. **공간 추가** 대화 상자에서 공간에 대한 이름을 입력하고 **확인**을 클릭합니다. 새 공간에 내 이름("scott")을 사용했으므로 내가 어떤 공간에서 일하고 있는지 동료들이 식별할 수 있습니다.

    ![](images/AddSpace.png)

7. 이제 프로젝트 속성 페이지에서 선택한 새 환경 및 개발 환경이 표시돼야 합니다.

    ![](images/Settings2.png)

### <a name="update-code-for-mywebapi"></a>*mywebapi*에 대한 코드 업데이트

1. `mywebapi` 프로젝트에서 다음과 같은 파일 `ValuesController.cs`의 `string Get(int id)` 메서드로 코드를 변경합니다.
 
    ```csharp
    [HttpGet("{id}")]
    public string Get(int id)
    {
        return "mywebapi now says something new";
    }
    ```

2. 이 업데이트된 코드 블록(이미 전에 하나를 설정했을 수 있습니다)에 중단점을 설정합니다.
3. `mywebapi` 서비스를 시작하려면 F5 키를 누릅니다. 이렇게 함으로써 나의 경우에 `scott`인 선택된 공간을 사용하여 개발 환경에서 서비스를 시작합니다.

다이어그램을 통해 다른 공간이 어떻게 작동하는지 이해할 수 있습니다. 파란색 경로는 URL에 어떤 공간도 추가되지 않은 경우에 사용된 기본 경로인 `mainline` 공간을 통해 요청을 표시합니다. 녹색 경로는 `scott` 공간을 통해 요청을 표시합니다.

![](media/Space-Routing.png)

연결된 환경의 이 기본 제공 기능을 사용하여 각 개발자가 자신의 공간에서 서비스의 전체 스택을 다시 만들도록 요구하지 않고도 공유 환경에서 코드를 종단 간 테스트할 수 있습니다. 이 가이트의 이전 단계에서 설명된 것처럼 이 라우팅은 앱 코드에서 전달된 전파 헤더를 요구합니다.

## <a name="test-code-running-in-the-scott-space"></a>`scott` 공간에서 실행되는 코드 테스트
`webfrontend`와 연결해 `mywebapi`의 새 버전을 테스트하려면 `webfrontend`에 대한 공용 액세스 지점 URL에서 브라우저를 열고(예: https://webfrontend-teamenv.vsce.io) 그리고 정보 페이지로 이동합니다. "Hello from webfrontend 및 Hello from mywebapi"라는 원래 메시지가 표시돼야 합니다.

이제 URL에 "scott-" 파트를 추가하면 https://scott-webfrontend-teamenv.vsce.io처럼 표시되고 브라우저를 새로 고칩니다. `mywebapi` 프로젝트에 설정한 중단점은 적중을 가져와야 합니다. F5 키를 클릭해 계속 진행하면 이제 브라우저에 "Hello from webfrontend 및 mywebapi가 이제 새로운 것을 얘기합니다"라는 새 메시지가 표시돼야 합니다. `mywebapi`에서 업데이트된 코드 경로가 `scott` 공간에서 실행되고 있기 때문입니다.

> [!div class="nextstepaction"]
> [요약](get-started-netcore-visualstudio-07.md)