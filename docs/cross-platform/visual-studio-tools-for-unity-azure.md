---
title: Visual Studio Tools for Unity Azure Walkthrough | Microsoft Docs
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7921D4C7-5526-42F5-8E03-82D3E33A893F
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: d5242dd873591abee15f528d09b6f588ea12f5ba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-azure-easy-tables-with-unity-walkthrough"></a>Unity를 사용한 Azure 간편한 테이블 연습 사용

![예제 게임 스크린샷](media/vstu_azure-test-sample-game-image2.png)

## <a name="introduction"></a>소개

Azure는 클라우드에서 원격 분석 및 기타 게임 데이터 저장에 확장 가능한 솔루션을 제공합니다. Unity 2017의 릴리스로, .NET 4.6에 Unity가 지원되어 Azure Mobile Client SDK를 사용할 수 있어 Azure를 어느 때보다도 간편하게 통합할 수 있습니다.

이 단계는 클라우드에서 원격 분석 및 순위표를 활용하는 Unity 프로젝트를 설정하는 과정을 안내합니다.

> [!NOTE]
> 이 프로젝트는 Unity 2017에서 "실험적" .NET 4.6 Mono 스크립팅 런타임이 필요합니다. [Unity는 곧 기본 설정이 될 것이라고 표시하지만](https://forum.unity3d.com/threads/future-plans-for-the-mono-runtime-upgrade.464327/), 지금은 여전히 “실험적”으로 표시되어 있으며 문제가 발생할 수 있습니다.

> 이 연습에서는 Unity PC 빌드에서 Azure Mobile App 백엔드에 연결하는 예를 기록하고 있습니다. 이 문서가 작성된 시점에서 이 프로젝트가 Mac 및 Android 프로젝트에서 작동하지 못하게 하는 알려진 문제가 있었습니다. 이러한 문제는 알려져 있고 해결된 예정이지만, 일정은 확실하지 않습니다. 자세한 내용은 Unity [실험적 스크립팅 포럼](https://forum.unity3d.com/forums/experimental-scripting-previews.107/)을 방문하세요.

## <a name="download-the-completed-project"></a>완료된 프로젝트 다운로드

완료된 프로젝트는 GitHub에서 사용 가능합니다. 하지만, 이 연습에서는 사용자가 비어 있는 새 프로젝트에서 시작하는 것으로 가정하며 필요 시 자산을 다운로드할 수 있는 링크를 제공합니다.

## <a name="walkthrough-steps"></a>연습 단계

1. [Azure에서 간편한 테이블 구성](visual-studio-tools-for-unity-azure-configure.md)
2. [간편한 테이블 만들기](visual-studio-tools-for-unity-azure-setup.md)
3. [개발 환경 준비](visual-studio-tools-for-unity-azure-prepare.md)
4. [데이터 모델 클래스 만들기](visual-studio-tools-for-unity-azure-data.md)
5. [Azure MobileServiceClient 구현](visual-studio-tools-for-unity-azure-mobile-client.md)
6. [Unity Mono 보안 인증서 저장소 업데이트](visual-studio-tools-for-unity-azure-security.md)
7. [클라이언트 연결 테스트](visual-studio-tools-for-unity-azure-connection.md)
7. [샘플 게임 자산 가져오기](visual-studio-tools-for-unity-azure-game-assets.md)
8. [샘플 게임 테스트](visual-studio-tools-for-unity-azure-game.md)
9. [RaceScene 설명](visual-studio-tools-for-unity-azure-racescene.md)
10. [HeatmapScene 설명](visual-studio-tools-for-unity-azure-heatmapscene.md)
11. [LeaderboardScene 설명](visual-studio-tools-for-unity-azure-leaderboardscene.md)


## <a name="next-step"></a>다음 단계
* [Azure에서 간편한 테이블 구성](visual-studio-tools-for-unity-azure-configure.md)
