---
title: "Visual Studio Tools for Unity Azure Walkthrough 데이터 모델 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6FCCA8D1-0D06-4B2A-A55F-FC3D1FEA0F56
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: e3b6064a3947f57ffcbe6422162c6c72fca0ab21
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="create-data-model-classes"></a>데이터 모델 클래스 만들기

Unity 프로젝트는 Azure Mobile App 백엔드에서 생성된 테이블에 해당하는 데이터 모델 클래스를 포함해야 합니다.

## <a name="create-the-crashinfo-class"></a>CrashInfo 클래스 만들기

1. Unity에서 **스크립트**라고 하는 루트 **자산** 디렉터리에서 새 폴더를 추가합니다. 새 스크립트 폴더 안에 **데이터 모델**이라고 하는 다른 새 폴더를 만듭니다. 단지 구성을 위한 것입니다.

2. 새 데이터 모델 폴더에서 **CrashInfo**라고 하는 새로운 C# 스크립트를 만듭니다.

3. 새 `CrashInfo` 스크립트를 열고 클래스 선언을 포함하고 문을 사용하는 템플릿 코드를 삭제하며 다음을 추가합니다.

  ```csharp
  public class CrashInfo
  {
      public string Id { get; set; }
      public float X { get; set; }
      public float Y { get; set; }
      public float Z { get; set; }
  }
  ```

  > [!WARNING]
  > 연습을 제대로 작동하려면 데이터 모델 클래스의 이름이 Azure Mobile App 백엔드에서 만든 간편한 테이블의 이름과 일치해야 합니다.

## <a name="create-the-highscoreinfo-class"></a>HighScoreInfo 클래스 만들기

1. 데이터 모델 폴더 안에 **HighScoreInfo**라고 하는 새 C# 스크립트를 만듭니다.

2. 새 `HighScoreInfo` 스크립트를 열고 클래스 선언을 포함하고 문을 사용하는 템플릿 코드를 삭제하며 다음을 추가합니다.

  ```csharp
  public class HighScoreInfo
  {
      public string Name { get; set; }
      public float Time { get; set; }
      public string Id { get; set; }
  }
  ```

  ## <a name="next-step"></a>다음 단계

  * [Azure MobileServiceClient 구현](visual-studio-tools-for-unity-azure-mobile-client.md)
