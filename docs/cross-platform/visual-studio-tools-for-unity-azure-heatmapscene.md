---
title: Visual Studio Tools for Unity Azure Walkthrough HeatmapScene| Microsoft Docs
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: E11DA08B-7341-4743-A817-0CAD59844305
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 472b6d5adae5e23007b9c1aa4d9c75118a94e1cc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="heatmapscene-explanation"></a>HeatmapScene 설명

HeatmapScene은 **LevelGeometry** prefab의 인스턴스를 포함합니다. 이러한 방식으로 충돌에 대한 좌표가 Azure Map에서 레벨 아트로 올바르게 로드됩니다.

## <a name="heatmap-script"></a>열 지도 스크립트

### <a name="initializecrashlistasync"></a>InitializeCrashListAsync
`InitializeCrashListAsync`는 Azure의 CrashInfo 간편한 테이블에 연결하여 <a href="https://msdn.microsoft.com/en-us/library/azure/jj554274(v=azure.10).aspx">`ToListAsync`</a>를 사용하여 모든 항목을 목록에 추가합니다.

```
private async Task InitializeCrashListAsync()
 {
     Debug.Log("Downloading crash data from Azure...");

     for (int i = 0; i < numberOfAttempts; i++)
     {
         try
         {
             Debug.Log("Connecting... attempt " + (i +1));
             crashesFromServer = await crashesTable.ToListAsync();
             Debug.Log("Done downloading.");
             return;
         }
         catch (System.Exception e)
         {
             Debug.Log("Error connecting: " + e.Message);
         }

         if (i == numberOfAttempts - 1)
             Debug.Log("Connection failed. Check logs, try again later.");
         else
             await Task.Delay(500);
     }
 }
```

### <a name="spawnmarkersfromlist"></a>SpawnMarkersFromList
`SpawnMarkersFromList`는 Azure에서 수신한 충돌 목록을 반복하며 각 항목에 대한 충돌 마커 prefab을 인스턴스화합니다.

```csharp
private void SpawnMarkersFromList()
{
    foreach (var item in crashesFromServer)
    {
        GameObject marker = GameObject.Instantiate(markerPrefab);
        marker.transform.position = new Vector3 { x = item.X, y = item.Y, z = item.Z };
    }
}
```

### <a name="deletecrashdataasync"></a>DeleteCrashDataAsync

사용자가 **데이터 지우기** 단추를 누르면 `DeleteCrashDataAsync`이(가) 호출됩니다. 로컬 충돌 목록을 반복하며 각 항목에 대해 <a href="https://msdn.microsoft.com/en-us/library/azure/jj554258(v=azure.10).aspx">`DeleteAsync`</a>를 호출합니다. 이를 통해 간편한 테이블에서 각 항목의 **삭제** 열이 **true**로 설정됩니다. `ToListAsync`는 삭제된 항목을 무시합니다.

```csharp
public async void DeleteCrashDataAsync()
{
    Debug.Log("Deleting crash data...");
    foreach (var item in crashesFromServer)
    {
        try
        {
            await crashesTable.DeleteAsync(item);
        }
        catch (System.Exception e)
        {
            Debug.Log("Error deleting crash data: " + e.Message);
        }
        Debug.Log("Done deleting crash data.");
    }
    SceneManager.LoadScene(SceneManager.GetActiveScene().name);
}
```

## <a name="next-step"></a>다음 단계

* [LeaderboardScene 설명](visual-studio-tools-for-unity-azure-leaderboardscene.md)