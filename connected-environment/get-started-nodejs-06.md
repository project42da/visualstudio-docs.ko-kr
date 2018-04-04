---
title: 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 Node.js 개발 환경 만들기 - 6단계 - 팀 개발 알아보기 | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: ghogen
ms.openlocfilehash: 4db1d71c96da29a06884e562a277a7ca427910d4
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Node.js를 사용하여 연결된 환경에서 시작

이전 단계: [별도 컨테이너에서 실행되는 서비스 호출](get-started-nodejs-05.md)

[!INCLUDE[](includes/team-development-1.md)]

어떻게 작동하는지 확인해 보겠습니다.
1. 예를 들어 `mywebapi`에 대한 VS Code 창으로 이동하고 기본 가져오기 `/` 처리기에 따라 코드를 편집합니다.

```javascript
app.get('/', function (req, res) {
    res.send('mywebapi now says something new');
});
```

[!INCLUDE[](includes/team-development-2.md)]

> [!div class="nextstepaction"]
> [다음](get-started-nodejs-07.md)

