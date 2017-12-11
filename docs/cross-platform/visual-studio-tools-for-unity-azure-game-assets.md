---
title: "Visual Studio Tools for Unity Azure Walkthrough 게임 자산 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: C06FAB2E-F592-4EFF-B96A-58858C92DCEB
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 3b1ad3d7dc6af48986e8b10278a8b8135843239d
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="import-sample-game-assets"></a>샘플 게임 자산 가져오기

점수 기능을 테스트한 결과, 작동하는 것으로 입증되었으므로 샘플 게임 자산을 가져올 때입니다.

## <a name="import-package"></a>패키지 가져오기

1. [샘플 게임 자산 패키지](https://github.com/dantogno/UnityAzureSample/blob/master/Azure%20Easy%20tables%20sample%20game%20assets.unitypackage)를 다운로드합니다.

2. Unity 프로젝트가 열려 있는지 확인한 다음, 다운로드 위치로 이동하여 해당 파일을 두 번 클릭합니다. 그러면 Unity에서 가져오기 대화 상자가 표시됩니다.

3. **모두**를 클릭한 다음 **가져오기**를 클릭합니다. 결과 진행 표시줄이 완료될 때까지 기다립니다.

  ![패키지 가져오기](media/vstu_azure-import-sample-assets-image1.png)

## <a name="add-scenes-to-build-settings"></a>빌드 설정에 장면 추가

파일 가져오기가 완료되면 Unity 프로젝트의 빌드 설정에서 필요한 장면 파일을 추가해야 합니다.

1. Unity 프로젝트 창에서 **Azure 간편한 테이블 샘플 게임 자산/장면** 디렉터리로 이동합니다.

2. Unity 메뉴에서 **파일 > 빌드 설정...**을 선택합니다. 그러면 빌드 설정 대화 상자가 표시됩니다.

3. 프로젝트 창에서 **HeatmapScene**, **LeaderboardScene**, **MenuScene** 및 **RaceScene** 파일을 빌드 설정 대화 상자의 **Scenes In Build** 섹션으로 끕니다.

  ![패키지 가져오기](media/vstu_azure-import-sample-assets-image2.png)

4. Unity 메뉴에서 **파일 > 프로젝트 저장**을 선택하여 빌드 설정이 저장되었는지 확인합니다.

## <a name="next-step"></a>다음 단계

* [샘플 게임 테스트](visual-studio-tools-for-unity-azure-game.md)