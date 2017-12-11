---
title: "Visual Studio Tools for Unity Azure Walkthrough 모바일 클라이언트 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5A8762A1-D843-4FD8-A89B-E5E489ECA03D
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 294942641aa0739d105a888f4fbfe6ba9cf05a16
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="implement-the-azure-mobileserviceclient"></a>Azure MobileServiceClient 구현

Azure Mobile Client SDK의 중심 기능은 모바일 앱 백엔드 액세스를 지원하는 <a href="https://msdn.microsoft.com/en-us/library/azure/microsoft.windowsazure.mobileservices.mobileserviceclient(v=azure.10).aspx">MobileServiceClient</a>입니다.

## <a name="locate-the-url-of-the-mobile-app-backend"></a>모바일 앱 백엔드의 URL 찾기

`MobileServiceClient` 생성자는 모바일 앱 URL을 매개변수로 사용하므로 계속하기 전에 URL를 찾습니다.

1. Azure Portal에서 **App Services** 단추를 클릭합니다.

    ![App Services 클릭](media/vstu_azure-implement-azure-mobileserviceclient-image1.png)

2. 모바일 앱의 입력 항목을 클릭합니다.

    ![모바일 앱 클릭](media/vstu_azure-implement-azure-mobileserviceclient-image2.png)

3. 모바일 앱 백엔드의 URL을 복사합니다.

    ![URL 복사](media/vstu_azure-implement-azure-mobileserviceclient-image3.png)

## <a name="create-the-mobileserviceclient-singleton"></a>MobileServiceClient singleton 만들기

`MobileServiceClient`의 단일 인스턴스가 있으므로, 연습에서는 singleton 패턴의 변형을 사용합니다.

1. Unity 프로젝트의 **Assets/Scripts** 디렉터리 내부에서 **AzureMobileServiceClient**라는 새 C# 스크립트를 만듭니다.

2. `AzureMobileServiceClient` 스크립트를 열고 using 문과 클래스 선언을 사용하여 기존 템플릿 코드를 삭제합니다.

3. 다음 코드를 추가합니다.

  ```csharp
  using Microsoft.WindowsAzure.MobileServices;

  public static class AzureMobileServiceClient
  {
      private const bool ignoreTls = true;
      private const string backendUrl = "MOBILE_APP_URL";
      private static MobileServiceClient client;

      public static MobileServiceClient Client
      {
          get
          {
              if (client == null)
              {
                  client = new MobileServiceClient(backendUrl);
              }

              return client;
          }
      }
  }
  ```

  > [!NOTE]
  > IntelliSense가 Microsoft.WindowsAzure 네임스페이스를 인식하지 않을 경우 [개발 환경 준비]() 섹션에서 모든 단계를 완료했는지 확인하세요.

4. 이전 코드에서 `MOBILE_APP_URL`을 모바일 앱 백엔드의 URL로 바꿉니다.

## <a name="next-step"></a>다음 단계

* [Unity Mono 보안 저장소 업데이트](visual-studio-tools-for-unity-azure-security.md)
