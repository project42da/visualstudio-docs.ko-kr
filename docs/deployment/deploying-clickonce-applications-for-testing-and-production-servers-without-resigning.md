---
title: 테스트를 위해 ClickOnce 응용 프로그램을 배포 하 고 다시 서명 하지 않고도 프로덕션 서버 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, deploying without resigning
- ClickOnce deployment, without resigning
- application updates, ClickOnce
- update location [ClickOnce]
- deploymentProvider tag
- manifests [ClickOnce]
ms.assetid: 1218a98d-1ad5-4eef-95dd-0e0b3c44168c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b4c71e1bd6f224fdd0198ce7850c92364126d7e3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="deploying-clickonce-applications-for-testing-and-production-servers-without-resigning"></a>다시 서명하지 않고 테스트 및 프로덕션 서버용 ClickOnce 응용 프로그램 배포
이 항목에서는.NET Framework 버전 3.5 ClickOnce 변경 하거나 다시 서명 하지 않고 여러 네트워크 위치에서 ClickOnce 응용 프로그램을 배포할 수 있도록 매니페스트에 도입 된 ClickOnce의 새로운 기능을 설명 합니다.  
  
> [!NOTE]
>  새 버전의 응용 프로그램을 배포 하기 위한 기본 방법이 여전히가 다시 서명 합니다. 가능한 경우 항상 서명 메서드를 사용 합니다. 자세한 내용은 [Mage.exe(매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)를 참조하세요.  
  
 제 3 자 개발자나 Isv 수에 옵트인이 기능을 보다 쉽게 고객에 게 해당 응용 프로그램을 업데이트 합니다. 다음과 같은 상황에서이 기능을 사용할 수 있습니다.  
  
-   응용 프로그램을 응용 프로그램의 첫 번째 설치 되지 않습니다 업데이트할 때.  
  
-   하나의 구성만 컴퓨터에서 응용 프로그램의 경우. 예를 들어 서로 다른 두 데이터베이스를 가리키도록 구성 된 응용 프로그램,이 기능을 사용할 수 없습니다.  
  
## <a name="excluding-deploymentprovider-from-deployment-manifests"></a>배포 매니페스트에 deploymentProvider 제외  
 .NET Framework 2.0 및.NET Framework 3.0에서 오프 라인 사용 가능에 대 한 시스템에 설치 하는 ClickOnce 응용 프로그램 지정 해야 합니다는 `deploymentProvider` 의 배포 매니페스트에 합니다. `deploymentProvider` 업데이트 위치; 라고도 하는 ClickOnce 응용 프로그램 업데이트를 확인 하는 위치입니다. 해당 배포에 서명 하는 응용 프로그램 게시자에 대 한 요구와 결합 되어이 요구 사항은 공급 업체 또는 다른 제 3 자에서 ClickOnce 응용 프로그램을 업데이트 하는 회사 어렵게 합니다. 예제도에서는 동일한 네트워크에 여러 위치에서 동일한 응용 프로그램을 배포 하기가 더 어려워집니다.  
  
 .NET Framework 3.5에서 ClickOnce에 대 한 변경 내용으로, 그런 다음 자체 네트워크에서 응용 프로그램을 배포할 수 있는 다른 조직의 ClickOnce 응용 프로그램을 제공 하는 제 3 자에 대 한 같습니다.  
  
 ClickOnce 응용 프로그램 개발자는이 기능을 활용 하기 위해 제외 해야 `deploymentProvider` 배포에서 매니페스트 합니다. 즉, 제외 하 고는 `-providerUrl` Mage.exe 또는 수 있도록 배포를 만들 때 인수 매니페스트는 **시작 위치** 텍스트 상자에는 **응용 프로그램 매니페스트** 탭 비어 있는 경우 있습니다 MageUI.exe와 함께 배포 매니페스트를 생성 하는 합니다.  
  
## <a name="deploymentprovider-and-application-updates"></a>deploymentProvider 및 응용 프로그램 업데이트  
 .NET Framework 3.5 이상에서는 더 이상 지정 해야는 `deploymentProvider` 온라인 및 오프 라인 사용에 대 한 ClickOnce 응용 프로그램을 배포 하려면 배포 매니페스트에 합니다. 이 패키지 및를 직접 배포에 서명 되었지만 해당 네트워크를 통해 응용 프로그램을 배포 하도록 다른 회사를 허용 해야 하는 시나리오를 지원 합니다.  
  
 점을 기억해 야 하는 제외 된 응용 프로그램은 `deploymentProvider` 포함 하는 업데이트 제공 될 때까지 업데이트 하는 동안 해당 설치 위치를 변경할 수 없습니다는 `deploymentProvider` 다시 태그를 지정 합니다.  
  
 다음은이 점을 명확히 하기 위해 두 가지 예입니다. 첫 번째 예에서는 게시 되지 않는 ClickOnce 응용 프로그램 `deploymentProvider` 태그 및 하면에서 설치를 사용자에 게 http://www.adatum.com/MyApplication/합니다. 응용 프로그램의 다음 업데이트를 게시할 것인지를 결정 하는 경우 http://subdomain.adatum.com/MyApplication/에 상주 하는 배포 매니페스트의이 이름임을 수 있는 방법이 나면 http://www.adatum.com/MyApplication/합니다. 다음 두 가지 중 하나를 수행할 수 있습니다.  
  
-   이전 버전을 제거 하 고 새 위치에서 새 버전을 설치 합니다.  
  
-   에 대 한 업데이트를 포함할 http://www.adatum.com/MyApplication/ 포함 하는 `deploymentProvider` 가리키는 http://www.adatum.com/MyApplication/합니다. 그런 다음 나중에 다른 업데이트를 릴리스 `deploymentProvider` 가리키는 http://subdomain.adatum.com/MyApplication/합니다.  
  
 두 번째 예제에서 지정 하는 ClickOnce 응용 프로그램 게시 `deploymentProvider`를 제거 하려면 다음 결정 합니다. 사용 하지 않는 새 버전에 한 번 `deploymentProvider` 다운로드 한 클라이언트에 됩니다 있는 응용 프로그램의 버전을 출시 될 때까지 업데이트에 대 한 사용 되는 경로 리디렉션할 수 `deploymentProvider` 복원 합니다. 첫 번째 예제와 마찬가지로 `deploymentProvider` 처음 새 위치가 아니라 현재 업데이트 위치를 가리켜야 합니다. 이 경우 삽입 하려고 하는 경우는 `deploymentProvider` 참조 하는 http://subdomain.adatum.com/MyApplication/, 다음 업데이트에 실패 합니다.  
  
## <a name="creating-a-deployment"></a>배포 만들기  
 에 다른 네트워크 위치에서 배포 될 수 있는 배포를 만드는 단계별 지침을 참조 하십시오. [연습: ClickOnce 응용 프로그램 해당 않습니다 하지 필요한 항목을 수동으로 배포 하 고 해당 유지 브랜딩 정보](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md).  
  
## <a name="see-also"></a>참고 항목  
 [Mage.exe(매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)