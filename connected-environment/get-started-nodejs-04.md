---
title: 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 Node.js 개발 환경 만들기 - 4단계 - Kubernetes에서 컨테이터 디버그 | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: ghogen
ms.openlocfilehash: 8dca016f3a3feb2d1fb10a80695b82e531e48a74
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Node.js를 사용하여 연결된 환경에서 시작

이전 단계: [Kubernetes에서 Node.js 컨테이너 만들기](get-started-nodejs-03.md)

[!INCLUDE[](includes/debug-intro.md)]

[!INCLUDE[](includes/init-debug-assets-vscode.md)]


## <a name="select-the-vsce-debug-configuration"></a>VSCE 디버그 구성 선택
1. 디버그 보기를 열려면 VS Code의 측면에서 **작업 모음**에서 디버그 아이콘을 클릭합니다.
1. **시작 프로그램(VSCE)**을 활성 디버그 구성으로 선택합니다.

![](media/debug-configuration-nodejs.png)

> [!Note]
> 명령 팔레트에 모든 연결된 환경 명령이 표시되지 않는 경우 [연결된 환경에 대해 VS Code 확장을 설치](get-started-nodejs-01.md#get-kubernetes-debugging-for-vs-code)했는지 확인합니다.

## <a name="debug-the-container-in-kubernetes"></a>Kubernetes에서 컨테이너 디버그
**F5** 키를 눌러 Kubernetes에서 코드를 디버그합니다!

`up` 명령과 유사한 코드는 디버깅을 시작할 때 개발 환경과 동기화되고 컨테이너는 빌드되어 Kubernetes에 배포됩니다. 이 번에는 물론 원격 컨테이너에 디버거가 연결됩니다.

[!INCLUDE[](includes/tip-vscode-status-bar-url.md)]

서버 쪽 코드 파일에서, 예를 들어 `server.js`의 `app.get('/api'...` 내에 중단점을 설정합니다. 브라우저 페이지를 새로 고치기하거나 ‘다시 말하기’ 단추를 누르면 중단점을 적중하고 코드를 단계별로 실행할 수 있어야 합니다.

호출 스택, 지역 변수, 예외 정보 등과 같은 코드를 로컬로 실행하는 경우 마찬가지로 디버그 정보에 대한 모든 액세스 권한이 있습니다.

## <a name="edit-code-and-refresh-the-debug-session"></a>코드 편집 및 디버그 세션 새로 고치기
디버거를 활성화하면 코드를 편집할 수 있습니다. 예를 들어 hello 메시지를 다시 수정합니다.

```javascript
app.get('/api', function (req, res) {
    res.send('**** Hello from webfrontend running in Azure! ****');
});
```

파일을 저장하고 **디버그 작업 창**에서 **새로 고침** 단추를 클릭합니다. 

![](media/debug-action-refresh-nodejs.png)

종종 상당한 시간이 걸리는 코드를 편집할 때마다 새 컨테이너 이미지를 다시 빌드하고 배포하는 대신 연결된 환경은 더 빠른 편집/디버그 반복을 제공하기 위해 디버그 세션 사이에서 Node.js 프로세스를 다시 시작하게 됩니다.

브라우저에서 웹앱을 새로 고침하거나 *다시 말하기* 단추를 누릅니다. UI에 표시된 사용자 지정 메시지를 확인해야 합니다.


## <a name="use-nodemon-to-develop-even-faster"></a>더 빠른 개발을 위해 NodeMon 사용
*Nodemon*은 인기 있는 도구로서 Node.js 개발자가 신속한 개발을 위해 사용합니다. 서버 쪽 코드가 편집될 때마다 수동으로 노드 프로세스를 다시 시작하는 대신 개발자는 해당 노드 프로젝트를 구성하여 *nodemon* 모니터 파일이 변경되고 서버 프로세스를 자동으로 다시 시작하게 합니다. 이런 스타일의 작업에서는 개발자가 코드를 편집한 뒤 브라우저를 새로 고침하기만 하면 됩니다.

연결된 환경의 의도는 로컬로 개발할 때 사용하는 동일 하고 생산적인 개발 워크플로를 사용할 수 있게 하는 것입니다. 이를 설명하려면 샘플 `webfrontend` 프로젝트가 *nodemon*을 사용하도록 구성됩니다(`package.json`에서 개발 종속성으로 구성됩니다).

다음과 같이 수행해 보세요.
1. VS Code 디버거를 중단합니다.
1. VS Code의 측면의 **작업 모음**에서 디버그 아이콘을 클릭합니다. 
1. **연결(VSCE)**을 활성 디버그 구성으로 선택합니다.
1. F5 키를 누릅니다.

이 구성에서 컨테이너는 *nodemon*이 시작하도록 구성됩니다. 서버 코드가 편집되는 경우 *nodemon*은 로컬로 개발할 때 처럼 노드 프로세스를 자동으로 다시 시작합니다. 
1. `server.js`에서 다시 hello 메시지를 편집하고 파일을 저장합니다.
1. 브라우저를 새로 고침하거나 *다시 말하기* 단추를 눌러 변경 내용이 적용되는 것을 확인합니다!

**이제 신속하게 코드에서 반복하고 Kubernetes에서 직접 디버깅하기 위한 메서드가 있습니다!** 다음으로 어떻게 두 번째 컨테이너를 만들고 호출할 수 있는지 알아보겠습니다.

> [!div class="nextstepaction"]
> [별도 컨테이너에서 실행되는 서비스 호출](get-started-nodejs-05.md)

