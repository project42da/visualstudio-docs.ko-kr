---
title: "연습: ClickOnce 응용 프로그램용 사용자 지정 설치 관리자 만들기 | Microsoft Docs"
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
  - "ClickOnce 배포, 사용자 지정 설치 관리자"
  - "사용자 지정 설치 관리자[ClickOnce]"
  - "응용 프로그램 배포[ClickOnce], 사용자 지정 설치 관리자"
  - "InPlaceHostingManager[ClickOnce], 사용자 지정 설치 관리자"
  - "설치 관리자[ClickOnce], 사용자 지정"
ms.assetid: fb222cc5-8aeb-4b94-8c49-b93e342f5f69
caps.latest.revision: 34
caps.handback.revision: 34
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연습: ClickOnce 응용 프로그램용 사용자 지정 설치 관리자 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

.exe 파일을 기반으로 하는 모든 ClickOnce 응용 프로그램은 사용자 지정 설치 관리자를 통해 자동으로 설치되고 업데이트될 수 있습니다.  사용자 지정 설치 관리자는 설치 중에 보안 및 유지 관리 작업을 위한 사용자 지정 대화 상자를 비롯하여 사용자 지정 사용자 환경을 구현할 수 있습니다.  사용자 지정 설치 관리자는 <xref:System.Deployment.Application.InPlaceHostingManager> 클래스를 사용하여 설치 작업을 수행합니다.  이 연습에서는 ClickOnce 응용 프로그램을 자동으로 설치하는 사용자 지정 설치 관리자를 만드는 방법을 보여 줍니다.  
  
## 사전 요구 사항  
  
### 사용자 지정 ClickOnce 응용 프로그램 설치 관리자를 만들려면  
  
1.  ClickOnce 응용 프로그램에서 System.Deployment 및 System.Windows.Forms에 대한 참조를 추가합니다.  
  
2.  응용 프로그램에 새 클래스를 추가하고 임의의 이름을 지정합니다.  이 연습에서는 이름으로 `MyInstaller`를 사용합니다.  
  
3.  새 클래스의 맨 위에 다음 `Imports` 또는 `using` 문을 추가합니다.  
  
    ```vb#  
    Imports System.Deployment.Application  
    Imports System.Windows.Forms  
    ```  
  
    ```c#  
    using System.Deployment.Application;  
    using System.Windows.Forms;  
    ```  
  
4.  클래스에 다음 메서드를 추가합니다.  
  
     이러한 메서드는 <xref:System.Deployment.Application.InPlaceHostingManager> 메서드를 호출하여 배포 매니페스트를 다운로드하고, 적절한 사용 권한을 어설션하고, 사용자에게 설치 권한을 요청하고, ClickOnce 캐시에 응용 프로그램을 다운로드하여 설치합니다.  사용자 지정 설치 관리자는 ClickOnce 응용 프로그램이 사전 신뢰되도록 지정하거나 <xref:System.Deployment.Application.InPlaceHostingManager.AssertApplicationRequirements%2A> 메서드가 호출될 때까지 신뢰 결정을 미룰 수 있습니다.  이 코드는 응용 프로그램을 사전 신뢰합니다.  
  
    > [!NOTE]
    >  사전 신뢰를 통해 지정되는 사용 권한은 사용자 지정 설치 관리자 코드의 사용 권한보다 높을 수 없습니다.  
  
     [!code-vb[System.Deployment.Application.InPlaceHostingManager#1](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-installer-for-a-clickonce-application_1.vb)]
     [!code-cs[System.Deployment.Application.InPlaceHostingManager#1](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-installer-for-a-clickonce-application_1.cs)]  
  
5.  코드에서 설치를 시도하려면 `InstallApplication` 메서드를 호출합니다.  예를 들어 클래스의 이름을 `MyInstaller`로 지정한 경우 다음과 같은 방식으로 `InstallApplication`을 호출할 수 있습니다.  
  
    ```vb#  
    Dim installer As New MyInstaller()  
    installer.InstallApplication("\\myServer\myShare\myApp.application")  
    MessageBox.Show("Installer object created.")  
    ```  
  
    ```c#  
    MyInstaller installer = new MyInstaller();  
    installer.InstallApplication(@"\\myServer\myShare\myApp.application");  
    MessageBox.Show("Installer object created.");  
  
    ```  
  
## 다음 단계  
 또한 ClickOnce 응용 프로그램은 업데이트 중에 표시할 사용자 지정 사용자 인터페이스를 비롯하여 사용자 지정 업데이트 논리를 추가할 수도 있습니다.  자세한 내용은 <xref:System.Deployment.Application.UpdateCheckInfo>를 참조하십시오.  또한 ClickOnce 응용 프로그램은 `<customUX>` 요소를 사용하여 시작 메뉴 항목, 바로 가기 및 프로그램 추가\/제거 항목을 표시하지 않을 수도 있습니다.  자세한 내용은 [\<entryPoint\> 요소](../deployment/entrypoint-element-clickonce-application.md) 및 <xref:System.Deployment.Application.DownloadApplicationCompletedEventArgs.ShortcutAppId%2A>를 참조하십시오.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)   
 [\<entryPoint\> 요소](../deployment/entrypoint-element-clickonce-application.md)