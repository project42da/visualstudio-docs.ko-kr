---
title: "Visual Studio Tools for Unity Azure Walkthrough 연결 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 516A8FB2-8DFF-4BAB-8116-FDCD1C228DB3
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: f21e320fe9e27f6873b9caed3048a93bfa94a9c4
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="test-the-client-connection"></a>클라이언트 연결 테스트

이제 AzureMobileServiceClient singleton을 만들었으므로 클라이언트 연결을 테스트할 시간입니다.

## <a name="create-the-testclientconnection-script"></a>TestClientConnection 스크립트 만들기

1. Unity의 **스크립트** 폴더 안에 **TestClientConnection**라고 하는 새로운 C# 스크립트를 만듭니다.

2. Visual Studio에서 스크립트 열고 모든 템플릿 코드를 삭제한 후 다음을 추가합니다.

  ```csharp
  using System.Collections.Generic;
  using UnityEngine;
  using System.Threading.Tasks;
  using System;
  using System.Linq;
  using Microsoft.WindowsAzure.MobileServices;

  public class TestClientConnection : MonoBehaviour
  {
      void Start()
      {
          Task.Run(TestTableConnection);
      }

      private async Task TestTableConnection()
      {
          var table = AzureMobileServiceClient.Client.GetTable<CrashInfo>();

          Debug.Log("Testing ToListAsync...");
          await TestToListAsync(table);

          Debug.Log("Testing InsertAsync...");
          await TestInsertAsync(table);

          Debug.Log("Testing DeleteAsync...");
          await TestDeleteAsync(table);

          Debug.Log("All testing complete.");
      }

      private async Task TestInsertAsync(IMobileServiceTable<CrashInfo> table)
      {
          try
          {
              var allEntries = await TestToListAsync(table);
              var initialCount = allEntries.Count();

              await table.InsertAsync(new CrashInfo { X = 1, Y = 2, Z = 3 });

              allEntries = await TestToListAsync(table);
              var newCount = allEntries.Count();

              Debug.Assert(newCount == initialCount + 1, "InsertAsync failed!");
          }
          catch (Exception)
          {
              throw;
          }
      }

      private async Task<List<CrashInfo>> TestToListAsync(IMobileServiceTable<CrashInfo> table)
      {
          try
          {
              var allEntries = await table.ToListAsync();
              Debug.Assert(allEntries != null, "ToListAsync failed!");
              return allEntries;
          }
          catch (Exception)
          {

              throw;
          }
      }

      private async Task TestDeleteAsync(IMobileServiceTable<CrashInfo> table)
      {
          var allEntries = await TestToListAsync(table);

          foreach (var item in allEntries)
          {
              try
              {
                  await table.DeleteAsync(item);
              }
              catch (Exception)
              {
                  throw;
              }
          }

          allEntries = await TestToListAsync(table);

          Debug.Assert(allEntries.Count() == 0, "DeleteAsync failed!");
      }
  }
  ```

3. Unity **GameObject** 메뉴에서 **GameObject > 빈 항목 만들기**를 선택하여 Unity 장면에서 빈 GameObject를 만듭니다. 이름을 **TestClientConnection**으로 바꿉니다.

4. Unity **프로젝트** 창에서 TestClientConnection 스크립트를 **계층 구조** 창의 TestClientConnection GameObject로 **끕니다**.

5. Unity 메뉴에서 **파일 > 다른 이름으로 장면 저장...**을 선택합니다. 장면 이름을 **클라이언트 연결 테스트**로 지정하고 **저장**을 클릭합니다.

5. Unity에서 **재생** 단추를 클릭하고 콘솔 창을 관찰합니다. 실패한 어설션이 없는지 확인합니다.

6. Azure Portal에서 CrashInfo 간편한 테이블을 엽니다. 이제 **X, Y, Z** 좌표**(1, 2, 3)**의 항목과 **삭제** 열에 **true** 값이 있어야 합니다. 테스트를 실행할 때마다 값은 동일하지만 고유한 ID의 새 항목이 테이블에 추가되어야 합니다.

  ![간편한 테이블 항목](media/vstu_azure-test-client-connection-image1.png)

## <a name="next-step"></a>다음 단계
* [샘플 게임 자산 가져오기](visual-studio-tools-for-unity-azure-game-assets.md)
