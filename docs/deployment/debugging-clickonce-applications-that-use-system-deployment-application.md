---
title: "System.Deployment.Application을 사용하는 ClickOnce 응용 프로그램 디버깅 | Microsoft Docs"
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
  - "ClickOnce 배포, 디버깅"
  - "디버깅, ClickOnce 응용 프로그램"
  - "디버깅, System.Deployment"
  - "응용 프로그램 배포[ClickOnce], 디버깅"
ms.assetid: 86f31948-2ca8-47c0-8e8b-c2b817bbf79f
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# System.Deployment.Application을 사용하는 ClickOnce 응용 프로그램 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에서 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 사용하면 응용 프로그램의 업데이트 방법을 구성할 수 있습니다.  그러나 고급 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 기능을 사용하고 사용자 지정해야 하는 경우 <xref:System.Deployment.Application>에서 제공하는 배포 개체 모델에 액세스해야 합니다.  다음과 같은 고급 작업에는 <xref:System.Deployment.Application> API를 사용할 수 있습니다.  
  
-   응용 프로그램에서 "지금 업데이트" 옵션 만들기  
  
-   다양한 응용 프로그램 구성 요소의 조건부 요청 시 다운로드  
  
-   응용 프로그램에 직접 통합된 업데이트  
  
-   클라이언트 응용 프로그램이 항상 최신 상태를 유지하도록 보장  
  
 <xref:System.Deployment.Application> API는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 기술을 사용하여 응용 프로그램을 배포하는 경우에만 작동되므로 이를 디버깅하는 유일한 방법은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 사용하여 응용 프로그램을 배포하고 이에 연결한 다음 디버깅하는 것입니다.  이 코드는 종종 디버거를 연결할 수 있기 전에 응용 프로그램이 시작되고 실행될 때 실행되므로 디버거를 적절한 시점에 연결하는 것은 어려울 수 있습니다.  업데이트 확인 코드 또는 주문형 코드 앞에 break\(Visual Basic 프로젝트의 경우 stop\)를 삽입하면 이 문제를 해결할 수 있습니다.  
  
 권장되는 디버깅 기술은 다음과 같습니다.  
  
1.  시작하기 전에 기호\(.pdb\)와 소스 파일이 보관되어 있는지 확인합니다.  
  
2.  응용 프로그램의 버전 1을 배포합니다.  
  
3.  새 빈 솔루션을 만듭니다.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  **새 프로젝트 추가** 대화 상자에서 **기타 프로젝트 형식** 노드를 연 다음 **Visual Studio 솔루션** 폴더를 선택합니다.  **템플릿** 창에서 **빈 솔루션**을 선택합니다.  
  
4.  보관된 소스 위치를 새 솔루션의 속성에 추가합니다.  **솔루션 탐색기**에서 솔루션 노드를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  **속성 페이지** 대화 상자에서 **소스 파일 디버그**를 선택한 다음 보관된 소스 코드의 디렉터리를 추가합니다.  그렇지 않으면 소스 파일 경로가 .pdb 파일에 기록되어 있으므로 디버거가 만료된 소스 파일을 찾습니다.  디버거가 만료된 소스 파일을 사용하는 경우 소스가 일치하지 않음을 나타내는 메시지가 표시됩니다.  
  
5.  디버거가 .pdb 파일을 찾을 수 있는지 확인합니다.  응용 프로그램을 사용하여 소스 파일을 배포한 경우 디버거는 해당 파일을 자동으로 찾습니다.  디버거는 항상 문제가 있는 어셈블리를 먼저 찾습니다.  그렇지 않으면 보관 경로를 **기호 파일\(.pdb\) 위치**에 추가해야 합니다. 이 옵션에 액세스하려면 **도구** 메뉴에서 **옵션**을 클릭한 다음 **디버깅** 노드를 열고 **기호**를 클릭해야 합니다.  
  
6.  `CheckForUpdate` 메서드와 `Download`\/`Update` 메서드 호출 사이에 발생한 동작을 디버깅합니다.  
  
     예를 들어, 업데이트 코드는 다음과 같습니다.  
  
    ```  
        Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
            If My.Application.Deployment.IsNetworkDeployed Then  
  
                If (My.Application.Deployment.CheckForUpdate()) Then  
  
                    My.Application.Deployment.Update()  
                    Application.Restart()  
  
                End If  
  
            End If  
        End Sub  
    ```  
  
7.  버전 2를 배포합니다.  
  
8.  버전 2에 대한 업데이트를 다운로드할 때 디버거를 버전 1 응용 프로그램에 연결합니다.  `System.Diagnostics.Debugger.Break` 메서드를 사용하거나 단순히 Visual Basic의 `Stop`을 사용할 수도 있습니다.  물론 이러한 메서드 호출을 프로덕션 코드에 그대로 두어서는 안 됩니다.  
  
     예를 들어, Windows Forms 응용 프로그램을 개발하는 중이고 이 메서드에 대해 업데이트 논리가 있는 이벤트 처리기가 있다고 가정해 보십시오.  이 이벤트 처리기를 디버그하려면 단추를 누르기 전에 간단히 연결한 다음 중단점을 설정합니다. 중단점은 해당 보관된 파일을 열어서 설정해야 합니다.  
  
 응용 프로그램이 배포되는 경우에만 <xref:System.Deployment.Application> API를 호출하려면 <xref:System.Deployment.Application.ApplicationDeployment.IsNetworkDeployed%2A> 속성을 사용합니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 디버깅하는 동안에는 API를 호출하면 안 됩니다.  
  
## 참고 항목  
 <xref:System.Deployment.Application>