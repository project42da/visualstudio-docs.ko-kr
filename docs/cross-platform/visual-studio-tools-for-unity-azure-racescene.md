---
title: Visual Studio Tools for Unity Azure Walkthrough RaceScene| Microsoft Docs
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1F9304E8-0F1B-4325-8BED-FE3EB0ADCE8D
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 7dc57628774624975cc6ede5bd241f322472bfe6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="racescene-explanation"></a>RaceScene 설명

RaceScene는 Unity [표준 자산](https://www.assetstore.unity3d.com/en/#!/content/32351)을 사용하여 기본 레이싱 게임과 레벨을 구성합니다. 이 섹션에서는 아래 스크린샷에 표시된 대로 RaceScene 계층 구조에서 나열된 순서로 관련 GameObject 및 해당 스크립트가 설명됩니다.

![RaceScene](media/vstu_azure-racescene-explanation-image1.png)

## <a name="multipurposecamerarig"></a>MultipurposeCameraRig

**MultipurposeCameraRig**는 **카메라** 표준 자산 패키지에 포함된 것입니다. Inspector 속성은 적절한 속도로 자동차를 따라가도록 조정되었습니다.

## <a name="levelgeometry"></a>LevelGeometry

LevelGeometry prefab은 구성에 사용되는 빈 GameObject입니다. 자식 GameObject는 플레이 가능한 공간을 구성합니다. 바닥, 벽, 진입로 및 장애물은 모두 **원형 생성** 표준 자산 패키지의 prefab으로 제작됩니다.

**한 가지 중요한 사항**은 Azure에서 레코딩되는 충돌에 대해 객체가 테스트되는 순서에서 **벽** 태그가 적용되어야 합니다.

![RaceScene](media/vstu_azure-racescene-explanation-image2.png)

## <a name="car"></a>자동차

**자동차** prefab은 **차량** 표준 자산 패키지에 포함되어 있습니다. 유일한 수정 사항은 **RecordCrashInfo** 스크립트 구성 요소가 추가되었다는 것입니다.

### <a name="recordcrashinfo"></a>RecordCrashInfo

이 스크립트는 `OnCollisionEnter`에서 충돌을 확인하고 목록에 레코딩합니다. `crashRecordingCooldown` 및 `crashRecordingMinVelocity`은(는) 관련 데이터 집합을 유지하기 위해 게임에서 충돌로 간주하는 것을 제한합니다.

`RaceFinished` 이벤트가 발생하면 `UploadNewCrashDataAsync`는 목록의 각 충돌을 Azure의 CrashInfo 간편한 테이블로 보냅니다.

```Csharp
using System.Collections;
using System.Collections.Generic;
using System.Threading.Tasks;
using UnityEngine;

public class RecordCrashInfo : MonoBehaviour
{
    [Tooltip("Time in seconds after a crash before a new crash can be recorded.")]
    [SerializeField]
    private float crashRecordingCooldown = 1;

    [Tooltip("How fast car must be traveling before crash can be recorded.")]
    [SerializeField]
    private float crashRecordingMinVelocity = 8;

    [SerializeField]
    private Rigidbody carRigidbody;

    [SerializeField]
    private GameObject crashMarkerPrefab;

    [Tooltip("If turned on, crash markers spawn when the player crashes.")]
    [SerializeField]
    private bool spawnDebugMarkers = false;

    private bool isOnCooldown = false;
    private bool meetsMinVelocity = false;
    private bool isRaceFinished = false;

    private List<CrashInfo> newCrashes = new List<CrashInfo>();

    private void LateUpdate()
    {
        // We have to update this in LateUpdate as opposed to checking in OnCollisionEnter.
        // The car's velocity has already decreased from crashing by the time
        // OnCollisionEnter gets called.

        meetsMinVelocity = carRigidbody.velocity.magnitude >= crashRecordingMinVelocity;
    }

    private void OnCollisionEnter(Collision collision)
    {
        if (!isRaceFinished && collision.gameObject.tag == "Wall" && !isOnCooldown && meetsMinVelocity)
        {
            Debug.Log("Collided with wall!");

            newCrashes.Add(new CrashInfo
            {
                X = collision.transform.position.x,
                Y = collision.transform.position.y,
                Z = collision.transform.position.z
            });

            if (spawnDebugMarkers && Debug.isDebugBuild)
                Instantiate(crashMarkerPrefab, collision.transform.position, Quaternion.identity);

            isOnCooldown = true;
            StartCoroutine(Cooldown());
        }  
    }

    private IEnumerator Cooldown()
    {
        yield return new WaitForSeconds(crashRecordingCooldown);

        isOnCooldown = false;
    }

    private void OnRaceFinished()
    {
        Task.Run(UploadNewCrashDataAsync);
    }

    private async Task UploadNewCrashDataAsync()
    {
        var crashTable = AzureMobileServiceClient.Client.GetTable<CrashInfo>();

        try
        {
            Debug.Log("Uploading crash data to Azure...");

            foreach (var item in newCrashes)
            {
                await crashTable.InsertAsync(item);
            }
            Debug.Log("Finished uploading crash data.");
        }
        catch (System.Exception e)
        {
            Debug.Log("Error uploading crash data: " + e.Message);
        }

    }

    private void OnEnable()
    {
        Checkpoint.RaceFinished += OnRaceFinished;
    }

    private void OnDisable()
    {
        Checkpoint.RaceFinished -= OnRaceFinished;
    }

}
```

## <a name="checkpoints"></a>checkpoints

이 수준에는 **체크포인트** 스크립트 구성 요소와 함께 4개의 GameObject가 있습니다. 체크포인트는 플레이어를 잘못된 길로 안내하여 레이스를 마치지 못하게 합니다. 또한, 플레이어가 레이스를 마치면 이를 감지하기도 합니다. `RaceFinished` 이벤트가 호출되는 곳입니다.

## <a name="invisible-collision"></a>투명 충돌

MeshRenderer 구성 요소가 비활성화된 표준 원시 큐브는 투명 충돌로 사용되어 플레이어가 되돌아오게 합니다. 또한, **탄력성** 물리학 소재가 적용되어 날으는 자동차가 만족스러운 방식으로 투명 벽에서 튕겨져 나가고 플레이어가 투명 벽에 부딪히거나 미끄러져 내려가고 투명 벽 꼭대기에 착지하지 못하게 합니다.

## <a name="recordhighscore"></a>RecordHighScore

이 스크립트는 플레이어가 새로운 높은 점수를 획득했는지 확인합니다. 높은 점수가 있는 경우 플레이어가 이름을 입력하고 **제출**을 클릭할 수 있도록 `enterNamePopup`을 표시합니다.

플레이어 이름을 제출하면 `UploadNewHighScoreAsync`가 호출되고 새로운 높은 점수가 Azure의 HighScoreInfo 간편한 테이블로 보내집니다.

```csharp
using System.Collections;
using System.Collections.Generic;
using Microsoft.WindowsAzure.MobileServices;
using UnityEngine;
using System.Threading.Tasks;
using System;
using System.Linq;
using UnityEngine.UI;

public class RecordHighScore : MonoBehaviour
{
    [SerializeField]
    private InputField nameInputField;

    [SerializeField]
    private CanvasGroup enterNamePopup;

    private List<HighScoreInfo> highScores;
    private string playerName = string.Empty;

    private async void Start()
    {
        ShowEnterNamePopup(false);
        highScores = await Leaderboard.GetTopHighScoresAsync();
    }

    private void ShowEnterNamePopup(bool shouldShow)
    {
        enterNamePopup.alpha = shouldShow ? 1 : 0;
        enterNamePopup.interactable = shouldShow;
    }

    public void SubmitButtonClicked()
    {
        playerName = nameInputField.text;
    }

    private async void OnAfterMostRecentScoreSet(float newScore)
    {
        bool isNewHighScore = CheckForNewHighScore(newScore);

        if (isNewHighScore)
        {
            Debug.Log("New High Score!");
            await GetPlayerNameAsync();
            await UploadNewHighScoreAsync(newScore);
        }
        else
        {
            Debug.Log("No new high score.");
        }
    }

    private async Task GetPlayerNameAsync()
    {
        // Wait a bit before showing the popup.
        // This just helps the player experience feel
        // less jarring.
        await Task.Delay(2000);
        ShowEnterNamePopup(true);

        // Wait until the player enters a name and clicks submit.
        // OnSubmitButtonClicked will set the playerName.
        while (playerName == string.Empty)
        {
            await Task.Delay(100);
        }

        ShowEnterNamePopup(false);
    }

    private bool CheckForNewHighScore(float newScore)
    {
        Debug.Log("Checking for a new high score...");

        bool isHighScoreListFull = highScores.Count >= Leaderboard.SizeOfHighScoreList;
        var lowerScores = highScores.Where(x => x.Time > newScore);

        return lowerScores.Count() > 0 || !isHighScoreListFull;
    }

    private async Task UploadNewHighScoreAsync(float newScore)
    {
        var newHighScoreInfo = new HighScoreInfo { Name = playerName, Time = newScore };

        try
        {
            Debug.Log("Uploading high score data to Azure...");

            await Leaderboard.HighScoreTable.InsertAsync(newHighScoreInfo);

            Debug.Log("Finished uploading high score data.");
        }
        catch (System.Exception e)
        {
            Debug.Log("Error uploading high score data: " + e.Message);
        }
    }

    private void OnEnable()
    {
        LapTimer.AfterMostRecentScoreSet += OnAfterMostRecentScoreSet;
    }

    private void OnDisable()
    {
        LapTimer.AfterMostRecentScoreSet -= OnAfterMostRecentScoreSet;
    }

}
```

## <a name="next-step"></a>다음 단계

* [HeatmapScene 설명](visual-studio-tools-for-unity-azure-heatmapscene.md)
