---
title: 개발 환경을 공유하는 방법 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 3/12/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: 43d23caa039340345372076d02b3c4989cde5b01
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="share-a-development-environment"></a>개발 환경 공유

연결된 환경을 사용하여 개발 환경을 팀의 다른 구성원과 공유할 수 있습니다. 각 개발자는 다른 구성원과 단절될 걱정 없이 자신만의 공간에서 작업할 수 있습니다. 또한 한 환경에서 공동 작업함으로써 종속성을 시뮬레이션하거나 모의 개체를 만들 필요 없이 코드를 종단 간 테스트할 수 있습니다. 자세한 내용은 [개발 팀 알아보기](../get-started-nodejs-06.md)를 참조합니다.

여러 개발자를 위한 환경을 설정하려면,
1. [Azure에서 연결된 환경을 만듭니다](../get-started.md). 선택한 Azure 구독에 소유자 또는 참가자를 액세스하게 해야 합니다.
1. 환경의 **리소스 그룹**을 구성해 각 팀 구성원에 대한 [참가자 액세스 권한을 부여](https://docs.microsoft.com/en-us/azure/active-directory/role-based-access-control-configure)합니다. 이 명령 `vsce env list`을 실행하여 환경의 리소스 그룹을 확인할 수 있습니다.
1. 팀 구성원에게 **환경을 선택**해 해당 환경에서 개발하도록 요구합니다.
     * **명령줄 또는 VS Code**: 액세스 권한이 있는 기존 연결된 환경을 확인하려면 `vsce env list`을 합니다. 환경을 선택하려면 `vsce env select`을 합니다.
     * **Visual Studio IDE**: Visual Studio에서 프로젝트를 열고 시작 설정 드롭다운 목록에서 **AKS에 대한 연결된 환경**을 선택합니다. 열린 대화 상자에서 기존 개발 환경을 선택합니다.

![Visual Studio 시작 설정 드롭다운 목록](../images/LaunchSettings.png)