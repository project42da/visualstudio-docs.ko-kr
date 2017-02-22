---
title: "방법: 응용 프로그램 및 배포 매니페스트에 다시 서명 | Microsoft Docs"
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
  - "ClickOnce 배포, 매니페스트 서명"
  - "응용 프로그램 배포[ClickOnce], 매니페스트 서명"
  - "응용 프로그램 배포, 매니페스트 서명"
  - "Office 응용 프로그램, 매니페스트 서명"
  - "Visual Studio에서 Office 개발, 매니페스트 서명"
ms.assetid: d53bceb9-4d3b-4c22-b909-8f370e7231fb
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: 응용 프로그램 및 배포 매니페스트에 다시 서명
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Windows Forms 응용 프로그램, Windows Presentation Foundation 응용 프로그램\(xbap\) 또는 Office 솔루션의 응용 프로그램 매니페스트에서 배포 속성을 변경한 후에는 인증서로 응용 프로그램 및 배포 매니페스트 둘 다에 다시 서명해야 합니다.  이렇게 하면 변조된 파일이 최종 사용자 컴퓨터에 설치되지 않도록 하는 데 도움이 됩니다.  
  
 매니페스트에 다시 서명하는 또 다른 시나리오는 고객이 자신의 인증서로 응용 프로그램 및 배포 매니페스트에 서명하기를 원하는 경우입니다.  
  
## 응용 프로그램 및 배포 매니페스트 다시 서명  
 이 절차에서는 응용 프로그램 매니페스트 파일\(.manifest\)을 이미 변경했다고 가정합니다.  자세한 내용은 [방법: 배포 속성 변경](http://msdn.microsoft.com/ko-kr/66052a3a-8127-4964-8147-2477ef5d1472)을 참조하십시오.  
  
#### Mage.exe로 응용 프로그램 및 배포 매니페스트에 다시 서명하려면  
  
1.  **Visual Studio 명령 프롬프트** 창을 엽니다.  
  
2.  서명할 매니페스트 파일이 들어 있는 폴더로 디렉터리를 변경합니다.  
  
3.  다음 명령을 입력하여 응용 프로그램 매니페스트 파일에 서명합니다.  ManifestFileName은 매니페스트 파일의 이름과 확장명으로 바꿉니다.  Certificate는 인증서 파일의 상대 경로나 정규화된 경로로 바꾸고 Password는 인증서의 암호로 바꿉니다.  
  
    ```  
    mage -sign ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     예를 들어, 다음 명령을 실행하여 추가 기능, Windows Form 응용 프로그램 또는 Windows Presentation Foundation 브라우저 응용 프로그램의 응용 프로그램 매니페스트에 서명할 수 있습니다.  Visual Studio에서 만들어진 임시 인증서는 프로덕션 환경에 배포하는 데 사용하지 않는 것이 좋습니다.  
  
    ```  
    mage -sign WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -sign ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -sign WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
4.  다음 명령을 입력하여 배포 매니페스트 파일을 업데이트하고 이에 서명합니다. 자리 표시자 이름은 이전 단계에서와 같이 바꿉니다.  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     예를 들어, 다음 명령을 실행하여 Excel 추가 기능, Windows Forms 응용 프로그램 또는 Windows Presentation Foundation 브라우저 응용 프로그램의 배포 매니페스트에 서명할 수 있습니다.  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5.  필요한 경우 마스터 배포 매니페스트\(publish\\*appname*.application\)를 버전 배포 디렉터리\(publish\\Application Files\\*appname*\_*version*\)로 복사합니다.  
  
## 응용 프로그램 및 배포 매니페스트 업데이트 및 다시 서명  
 이 절차에서는 응용 프로그램 매니페스트 파일\(.manifest\)을 이미 변경했지만 다른 파일이 업데이트된 경우를 가정합니다.  파일이 업데이트되면 해당 파일을 나타내는 해시 역시 업데이트되어야 합니다.  
  
#### Mage.exe로 응용 프로그램 및 배포 매니페스트를 업데이트하고 다시 서명하려면  
  
1.  **Visual Studio 명령 프롬프트** 창을 엽니다.  
  
2.  서명할 매니페스트 파일이 들어 있는 폴더로 디렉터리를 변경합니다.  
  
3.  게시 출력 폴더에 있는 파일에서 .deploy 파일 확장명을 제거합니다.  
  
4.  다음 명령을 입력하여 업데이트된 파일의 새 해시로 응용 프로그램 매니페스트를 업데이트하고 응용 프로그램 매니페스트 파일에 서명합니다.  ManifestFileName은 매니페스트 파일의 이름과 확장명으로 바꿉니다.  Certificate는 인증서 파일의 상대 경로나 정규화된 경로로 바꾸고 Password는 인증서의 암호로 바꿉니다.  
  
    ```  
    mage -update ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     예를 들어, 다음 명령을 실행하여 추가 기능, Windows Form 응용 프로그램 또는 Windows Presentation Foundation 브라우저 응용 프로그램의 응용 프로그램 매니페스트에 서명할 수 있습니다.  Visual Studio에서 만들어진 임시 인증서는 프로덕션 환경에 배포하는 데 사용하지 않는 것이 좋습니다.  
  
    ```  
    mage -update WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5.  다음 명령을 입력하여 배포 매니페스트 파일을 업데이트하고 이에 서명합니다. 자리 표시자 이름은 이전 단계에서와 같이 바꿉니다.  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     예를 들어, 다음 명령을 실행하여 Excel 추가 기능, Windows Forms 응용 프로그램 또는 Windows Presentation Foundation 브라우저 응용 프로그램의 배포 매니페스트에 서명할 수 있습니다.  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
6.  응용 프로그램 및 배포 매니페스트 파일을 제외한 나머지 파일에 다시 .deploy 파일 확장명을 추가합니다.  
  
7.  필요한 경우 마스터 배포 매니페스트\(publish\\*appname*.application\)를 버전 배포 디렉터리\(publish\\Application Files\\*appname*\_*version*\)로 복사합니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce 응용 프로그램의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce 및 Authenticode](../deployment/clickonce-and-authenticode.md)   
 [신뢰할 수 있는 응용 프로그램 배포 개요](../deployment/trusted-application-deployment-overview.md)   
 [방법: ClickOnce 보안 설정 사용](../deployment/how-to-enable-clickonce-security-settings.md)   
 [방법: ClickOnce 응용 프로그램의 보안 영역 설정](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [방법: ClickOnce 응용 프로그램에 대한 사용자 지정 권한 설정](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [방법: 제한된 권한으로 ClickOnce 응용 프로그램 디버깅](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [방법: ClickOnce 응용 프로그램의 클라이언트 컴퓨터에 신뢰할 수 있는 게시자 추가](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [방법: ClickOnce 신뢰 프롬프트 동작 구성](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)