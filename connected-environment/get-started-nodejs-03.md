---
title: 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 Node.js 개발 환경 만들기 - 3단계 - ASP.NET 웹앱 만들기 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: 34e1f07e173ccba6aab561fb4795abbe938e0127
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Node.js를 사용하여 연결된 환경에서 시작

이전 단계: [Azure에서 Kubernetes 개발 환경 만들기](get-started-nodejs-02.md)

## <a name="create-a-nodejs-web-app"></a>Node.js 웹앱 만들기
https://github.com/Azure/vsce로 이동하여 GitHub에서 코드를 다운로드하고 **복제 또는 다운로드**를 선택하여 로컬 환경에 GitHub 리포지토리를 다운로드합니다. 이 가이드에 대한 코드는 `vsce/samples/nodejs/getting-started/webfrontend`에 있습니다.

[!INCLUDE[](includes/vsce-init.md)]

[!INCLUDE[](includes/ensure-env-created.md)]

[!INCLUDE[](includes/build-and-run-in-k8s-cli.md)]

## <a name="update-a-content-file"></a>콘텐츠 파일 업데이트
연결된 환경은 Kubernetes에서 실행되는 코드를 가져오는 방법에 대한 것이 아니라 코드 변경 내용이 클라우드의 Kubernetes 환경에 적용되는지 빠르고 반복적으로 확인할 수 있는 방법에 대한 것입니다.

1. 파일 `./public/index.html`을 찾아 HTML을 편집합니다. 예를 들어 페이지의 배경색을 파란색 음영으로 변경합니다.

```html
<body style="background-color: #95B9C7; margin-left:10px; margin-right:10px;">
```

2. 파일을 저장합니다. 잠시 후 실행 중인 컨테이너에서 파일이 업데이트됐다는 메시지가 터미널 창에 표시됩니다.
1. 브라우저로 이동해서 페이지를 새로 고칩니다. 색 업데이트가 표시돼야 합니다.

어떻게 된 것입니까? HTML 및 CSS 같은 콘텐츠 파일에 대한 편집은 Node.js process 다시 시작하기를 요구하지 않으므로 `vsce up` 활성 명령은 모든 수정된 콘텐츠 파일을 직접 Azure에서 실행 중인 컨테이너와 자동으로 동기화합니다. 따라서 콘텐츠 편집을 확인하는 빠른 방법을 제공합니다.

### <a name="test-from-a-mobile-device"></a>모바일 장치를 사용하여 테스트
모바일 장치에서 웹앱을 열 경우 UI가 소형 장치에서 제대로 표시되지 않는지 확인합니다.

이 문제를 해결하려면 `viewport` 메타 태그를 추가합니다.
1. 파일 열기 `./public/index.html`
1. 기존 `head` 요소에 `viewport` 메타 태그를 추가합니다.

```html
<head>
    <!-- Add this line -->
    <meta name="viewport" content="width=device-width, initial-scale=1">
</head>
```

1. 파일을 저장합니다.
1. 장치 브라우저를 새로 고칩니다. 이제 제대로 렌더링된 웹앱이 표시돼야 합니다. 

앱이 사용되기로 한 장치에서 테스트할 때까지 일부 문제도 발견되지 않은 방법에 대한 예제입니다. VS 연결된 환경을 통해 신속하게 코드에서 반복하고 대상 장치에서 모든 변경의 유효성을 검사할 수 있습니다.

## <a name="update-a-code-file"></a>코드 파일 업데이트
서버 쪽 코드 파일의 업데이트는 Node.js 앱이 다시 시작해야 하기 때문에 좀 더 많은 작업이 요구됩니다.

1. 터미널 창에서 `Ctrl+C`을 눌러(`vsce up`를 중단합니다).
1. `server.js`이라는 코드 파일을 열고 서비스의 Hello 메시지를 편집합니다. 

```javascript
res.send('Hello from webfrontend running in Azure!');
```

3. 파일을 저장합니다.
1. 터미널 창에서 `vsce up`을 실행합니다. 

이렇게 해서 컨테이너 이미지를 다시 빌드하고 Helm 차트를 다시 배포합니다. 코드 변경 내용이 적용되는 것을 확인하려면 브라우저 페이지를 다시 로드합니다.


그러나 코드를 개발하기 위해 *더 빠른 메서드*가 있습니다. 이는 다음 섹션에서 살펴보겠습니다. 
> [!div class="nextstepaction"]
> [Kubernetes에서 컨테이너 디버그](get-started-nodejs-04.md)
