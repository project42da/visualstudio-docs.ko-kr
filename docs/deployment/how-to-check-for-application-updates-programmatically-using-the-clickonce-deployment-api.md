---
title: "방법: ClickOnce 배포 API를 사용하여 프로그래밍 방식으로 응용 프로그램 업데이트 확인 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "응용 프로그램 업데이트"
  - "ClickOnce 배포, 업데이트"
ms.assetid: 1a886310-67c8-44e5-a382-c2f0454f887d
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 배포 API를 사용하여 프로그래밍 방식으로 응용 프로그램 업데이트 확인
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ClickOnce에서는 응용 프로그램이 배포된 후 두 가지 방법으로 업데이트할 수 있습니다.  첫 번째 방법은 ClickOnce 배포를 구성하여 특정 간격에 따라 업데이트를 자동으로 확인하는 것입니다.  두 번째 방법은 <xref:System.Deployment.Application.ApplicationDeployment> 클래스를 사용하는 코드를 작성하여 사용자 요청과 같은 이벤트를 기반으로 업데이트를 확인하는 것입니다.  
  
 다음 절차에서는 프로그래밍 방식의 업데이트를 수행하기 위한 일부 코드를 보여 주고 프로그래밍 방식의 업데이트 확인을 사용할 수 있도록 ClickOnce 배포를 구성하는 방법도 설명합니다.  
  
 ClickOnce 응용 프로그램을 프로그래밍 방식으로 업데이트하려면 업데이트 위치를 지정해야 합니다.  이를 배포 공급자라고 합니다.  이 속성 설정에 대한 자세한 내용은 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)을 참조하십시오.  
  
> [!NOTE]
>  아래에 설명된 방법을 사용하여 응용 프로그램을 배포한 위치와는 다른 위치에서 응용 프로그램을 업데이트할 수도 있습니다.  자세한 내용은 [방법: 배포 업데이트를 위한 대체 위치 지정](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md)을 참조하십시오.  
  
### 프로그래밍 방식으로 업데이트를 확인하려면  
  
1.  기본 명령줄 또는 비주얼 도구를 사용하여 새 Windows Forms 응용 프로그램을 만듭니다.  
  
2.  사용자가 업데이트를 확인하기 위해 선택할 수 있는 단추, 메뉴 항목 또는 기타 사용자 인터페이스 항목을 만듭니다.  해당 항목의 이벤트 처리기에서 다음 메서드를 호출하여 업데이트를 확인하고 설치할 수 있습니다.  
  
     [!code-cs[ClickOnceAPI#6](../deployment/codesnippet/CSharp/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.cs)]
     [!code-cpp[ClickOnceAPI#6](../deployment/codesnippet/CPP/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.cpp)]
     [!code-vb[ClickOnceAPI#6](../deployment/codesnippet/VisualBasic/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.vb)]  
  
3.  응용 프로그램을 컴파일합니다.  
  
### Mage.exe를 사용하여 프로그래밍 방식으로 업데이트를 확인하는 응용 프로그램을 배포합니다.  
  
-   [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)에 설명된 대로 Mage.exe를 사용하여 응용 프로그램을 배포하는 지침을 따릅니다.  Mage.exe를 호출하여 배포 매니페스트를 생성할 경우에는 명령줄 스위치 `providerUrl`을 사용하고 ClickOnce에서 업데이트를 확인할 위치의 URL을 지정해야 합니다.  예를 들어, 응용 프로그램이 [http:\/\/www.microsoft.com\/ko\/kr\/default.aspx](http://www.microsoft.com/ko/kr/default.aspx)에서 업데이트되는 경우 다음을 호출하여 배포 매니페스트를 생성합니다.  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "My App 1.0" -Version 1.0.0.0 -AppManifest 1.0.0.0\MyApp.manifest -providerUrl http://www.adatum.com/MyApp/MyApp.application  
    ```  
  
### MageUI.exe를 사용하여 프로그래밍 방식으로 업데이트를 확인하는 응용 프로그램을 배포합니다.  
  
-   [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)에 설명된 대로 Mage.exe를 사용하여 응용 프로그램을 배포하는 지침을 따릅니다.  **배포 옵션** 탭에서 **시작 위치** 필드를 ClickOnce에서 업데이트를 검사할 응용 프로그램 매니페스트로 설정합니다.  **업데이트 옵션** 탭에서 **이 응용 프로그램의 업데이트 확인** 확인란의 선택을 취소합니다.  
  
## .NET Framework 보안  
 프로그래밍 방식의 업데이트를 사용하려면 응용 프로그램에 완전 신뢰 권한이 있어야 합니다.  
  
## 참고 항목  
 [방법: 배포 업데이트를 위한 대체 위치 지정](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md)   
 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)