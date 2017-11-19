---
title: "방법: 배포 업데이트를 위한 대체 위치를 지정 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, updates
- deployment update, alternative locations
ms.assetid: 7faacd35-2638-492d-80f6-6b57e5f820de
caps.latest.revision: "15"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: a429fa17285018190530ca8058dfb4db7bcb47a2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-specify-an-alternate-location-for-deployment-updates"></a>방법: 배포 업데이트를 위한 대체 위치 지정
설치할 수 있습니다 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] CD 또는 파일 공유에서 처음 응용 프로그램이 있지만 응용 프로그램 웹 정기적 업데이트를 확인 해야 합니다. 응용 프로그램을 처음 설치한 후 웹에서 자동으로 업데이트할 수 있도록 배포 매니페스트에 업데이트에 대 한 대체 위치를 지정할 수 있습니다.  
  
> [!NOTE]
>  응용 프로그램은이 기능을 사용 하는 로컬에 설치 하려면 구성 되어야 합니다. 자세한 내용은 참조 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)합니다. 또한 설치 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 대체 위치를 설정 하면 네트워크에서 응용 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 처음 설치 하 고 이후의 모든 업데이트 모두에 대 한 해당 위치를 사용 하도록 합니다. 응용 프로그램을 로컬로 (예: CD)에서 설치 하는 경우, 원본 미디어를 사용 하 여 초기 설치를 수행 하 고 이후의 모든 업데이트는 대체 위치를 사용 합니다.  
  
### <a name="specifying-an-alternate-location-for-updates-by-using-mageuiexe-windows-forms-based-utility"></a>MageUI.exe (Windows Forms 기반 유틸리티)를 사용 하 여 업데이트에 대 한 대체 위치 지정  
  
1.  .NET Framework 명령 프롬프트를 열고 유형:  
  
     **mageui.exe**  
  
2.  에 **파일** 메뉴 선택 **열고** 응용 프로그램의 배포 매니페스트를 엽니다.  
  
3.  선택 된 **배포 옵션** 탭 합니다.  
  
4.  텍스트 상자에 라는 **시작 위치**, 응용 프로그램 업데이트를 배포 매니페스트가 들어 있는 디렉터리에 URL을 입력 합니다.  
  
5.  배포 매니페스트를 저장 합니다.  
  
### <a name="specifying-an-alternate-location-for-updates-by-using-mageexe"></a>Mage.exe를 사용 하 여 업데이트에 대 한 대체 위치 지정  
  
1.  .NET Framework 명령 프롬프트를 엽니다.  
  
2.  다음 명령을 사용 하 여 업데이트 위치를 설정 합니다. 이 예제에서는 **HelloWorld.exe.application** 에 경로 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 항상에.application 확장, 응용 프로그램 매니페스트 및 **http://adatum.com/Update/Path** url [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 업데이트를 확인 합니다.  
  
     **Mage-HelloWorld.exe.application 업데이트-ProviderUrl http://adatum.com/Update/Path**  
  
3.  파일을 저장합니다.  
  
    > [!NOTE]
    >  이제 Mage.exe 사용 하 여 파일에 다시 서명 해야 합니다. 자세한 내용은 참조 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 예: CD, 오프 라인 미디어의 응용 프로그램을 설치 하 고 컴퓨터를 온라인으로 하는 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 로 지정 된 URL에서 먼저 확인 하는 `<deploymentProvider>` 업데이트 위치 보다 최신 버전의 인스턴스가 있는지 확인 하려면 배포 매니페스트에서 태그는 응용 프로그램입니다. 그렇지 않으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 대신 초기 설치 디렉터리에서에서 직접 응용 프로그램을 설치 하 고 공용 언어 런타임 (CLR) 응용 프로그램 신뢰 결정를 사용 하 여 수준 `<deploymentProvider>`합니다. 컴퓨터가 오프 라인 상태 또는 `<deploymentProvider>` 연결할 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치 CD를와 CLR에서 설치 지점을 기반으로 신뢰를 부여. 즉 CD 설치에 대 한 응용 프로그램에 완전 신뢰가 부여 합니다. 이후의 모든 업데이트는 해당 신뢰 수준을 상속 합니다.  
  
 모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 를 사용 하는 응용 프로그램 `<deploymentProvider>` 의 응용 프로그램 매니페스트에 필요한 권한만 응용 프로그램에서 서로 다른 수준의 신뢰 서로 다른 컴퓨터에 수신 되지 않도록 명시적으로 선언 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)