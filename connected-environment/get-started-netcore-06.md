---
title: 클라우드에서 Kubernetes를 사용하여 컨테이너가 있는 .NET Core 개발 환경 만들기 - 6단계 - 팀 개발 알아보기 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: 4da5051b760a12f8fd8837072ada44c8c5a9b239
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core"></a>.NET Core를 사용하여 연결된 환경에서 시작

이전 단계: [다른 컨테이너 호출](get-started-netcore-05.md)

[!INCLUDE[](includes/team-development-1.md)]

어떻게 작동하는지 확인해 보겠습니다.
1. 예를 들어 `mywebapi`에 대한 VS Code 창으로 이동하고 `string Get(int id)` 메서드에 따라 코드를 편집합니다.

```csharp
[HttpGet("{id}")]
public string Get(int id)
{
    return "mywebapi now says something new";
}
```

[!INCLUDE[](includes/team-development-2.md)]

> [!div class="nextstepaction"]
> [다음](get-started-netcore-07.md)
