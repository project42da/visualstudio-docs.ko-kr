---
title: "방법: 배포 업데이트를 위한 대체 위치 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "ClickOnce 배포, 업데이트"
  - "배포 업데이트, 대체 위치"
ms.assetid: 7faacd35-2638-492d-80f6-6b57e5f820de
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: 배포 업데이트를 위한 대체 위치 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 처음 설치할 때는 CD나 파일 공유 위치를 사용할 수 있지만 일단 응용 프로그램을 설치한 후에는 정기적으로 웹에서 업데이트 여부를 확인해야 합니다.  처음 설치한 이후 웹에서 응용 프로그램을 자동으로 업데이트할 수 있도록 배포 매니페스트에 업데이트 대체 위치를 지정할 수 있습니다.  
  
> [!NOTE]
>  이 기능을 사용하려면 응용 프로그램을 로컬로 설치하도록 구성해야 합니다.  자세한 내용은 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)를 참조하십시오.  또한 네트워크를 통해 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 설치하는 경우 대체 위치를 설정하면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 초기 설치와 이후의 모든 업데이트에 모두 이 위치를 사용합니다.  CD를 사용하는 경우와 같이 응용 프로그램을 로컬로 설치하는 경우 초기 설치는 원본 미디어를 사용하여 수행되고 이후의 모든 업데이트에는 대체 위치가 사용됩니다.  
  
### Windows Forms 기반 유틸리티인 MageUI.exe를 사용하여 업데이트 대체 위치 지정  
  
1.  .NET Framework 명령 프롬프트를 열고 다음을 입력합니다.  
  
     **mageui.exe**  
  
2.  **파일** 메뉴에서 **열기**를 선택하고 응용 프로그램의 배포 매니페스트를 엽니다.  
  
3.  **Deployment Options** 탭을 선택합니다.  
  
4.  **시작 위치** 텍스트 상자에 응용 프로그램 업데이트를 위한 배포 매니페스트가 들어 있는 디렉터리의 URL을 입력합니다.  
  
5.  배포 매니페스트를 저장합니다.  
  
### Mage.exe를 사용하여 업데이트 대체 위치 지정  
  
1.  .NET Framework 명령 프롬프트를 엽니다.  
  
2.  다음 명령을 사용하여 업데이트 위치를 설정합니다.  이 예제에서 **HelloWorld.exe.application**은 항상 .application 확장명을 사용하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트의 경로이고, **http:\/\/adatum.com\/Update\/Path**는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 응용 프로그램 업데이트를 확인하는 URL입니다.  
  
     **Mage \-Update HelloWorld.exe.application \-ProviderUrl http:\/\/adatum.com\/Update\/Path**  
  
3.  파일을 저장합니다.  
  
    > [!NOTE]
    >  이제 Mage.exe에서 해당 파일에 다시 서명해야 합니다.  자세한 내용은 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)를 참조하십시오.  
  
## .NET Framework 보안  
 CD 같은 오프라인 미디어를 사용하여 응용 프로그램을 설치하는 경우 컴퓨터가 네트워크에 연결되어 있으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 먼저 배포 매니페스트의 `<deploymentProvider>` 태그로 지정된 URL을 검사하여 업데이트 위치에 더 최신 버전의 응용 프로그램이 있는지 확인합니다.  더 최신 버전의 응용 프로그램이 있으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 초기 설치 디렉터리 대신 이 위치에서 직접 응용 프로그램을 설치합니다. 이때 CLR\(공용 언어 런타임\)에서는 `<deploymentProvider>`를 사용하여 응용 프로그램의 신뢰 수준을 결정합니다.  컴퓨터가 네트워크에 연결되어 있지 않거나 `<deploymentProvider>`를 사용할 수 없는 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 CD를 사용하여 응용 프로그램을 설치하고 CLR에서는 설치 지점을 기준으로 신뢰 수준을 부여합니다. CD 설치의 경우 이는 응용 프로그램에 완전 신뢰가 부여됨을 의미합니다.  이후의 모든 업데이트에는 이 신뢰 수준이 상속됩니다.  
  
 `<deploymentProvider>`를 사용하는 모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에서는 응용 프로그램 매니페스트에 필요한 권한을 명시적으로 선언하여 컴퓨터가 달라도 동일한 수준의 신뢰를 부여받도록 해야 합니다.  
  
## 참고 항목  
 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)