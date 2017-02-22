---
title: "방법: ClickOnce 응용 프로그램에 대한 업데이트 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.Update"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 업데이트"
  - "ClickOnce 배포, 응용 프로그램 관리"
  - "ClickOnce 배포, 업데이트"
  - "데이터 업데이트, ClickOnce"
ms.assetid: a3f23f05-e7f1-4620-b23c-2d68f9643684
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 응용 프로그램에 대한 업데이트 관리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에서는 업데이트를 자동으로 또는 프로그래밍 방식으로 확인할 수 있습니다.  개발자의 경우 업데이트를 확인하는 시기와 방법, 필수 업데이트인지 여부 및 응용 프로그램에서 업데이트를 확인하는 위치 등을 자유롭게 지정할 수 있습니다.  
  
 응용 프로그램이 시작되기 전이나 응용 프로그램이 시작된 후 설정한 간격에 따라 업데이트를 자동으로 확인하도록 응용 프로그램을 구성할 수 있습니다.  필요한 최소 버전을 지정할 수도 있습니다. 이 경우 사용자의 버전이 필요한 버전보다 낮은 경우에 업데이트가 설치됩니다.  
  
 사용자 요청과 같은 이벤트에 따라 업데이트를 프로그래밍 방식으로 확인하도록 응용 프로그램을 구성할 수 있습니다.  이 항목의 "프로그래밍 방식으로 업데이트를 확인하려면" 절차에서는 <xref:System.Deployment.Application.ApplicationDeployment> 클래스를 사용하여 이벤트에 따라 업데이트를 확인하는 코드를 작성하는 방법을 보여 줍니다.  
  
 응용 프로그램을 배포한 위치와는 다른 위치에서 응용 프로그램을 업데이트할 수도 있습니다.  자세한 내용은 "다른 업데이트 위치를 지정하려면" 절차를 참조하십시오.  
  
 자세한 내용은 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)을 참조하십시오.  
  
 업데이트 동작은 **프로젝트 디자이너**의 **게시** 페이지에서 사용할 수 있는 **응용 프로그램 업데이트** 대화 상자에서 관리합니다.  
  
### 응용 프로그램이 시작되기 전에 업데이트를 확인하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **업데이트** 단추를 클릭하여 **응용 프로그램 업데이트** 대화 상자를 엽니다.  
  
4.  **응용 프로그램 업데이트** 대화 상자에서 **응용 프로그램이 업데이트를 확인해야 함** 확인란이 선택되어 있는지 확인합니다.  
  
5.  **응용 프로그램이 언제 업데이트를 확인하는지 선택하십시오.** 섹션에서 **응용 프로그램 시작 전**을 선택합니다.  이렇게 하면 네트워크에 연결되어 있는 경우 항상 최신 업데이트로 응용 프로그램을 실행할 수 있습니다.  
  
### 응용 프로그램이 시작된 후에 백그라운드에서 업데이트를 확인하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **업데이트** 단추를 클릭하여 **응용 프로그램 업데이트** 대화 상자를 엽니다.  
  
4.  **응용 프로그램 업데이트** 대화 상자에서 **응용 프로그램이 업데이트를 확인해야 함** 확인란이 선택되어 있는지 확인합니다.  
  
5.  **응용 프로그램이 언제 업데이트를 확인하는지 선택하십시오.** 섹션에서 **응용 프로그램 시작 후**를 선택합니다.  이 방법을 사용하면 응용 프로그램이 좀 더 빨리 시작되고 백그라운드에서 업데이트가 확인되며 사용할 수 있는 업데이트가 있을 때만 사용자에게 알립니다.  업데이트를 설치해도 응용 프로그램을 다시 시작할 때까지는 적용되지 않습니다.  
  
6.  **응용 프로그램이 업데이트를 확인하는 빈도를 지정하십시오.** 구역에서 **응용 프로그램이 실행될 때마다 확인**\(기본값\) 또는 **확인 간격**을 선택하고 숫자 및 시간 간격을 입력합니다.  
  
### 응용 프로그램에 필요한 최소 버전을 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **업데이트** 단추를 클릭하여 **응용 프로그램 업데이트** 대화 상자를 엽니다.  
  
4.  **응용 프로그램 업데이트** 대화 상자에서 **응용 프로그램이 업데이트를 확인해야 함** 확인란이 선택되어 있는지 확인합니다.  
  
5.  **이 응용 프로그램에 필요한 최소 버전 지정** 확인란을 선택하고 응용 프로그램의 **주 버전**, **부 버전**, **빌드 버전** 및 **수정 버전**을 입력합니다.  
  
### 다른 업데이트 위치를 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **업데이트** 단추를 클릭하여 **응용 프로그램 업데이트** 대화 상자를 엽니다.  
  
4.  **응용 프로그램 업데이트** 대화 상자에서 **응용 프로그램이 업데이트를 확인해야 함** 확인란이 선택되어 있는지 확인합니다.  
  
5.  **업데이트 위치** 필드에서 http:\/\/Hostname\/ApplicationName 형식의 정규화된 URL을 사용하거나 \\\\Server\\ApplicationName 형식의 UNC 경로를 사용하여 업데이트 위치를 입력하거나 **찾아보기** 단추를 클릭하여 업데이트 위치를 찾습니다.  
  
### 프로그래밍 방식으로 업데이트를 확인하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **업데이트** 단추를 클릭하여 **응용 프로그램 업데이트** 대화 상자를 엽니다.  
  
4.  **응용 프로그램 업데이트** 대화 상자에서 **응용 프로그램이 업데이트를 확인해야 함** 확인란의 선택이 취소되어 있는지 확인합니다.  필요한 경우 이 확인란을 선택하여 업데이트를 프로그래밍 방식으로 확인할 수 있으며 ClickOnce 런타임에서 업데이트를 자동으로 확인하도록 할 수도 있습니다.  
  
5.  **업데이트 위치** 필드에서 http:\/\/Hostname\/ApplicationName 형식의 정규화된 URL을 사용하거나 \\\\Server\\ApplicationName 형식의 UNC 경로를 사용하여 업데이트 위치를 입력하거나 **찾아보기** 단추를 클릭하여 업데이트 위치를 찾습니다.  업데이트 위치는 응용 프로그램에서 업데이트된 버전을 찾는 위치입니다.  
  
6.  Windows Form에서 사용자가 업데이트를 확인하기 위해 선택할 수 있는 단추, 메뉴 항목 또는 기타 사용자 인터페이스 항목을 만듭니다.  해당 항목의 이벤트 처리기에서 메서드를 호출하여 업데이트를 확인하고 설치할 수 있습니다.  이러한 메서드에 대한 Visual Basic 및 Visual C\# 코드 예제는 [방법: ClickOnce 배포 API를 사용하여 프로그래밍 방식으로 응용 프로그램 업데이트 확인](../deployment/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api.md)을 참조하십시오.  
  
7.  응용 프로그램을 빌드합니다.  
  
## 참고 항목  
 <xref:System.Deployment.Application.ApplicationDeployment>   
 [Application Updates Dialog Box](http://msdn.microsoft.com/ko-kr/8eca8743-8e68-4d04-bfd5-4dc0a9b2934f)   
 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [방법: ClickOnce 배포 API를 사용하여 프로그래밍 방식으로 응용 프로그램 업데이트 확인](../deployment/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api.md)