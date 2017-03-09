---
title: "다시 서명하지 않고 테스트 및 프로덕션 서버용 ClickOnce 응용 프로그램 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 업데이트, ClickOnce"
  - "ClickOnce 응용 프로그램, 다시 서명 없이 배포"
  - "ClickOnce 배포, 다시 서명하지 않음"
  - "deploymentProvider 태그"
  - "매니페스트[ClickOnce]"
  - "업데이트 위치[ClickOnce]"
ms.assetid: 1218a98d-1ad5-4eef-95dd-0e0b3c44168c
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 다시 서명하지 않고 테스트 및 프로덕션 서버용 ClickOnce 응용 프로그램 배포
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 .NET Framework 버전 3.5에 도입된 ClickOnce의 새 기능에 대해 설명합니다. 이 기능을 사용하면 다시 서명하거나 ClickOnce 매니페스트를 변경하지 않고 여러 네트워크 위치에서 ClickOnce 응용 프로그램을 배포할 수 있습니다.  
  
> [!NOTE]
>  다시 서명하여 새 버전의 응용 프로그램을 배포하는 방법이 가장 좋으므로  가능하면 다시 서명하는 방법을 사용하는 것이 좋습니다.  자세한 내용은 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)를 참조하십시오.  
  
 타사 개발자 및 ISV는 이 기능을 사용하여 자사 고객들이 자사 응용 프로그램을 보다 손쉽게 업데이트하도록 할 수 있습니다.  이 기능은 다음과 같은 경우에 사용할 수 있습니다.  
  
-   응용 프로그램을 처음 설치하는 것이 아니라 업데이트하는 경우  
  
-   컴퓨터에 응용 프로그램에 대한 구성이 하나만 있는 경우.  예를 들어, 응용 프로그램이 서로 다른 두 데이터베이스를 가리키도록 구성된 경우에는 이 기능을 사용할 수 없습니다.  
  
## 배포 매니페스트에서 deploymentProvider 제외  
 .NET Framework 2.0 및 .NET Framework 3.0에서는 오프라인으로 사용하도록 시스템에 설치된 모든 ClickOnce 응용 프로그램이 해당 배포 매니페스트에 `deploymentProvider`를 지정해야 합니다.  `deploymentProvider`는 업데이트 위치라고도 하는데, 이 위치는 ClickOnce가 응용 프로그램 업데이트가 있는지 확인하는 위치입니다.  응용 프로그램 게시자가 해당 배포에 서명해야 해는 필요성과 연관된 이 요구 사항은 특정 회사에서 공급업체나 타사의 ClickOnce 응용 프로그램을 업데이트하는 것을 어렵게 할 뿐 아니라  같은 네트워크의 여러 위치에서 동일한 응용 프로그램을 배포하는 것도 더 어렵게 합니다.  
  
 .NET Framework 3.5에서는 ClickOnce가 변경되어 타사에서 다른 조직에 ClickOnce 응용 프로그램을 제공할 수 있습니다. 그러면 ClickOnce 응용 프로그램을 받은 조직에서는 ClickOnce 응용 프로그램을 자체 네트워크에 배포할 수 있습니다.  
  
 이 기능을 사용하려면 ClickOnce 응용 프로그램의 개발자는 해당 배포 매니페스트에서 `deploymentProvider`를 제외해야 합니다.  즉, Mage.exe를 사용하여 배포 매니페스트를 만들 때 `-providerUrl` 인수를 제외하거나 MageUI.exe를 사용하여 배포 매니페스트를 만들 때 **응용 프로그램 매니페스트** 탭의 **시작 위치** 텍스트 상자가 비어 있는지 확인합니다.  
  
## deploymentProvider 및 응용 프로그램 업데이트  
 .NET Framework 3.5부터는 온라인과 오프라인으로 모두 사용하도록 ClickOnce 응용 프로그램을 배포하기 위해 더 이상 배포 매니페스트에 `deploymentProvider`를 지정하지 않아도 됩니다.  이것은 배포를 직접 패키지하고 서명해야 하지만 타사에서 자사 네트워크를 통해 응용 프로그램을 배포하도록 허용하는 시나리오를 지원합니다.  
  
 `deploymentProvider`가 제외된 응용 프로그램은 `deploymentProvider` 태그가 포함된 업데이트가 다시 제공될 때까지 업데이트하는 동안 해당 설치 위치를 변경할 수 없습니다.  
  
 다음은 이러한 내용을 명확하게 보여 주는 두 가지 예제입니다.  첫 번째 예제에서는 `deploymentProvider` 태그가 없는 ClickOnce 응용 프로그램을 게시하고 사용자에게 http:\/\/www.adatum.com\/MyApplication\/에서 이 응용 프로그램을 설치하도록 요청합니다.  그러나 http:\/\/subdomain.adatum.com\/MyApplication\/에 이 응용 프로그램의 다음 업데이트를 게시하려는 경우 http:\/\/www.adatum.com\/MyApplication\/에 있는 배포 매니페스트에서 이를 나타낼 수 있는 방법이 없습니다.  이 경우 다음 두 작업 중 하나를 수행할 수 있습니다.  
  
-   사용자에게 이전 버전을 제거하고 새 위치에서 새 버전을 설치하도록 요청  
  
-   http:\/\/www.adatum.com\/MyApplication\/을 가리키는 `deploymentProvider`가 있는 http:\/\/www.adatum.com\/MyApplication\/에 업데이트를 저장한 다음  http:\/\/subdomain.adatum.com\/MyApplication\/을 가리키는 `deploymentProvider`를 사용하여 나중에 다른 업데이트 발표  
  
 두 번째 예제에서는 `deploymentProvider`를 지정하는 ClickOnce 응용 프로그램을 게시한 다음 이를 제거하도록 선택합니다.  `deploymentProvider`가 없는 새 버전이 클라이언트로 다운로드되면 복원된 `deploymentProvider`가 있는 응용 프로그램 버전을 출시할 때까지 업데이트에 사용된 경로를 리디렉션할 수 없습니다.  첫 번째 예제와 마찬가지로 `deploymentProvider`는 처음에는 새 위치가 아니라 현재 업데이트 위치를 가리켜야 합니다.  이 경우 http:\/\/subdomain.adatum.com\/MyApplication\/을 참조하는 `deploymentProvider`를 삽입하려고 하면 다음 업데이트가 실패합니다.  
  
## 배포 만들기  
 여러 네트워크 위치에서 배포할 수 있는 배포를 만드는 방법에 대한 단계별 지침은 [연습: 다시 서명할 필요가 없고 브랜드 정보가 유지되는 ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md)를 참조하십시오.  
  
## 참고 항목  
 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)   
 [MageUI.exe \(매니페스트 생성 및 편집 도구, 그래픽 클라이언트\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)