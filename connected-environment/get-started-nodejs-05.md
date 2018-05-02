---
title: 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 Node.js 개발 환경 만들기 - 5단계 - 다른 컨테이너 호출 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: 89565869feec746aff75327b59ee7d0b466f26c1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Node.js를 사용하여 연결된 환경에서 시작

이전 단계: [Kubernetes 컨테이너 디버그](get-started-nodejs-04.md)

이 섹션에서는 두 번째 서비스 `mywebapi`을 만들고 `webfrontend`가 이 서비스를 호출하도록 하겠습니다. 각 서비스는 별도 컨테이너에서 실행됩니다. 그런 다음, 두 컨테이너에서 디버그하게 됩니다.

![](media/multi-container.png)

## <a name="open-sample-code-for-mywebapi"></a>*mywebapi*에 대한 샘플 코드 열기
`vsce/samples`이라는 폴더 아래 이 가이드에 대한 `mywebapi`을 위한 샘플 코드가 이미 있어야 합니다(그렇지 않은 경우로 https://github.com/Azure/vsce으로 이동해 **복제 또는 다운로드**를 선택해 GitHub 리포지토리를 다운로드합니다.) 이 섹션에 대한 코드는 `vsce/samples/nodejs/getting-started/mywebapi`에 있습니다.

## <a name="run-mywebapi"></a>*mywebapi* 실행
1. *별도 VS Code 창*에서 폴더 `mywebapi`을 엽니다.
1. F5 키를 누르고 서비스가 빌드 및 배포되는 것을 기다립니다. VS Code 디버그 표시줄이 표시되는 경우 준비된 것을 알 수 있습니다.
1. 끝점 URL을 유의하십시오. http://localhost:\<portnumber\> 같이 표시됩니다. **팁: VS Code 상태 표시줄에 클릭 가능한 URL이 표시됩니다.** 컨테이너가 로컬로 실행되는 것 같지만 실제로는 Azure의 개발 환경에서 실행 중입니다. localhost 주소에 대한 이유는 `mywebapi`이 모든 공용 끝점을 정의하지 않았고 Kubernetes 인스턴스 내에서부터 액세스될 수 있기 때문입니다. 사용자 편의를 위해 그리고 로컬 컴퓨터에서 개인 서비스와 상호 작용을 활성화하려면 연결된 환경이 Azure에서 실행 중인 컨테이너에 임시로 SSH 터널을 만듭니다.
1. `mywebapi`이 준비되면 localhost 주소에서 브라우저를 엽니다. `mywebapi` 서비스("Hello from mywebapi")에서 응답을 확인해야 합니다.


## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>*webfrontend*에서 *mywebapi*로 요청하기
이제 `mywebapi`에 요청하는 `webfrontend`에서 코드를 작성해봅시다.
1. `webfrontend`에 대한 VS Code 창으로 전환합니다.
1. `server.js`의 상단에 코드의 줄을 추가합니다.
```javascript
var request = require('request');
var propagateHeaders = require('./propagateHeaders');
```

3. `/api` 가져오기 처리기에 대해 코드를 *바꿉니다*. 요청을 처리할 때 차례로 `mywebapi`에 대한 호출을 한 다음, 두 서비스에서 결과를 반환합니다.

```javascript
app.get('/api', function (req, res) {
    request({
        uri: 'http://mywebapi',
        headers: propagateHeaders.from(req) // propagate headers to outgoing requests
    }, function (error, response, body) {
        res.send('Hello from webfrontend and ' + body);
    });
});
```

`http://mywebapi`로서 서비스를 참조하려면 Kubernetes의 DNS 서비스 검색이 사용되는 방법을 참고하십시오. **코드가 프로덕션에서 실행되는 것과 동일한 방식으로 개발 환경에서 실행됩니다**.

위의 코드 예제는 `propagateHeaders`이라는 도우미 모듈을 사용합니다. `vsce init`을 실행할 때 이 도우미가 코드 폴더에 추가됩니다. `propagateHeaders.from()` 함수가 기존 http.IncomingMessage 개체에서 특정 헤더를 나가는 요청에 대한 헤더 개체로 전파합니다. 이렇게 함으로써 팀 시나리오에서 보다 생산적인 개발 환경을 활성화하는 방법을 나중에 알아봅니다.


## <a name="debug-across-multiple-services"></a>여러 서비스에서 디버그
1. 이 시점에서 `mywebapi`은 디버거가 연결된 상태로 계속 실행돼야 합니다. 그렇지 않은 경우 `mywebapi` 프로젝트에서 F5 키를 누릅니다.
1. 기본 가져오기 `/` 처리기에 중단점을 설정합니다.
1. `webfrontend` 프로젝트에서 `http://mywebapi`에 가져오기 요청을 보내기 바로 전에 중단점을 설정합니다.
1. `webfrontend` 프로젝트에서 F5 키를 누릅니다.
1. 웹앱을 열고 두 서비스의 코드를 단계별로 실행합니다. 웹앱에는 "Hello from webfrontend 및 Hello from mywebapi" 등의 두 서비스에서 연결한 메시지가 표시돼야 합니다.


훌륭합니다! 각 컨테이너가 별도로 개발되고 배포될 수 있는 다중 컨테이너 응용 프로그램이 있습니다.

> [!div class="nextstepaction"]
> [팀 개발에 대해 알아보기](get-started-nodejs-06.md)
