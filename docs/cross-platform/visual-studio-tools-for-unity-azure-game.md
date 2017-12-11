---
title: "Visual Studio Tools for Unity Azure Walkthrough 게임 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: DA86FC7F-E456-4DFC-84BF-D780421508B9
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 204389c2341c3aa9f729b92b5f3d459e7b101d24
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="test-the-sample-game"></a>샘플 게임 테스트

샘플 게임은 플레이어의 행동에 대한 데이터를 기록하여 Azure 간편한 테이블에 저장하는 간단한 레이싱 게임입니다. 이 샘플 게임에는 Azure에서 데이터를 읽어서 플레이어를 위해 시각화하는 장면이 포함되어 있습니다.

이 섹션은 샘플 게임을 플레이하고 제대로 작동하고 있는지 확인하는 방법을 간단하게 설명합니다. 다음 섹션에서는 샘플 게임의 작동 방식을 더 자세히 설명합니다.

## <a name="starting-the-game"></a>게임 시작

1. Unity 프로젝트 창에서 **자산/Azure 간편한 테이블 샘플 게임 자산/장면** 폴더로 이동합니다.

2. **MenuScene**을 두 번 클릭하여 엽니다.

3. Unity 게임 창에서 **화면비 드롭다운**을 클릭하고 **16:9**를 선택합니다.

  ![화면비 설정](media/vstu_azure-test-sample-game-image1.png)

4. **플레이** 단추를 클릭하여 Unity 편집기에서 게임을 실행합니다.


## <a name="complete-a-race"></a>레이스 완료

순위표 또는 열 지도를 보기 전에 적어도 한 번은 레이스를 완료하여 일부 샘플 데이터를 만드는 것이 가장 좋습니다.

1. Unity 편집기에서 게임을 실행하면서 **경주!** 단추를 클릭하여 새 레이스를 시작합니다.

2. **WASD** 또는 **화살표 키**를 사용하여 자동차를 운전하고 시계 방향으로 트랙을 완주합니다. 예를 들기 위해 경주하면서 벽에 충돌해 보세요. Unity 콘솔의 디버그 출력에서 충돌이 기록되었음을 나타내야 합니다.

  >[!NOTE]
  > 자동차를 뒤집고 계속할 수 없다면 **다시 시작**을 클릭하세요. 완주하면 데이터는 Azure로만 전송됩니다.

  ![레이스 시작](media/vstu_azure-test-sample-game-image2.png)

3. 체크 무늬의 결승선을 통과하면 게임은 **끝** 메시지를 표시해야 합니다. 이 지점에서 총돌 데이터가 Azure로 업로드됩니다.

4. 상위 10위의 빠른 경주 시간을 기록했다면 고득점자로 이름을 입력하라는 메시지가 표시됩니다. 이름을 입력하고 **제출**을 클릭합니다.

  ![레이스 시작](media/vstu_azure-test-sample-game-image3.png)

## <a name="view-the-heatmap"></a>열 지도 보기

1. 레이스 장면에서 **충돌 열 지도 보기** 단추를 클릭하거나 기본 메뉴에서 **충돌 열 지도**를 선택합니다.

2. 열 지도 장면은 Azure의 CrashInfo 테이블에서 데이터를 로드하며 플레이어가 경주 트랙 벽에 충돌한 위치에 투명한 적색구를 표시합니다. 중복된 곳에 여러 충돌이 발생한 경우에는 구가 더 밝게 나타납니다.

  ![열 지도](media/vstu_azure-test-sample-game-image4.png)

## <a name="view-the-leaderboard"></a>순위표 보기

1. 레이스 장면 또는 기본 메뉴에서 **순위표** 단추를 클릭합니다.

2. 순위표 장면은 Azure의 HighScoreInfo 테이블에서 고득점 데이터를 로드하고 각 고득점 입력에 대한 플레이어 이름과 기록을 표시합니다.

  ![순위표](media/vstu_azure-test-sample-game-image5.png)

## <a name="next-step"></a>다음 단계

* [RaceScene 설명](visual-studio-tools-for-unity-azure-racescene.md)
