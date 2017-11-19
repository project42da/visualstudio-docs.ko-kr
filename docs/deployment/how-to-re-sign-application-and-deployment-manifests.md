---
title: "방법: 응용 프로그램 및 배포 매니페스트에 다시 서명 | Microsoft Docs"
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
- Office applications, signing manifests
- deploying applications [ClickOnce], signing manifests
- deploying applications, signing manifests
- ClickOnce deployment, signing manifests
- Office development in Visual Studio, signing manifests
ms.assetid: d53bceb9-4d3b-4c22-b909-8f370e7231fb
caps.latest.revision: "17"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: baa3e9310946482a4c7c64fdb619ce612a21dbda
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-re-sign-application-and-deployment-manifests"></a>방법: 응용 프로그램 및 배포 매니페스트에 다시 서명
Windows Forms 응용 프로그램, Windows Presentation Foundation 응용 프로그램 (xbap) 또는 Office 솔루션에 대 한 응용 프로그램 매니페스트의 배포 속성을 변경한 후 응용 프로그램을 다시 서명 해야 사용 및 배포 매니페스트에 인증서입니다. 이 프로세스는 변조 된 파일은 최종 사용자 컴퓨터에 설치 되지 않았는지 확인 하는 데 도움이 됩니다.  
  
 다른 시나리오 매니페스트에 다시 서명할 수는 있는 고객에 게 응용 프로그램에 서명 하 고 자신의 인증서로 배포 매니페스트 하는 경우입니다.  
  
## <a name="re-signing-the-application-and-deployment-manifests"></a>매니페스트는 응용 프로그램 및 배포에 다시 서명  
 이 절차에서는 응용 프로그램 매니페스트 파일 (.manifest)에 이미 변경 했다고 가정 합니다. 자세한 내용은 참조 [하는 방법: 배포 속성 변경을](http://msdn.microsoft.com/en-us/66052a3a-8127-4964-8147-2477ef5d1472)합니다.  
  
#### <a name="to-re-sign-the-application-and-deployment-manifests-with-mageexe"></a>Mage.exe로 매니페스트에 응용 프로그램 및 배포를 다시 서명 하려면  
  
1.  열기는 **Visual Studio 명령 프롬프트** 창.  
  
2.  로그인 할 때 매니페스트 파일이 있는 폴더로 디렉터리를 변경 합니다.  
  
3.  응용 프로그램 매니페스트 파일에 서명 하려면 다음 명령을 입력 합니다. ManifestFileName를 확장 매니페스트 파일의 이름과 바꿉니다. 인증서를 인증서 파일의 상대 또는 정규화 된 경로 바꾸고 암호는 인증서에 대 한 암호를 사용 합니다.  
  
    ```  
    mage -sign ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     예를 들어 추가 기능, Windows Form 응용 프로그램, 또는 Windows Presentation Foundation 브라우저 응용 프로그램에 대 한 응용 프로그램 매니페스트를 서명 하려면 다음 명령을 실행할 수 있습니다. Visual Studio에서 만든 임시 인증서를 프로덕션 환경으로 배포에 대 한 권장 되지 않습니다.  
  
    ```  
    mage -sign WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -sign ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -sign WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
4.  업데이트 하 고 이전 단계에서 설명한 대로 자리 표시자 이름을 대체 배포 매니페스트 파일을 서명 하려면 다음 명령을 입력 합니다.  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     예를 들어 업데이트 하 고는 Excel 추가 기능으로, Windows Forms 응용 프로그램 또는 Windows Presentation Foundation 브라우저 응용 프로그램에 대 한 배포 매니페스트를 서명 하려면 다음 명령을 실행할 수 있습니다.  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5.  필요한 복사 하 여 마스터 배포 매니페스트 (게시\\*appname*.application) 버전 배포 디렉터리 (publish\Application 파일\\*appname*_ *버전*).  
  
## <a name="updating-and-re-signing-the-application-and-deployment-manifests"></a>업데이트 및 응용 프로그램 및 배포 매니페스트에 다시 서명  
 이 절차에서는 매니페스트 파일 (.manifest) 응용 프로그램에 변경 내용을 이미 이지만 업데이트 된 파일도 가정 합니다. 파일을 업데이트할 때 파일을 나타내는 해시도 업데이트 해야 합니다.  
  
#### <a name="to-update-and-re-sign-the-application-and-deployment-manifests-with-mageexe"></a>Mage.exe로 매니페스트를 업데이트 하 고 응용 프로그램 및 배포를 다시 서명  
  
1.  열기는 **Visual Studio 명령 프롬프트** 창.  
  
2.  로그인 할 때 매니페스트 파일이 있는 폴더로 디렉터리를 변경 합니다.  
  
3.  게시 출력 폴더에 있는 파일에서.deploy 파일 확장명을 제거 합니다.  
  
4.  업데이트 된 파일에 대 한 새 해시와 함께 응용 프로그램 매니페스트를 업데이트 하 고 응용 프로그램 매니페스트 파일을 서명 하려면 다음 명령을 입력 합니다. ManifestFileName를 확장 매니페스트 파일의 이름과 바꿉니다. 인증서를 인증서 파일의 상대 또는 정규화 된 경로 바꾸고 암호는 인증서에 대 한 암호를 사용 합니다.  
  
    ```  
    mage -update ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     예를 들어 추가 기능, Windows Form 응용 프로그램, 또는 Windows Presentation Foundation 브라우저 응용 프로그램에 대 한 응용 프로그램 매니페스트를 서명 하려면 다음 명령을 실행할 수 있습니다. Visual Studio에서 만든 임시 인증서를 프로덕션 환경으로 배포에 대 한 권장 되지 않습니다.  
  
    ```  
    mage -update WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5.  업데이트 하 고 이전 단계에서 설명한 대로 자리 표시자 이름을 대체 배포 매니페스트 파일을 서명 하려면 다음 명령을 입력 합니다.  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     예를 들어 업데이트 하 고는 Excel 추가 기능으로, Windows Forms 응용 프로그램 또는 Windows Presentation Foundation 브라우저 응용 프로그램에 대 한 배포 매니페스트를 서명 하려면 다음 명령을 실행할 수 있습니다.  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
6.  응용 프로그램 및 배포 매니페스트 파일 제외 하 고.deploy 파일 확장명을 파일에 다시 추가 합니다.  
  
7.  필요한 복사 하 여 마스터 배포 매니페스트 (게시\\*appname*.application) 버전 배포 디렉터리 (publish\Application 파일\\*appname*_ *버전*).  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce 응용 프로그램에 대 한 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce 및 Authenticode](../deployment/clickonce-and-authenticode.md)   
 [신뢰할 수 있는 응용 프로그램 배포 개요](../deployment/trusted-application-deployment-overview.md)   
 [방법: ClickOnce 보안 설정 사용](../deployment/how-to-enable-clickonce-security-settings.md)   
 [방법: ClickOnce 응용 프로그램에 대 한 보안 영역 설정](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [How to: Set Custom Permissions for a ClickOnce Application](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [방법: 제한 된 권한으로 ClickOnce 응용 프로그램 디버깅](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [방법: ClickOnce 응용 프로그램에 대 한 클라이언트 컴퓨터에 신뢰할 수 있는 게시자 추가](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [방법: ClickOnce 신뢰 프롬프트 동작 구성](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)