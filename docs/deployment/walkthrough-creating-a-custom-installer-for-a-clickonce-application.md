---
title: '연습: ClickOnce 응용 프로그램에 대 한 사용자 지정 설치 관리자 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, custom installer
- installer [ClickOnce], custom
- deploying applications [ClickOnce], custom installer
- InPlaceHostingManager [ClickOnce], custom installer
- custom installer [ClickOnce]
ms.assetid: fb222cc5-8aeb-4b94-8c49-b93e342f5f69
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 585a33a8a3c49792be0cc986b36636e7107290ac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-a-custom-installer-for-a-clickonce-application"></a>연습: ClickOnce 응용 프로그램용 사용자 지정 설치 관리자 만들기
ClickOnce 응용 프로그램은.exe 파일에 따라 자동으로 설치 및 사용자 지정 설치 관리자에 의해 업데이트 수입니다. 사용자 지정 설치 관리자는 보안 및 유지 관리 작업에 대 한 사용자 지정 대화 상자를 포함 하 여 설치 하는 동안 사용자 지정 고객 환경을 구현할 수 있습니다. 사용자 지정 설치 관리자 설치 작업을 수행 하려면 사용 하 여는 <xref:System.Deployment.Application.InPlaceHostingManager> 클래스입니다. 이 연습에는 ClickOnce 응용 프로그램을 설치 하는 사용자 지정 설치 관리자를 만드는 방법을 보여 줍니다.  
  
## <a name="prerequisites"></a>필수 조건  
  
### <a name="to-create-a-custom-clickonce-application-installer"></a>사용자 지정 ClickOnce 응용 프로그램 설치 관리자를 만들려면  
  
1.  ClickOnce 응용 프로그램에서 System.Deployment 및 System.Windows.Forms에 대 한 참조를 추가 합니다.  
  
2.  응용 프로그램에 새 클래스를 추가 하 고 임의의 이름을 지정 합니다. 이 연습에서는 이름 `MyInstaller`합니다.  
  
3.  다음 추가 `Imports` 또는 `using` 문을 새 클래스의 맨 위에 있습니다.  
  
    ```vb  
    Imports System.Deployment.Application  
    Imports System.Windows.Forms  
    ```  
  
    ```csharp  
    using System.Deployment.Application;  
    using System.Windows.Forms;  
    ```  
  
4.  클래스에 다음 메서드를 추가 합니다.  
  
     이러한 메서드는 호출 <xref:System.Deployment.Application.InPlaceHostingManager> 배포 매니페스트를 다운로드 하는 메서드를 설치 하 고 다운로드 한 다음 ClickOnce 캐시에 응용 프로그램을 설치 하는 권한에 대 한 사용자에 게 적절 한 권한을 어설션 합니다. 사용자 지정 설치 관리자 미리 신뢰할 수 또는 ClickOnce 응용 프로그램 신뢰 결정을 내리도록을 연기할 수를 지정할 수는 <xref:System.Deployment.Application.InPlaceHostingManager.AssertApplicationRequirements%2A> 메서드를 호출 합니다. 이 코드는 응용 프로그램을 미리 신뢰 합니다.  
  
    > [!NOTE]
    >  미리를 신뢰 하 여 할당 된 사용 권한 사용자 지정 설치 관리자 코드의 사용 권한을 초과할 수 없습니다.  
  
     [!code-vb[System.Deployment.Application.InPlaceHostingManager#1](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-installer-for-a-clickonce-application_1.vb)]
     [!code-csharp[System.Deployment.Application.InPlaceHostingManager#1](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-installer-for-a-clickonce-application_1.cs)]  
  
5.  호출 코드에서 설치를 시도 하는 `InstallApplication` 메서드. 예를 들어, 클래스의 이름을 `MyInstaller`를 호출할 수 있는 `InstallApplication` 다음과 같은 방식으로 합니다.  
  
    ```vb  
    Dim installer As New MyInstaller()  
    installer.InstallApplication("\\myServer\myShare\myApp.application")  
    MessageBox.Show("Installer object created.")  
    ```  
  
    ```csharp  
    MyInstaller installer = new MyInstaller();  
    installer.InstallApplication(@"\\myServer\myShare\myApp.application");  
    MessageBox.Show("Installer object created.");  
    ```  
  
## <a name="next-steps"></a>다음 단계  
 ClickOnce 응용 프로그램 업데이트 과정에서 표시 하기 위한 사용자 지정 사용자 인터페이스를 포함 하 여 사용자 지정 업데이트 논리를 추가할 수도 있습니다. 자세한 내용은 <xref:System.Deployment.Application.UpdateCheckInfo>을 참조하세요. ClickOnce 응용 프로그램 에서도 표시 하지 않을 수 시작 메뉴 항목, 바로 가기를 마우스 항목 프로그램 추가 / 제거를 사용 하 여 한 `<customUX>` 요소입니다. 자세한 내용은 참조 [ \<entryPoint > 요소](../deployment/entrypoint-element-clickonce-application.md) 및 <xref:System.Deployment.Application.DownloadApplicationCompletedEventArgs.ShortcutAppId%2A>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)   
 [\<entryPoint > 요소](../deployment/entrypoint-element-clickonce-application.md)