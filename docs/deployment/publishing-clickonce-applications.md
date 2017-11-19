---
title: "ClickOnce 응용 프로그램 게시 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.Options
- Microsoft.VisualStudio.Publish.ClickOnceProvider.PublishWizard.Help
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- ClickOnce applications, publishing
- applications [Visual Studio], ClickOnce deployment
- deploying applications [ClickOnce], publishing ClickOnce applications
ms.assetid: eb6dfe79-f54c-4331-8e36-073688e70973
caps.latest.revision: "22"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 35d642256a199c8ee5bf5e67a6a0bfb414b9fccc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="publishing-clickonce-applications"></a>ClickOnce 응용 프로그램 게시
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 처음으로 게시할 때는 게시 마법사를 사용하여 게시 속성을 설정할 수 있습니다. 마법사에서는 일부 속성만 사용 가능하며 기타 모든 설정은 기본값으로 설정됩니다.  
  
 게시 속성을 추가로 변경에 **게시** 페이지에 **프로젝트 디자이너**합니다.  
  
## <a name="publish-wizard"></a>게시 마법사  
 게시 마법사를 사용하여 응용 프로그램 게시를 위한 기본 설정을 지정할 수 있습니다. 여기에는 다음과 같은 게시 속성이 포함됩니다.  
  
-   게시 폴더 위치 - Visual Studio에서 파일을 복사하는 위치(로컬 컴퓨터, 네트워크 파일 공유, FTP 서버 또는 웹 사이트)  
  
-   설치 폴더 위치 - 최종 사용자가 설치하는 위치(네트워크 파일 공유, FTP 서버, 웹 사이트, CD/DVD)  
  
-   온라인 또는 오프라인 사용 가능 여부 - 최종 사용자가 네트워크에 연결하지 않고 응용 프로그램에 액세스할 수 있는지 여부  
  
-   업데이트 빈도 - 응용 프로그램에서 새 업데이트를 확인하는 빈도  
  
 자세한 내용은 [하는 방법: 게시 마법사를 사용 하 여 ClickOnce 응용 프로그램을 게시할](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
## <a name="publish-page"></a>게시 페이지  
 **프로젝트 디자이너** 의 **게시** 페이지를 통해 ClickOnce 배포를 위한 속성을 구성합니다. 다음 표에 관련 항목이 나와 있습니다.  
  
|제목|설명|  
|-----------|-----------------|  
|[방법: Visual Studio의 파일 복사 위치 지정](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)|Visual Studio에서 응용 프로그램 파일 및 매니페스트를 배치하는 위치를 설정하는 방법을 설명합니다.|  
|[방법: 최종 사용자의 설치 원본 위치 지정](../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)|사용자가 응용 프로그램을 다운로드하고 설치할 수 있는 위치를 설정하는 방법을 설명합니다.|  
|[방법: ClickOnce 오프라인 또는 온라인 설치 모드 지정](../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)|응용 프로그램을 오프라인으로 제공할지 아니면 온라인으로 제공할지를 설정하는 방법을 설명합니다.|  
|[방법: ClickOnce 게시 버전 설정](../deployment/how-to-set-the-clickonce-publish-version.md)|ClickOnce를 설정 하는 방법에 설명 **게시 버전** 속성을 게시 하는 응용 프로그램 업데이트로 간주할지 여부를 결정 합니다.|  
|[방법: ClickOnce 게시 버전 자동 증가](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)|수정 번호를 자동으로 증가 하는 방법에 설명 된 **PublishVersion** 응용 프로그램을 게시할 때마다 합니다.|  
  
 자세한 내용은 참조 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)  
  
### <a name="application-files-dialog-box"></a>응용 프로그램 파일 대화 상자  
 이 대화 상자에서는 프로젝트의 파일이 게시, 동작 다운로드 및 업데이트용으로 분류되는 방법을 지정할 수 있습니다. 이 대화 상자에 포함된 표에는 기본적으로 제외되지 않거나 다운로드 그룹이 있는 프로젝트 파일이 나열됩니다.  
  
 파일을 제외 하려면 파일을 데이터 파일 또는 필수 구성 요소를 표시할 및 Visual Studio UI에서 조건부 설치에 대 한 파일 그룹을 만들, 참조 [하는 방법: 지정는 통해 게시할 파일 ClickOnce](../deployment/how-to-specify-which-files-are-published-by-clickonce.md)합니다. Mage.exe를 사용하여 데이터 파일을 표시할 수도 있습니다. 자세한 내용은 [How to: Include a Data File in a ClickOnce Application](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)을 참조하세요.  
  
### <a name="prerequisites-dialog-box"></a>필수 조건 대화 상자  
 이 대화 상자에서는 설치되는 필수 구성 요소 및 해당 설치 방법을 지정합니다. 자세한 내용은 참조 [하는 방법: ClickOnce 응용 프로그램에 필수 구성 요소 설치](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md) 및 [필수 구성 요소 대화 상자](../ide/reference/prerequisites-dialog-box.md)합니다.  
  
### <a name="application-updates-dialog-box"></a>응용 프로그램 업데이트 대화 상자  
 이 대화 상자에서는 설치된 응용 프로그램에서 업데이트를 확인하는 방법을 지정합니다. 자세한 내용은 참조 [하는 방법: ClickOnce 응용 프로그램에 대 한 업데이트 관리](../deployment/how-to-manage-updates-for-a-clickonce-application.md)합니다.  
  
### <a name="publish-options-dialog-box"></a>게시 옵션 대화 상자  
 게시 옵션 대화 상자에서는 응용 프로그램의 배포 옵션을 지정합니다.  
  
|||  
|-|-|  
|[방법: ClickOnce 응용 프로그램의 게시 언어 변경](../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)|지역화된 버전과 일치하도록 언어 및 문화권을 지정하는 방법을 설명합니다.|  
|[방법: ClickOnce 응용 프로그램의 시작 메뉴 이름 지정](../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)|ClickOnce 응용 프로그램의 표시 이름을 변경하는 방법을 설명합니다.|  
|[방법: 기술 지원을 위한 링크 지정](../deployment/how-to-specify-a-link-for-technical-support.md)|설정 하는 방법에 설명 된 **지원 URL** 웹 페이지 또는 파일 공유 사용자가 응용 프로그램에 대 한 정보를 가져오려면 이동할 수 있는 위치를 식별 하는 속성입니다.|  
|[방법: ClickOnce 배포 시 개별 필수 구성 요소에 대한 지원 URL 지정](../deployment/how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment.md)|각 필수 구성 요소에 대한 개별 지원 URL을 포함하도록 응용 프로그램 매니페스트를 수동으로 변경하는 방법을 설명합니다.|  
|[방법: ClickOnce 응용 프로그램의 게시 페이지 지정](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)|응용 프로그램과 함께 기본 웹 페이지(publish.htm)를 생성 및 게시하는 방법을 설명합니다.|  
|[방법: ClickOnce 기본 웹 페이지 사용자 지정](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)|자동으로 생성되어 응용 프로그램과 함께 게시되는 웹 페이지를 사용자 지정하는 방법을 설명합니다.|  
|[방법: CD 설치를 위한 자동 시작 사용](../deployment/how-to-enable-autostart-for-cd-installations.md)|미디어를 삽입할 때 ClickOnce 응용 프로그램이 자동으로 시작되도록 자동 시작 기능을 사용하도록 설정하는 방법을 설명합니다.|  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[방법: ClickOnce 응용 프로그램에 대한 파일 연결 만들기](../deployment/how-to-create-file-associations-for-a-clickonce-application.md)|ClickOnce 응용 프로그램에 파일 이름 확장명 지원을 추가하는 방법을 설명합니다.|  
|[방법: 온라인 ClickOnce 응용 프로그램에서 쿼리 문자열 정보 검색](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)|ClickOnce 응용 프로그램을 실행하는 데 사용되는 URL에 전달된 매개 변수를 검색하는 방법을 보여 줍니다.|  
|[방법: 디자이너를 사용하여 ClickOnce 응용 프로그램의 URL 활성화를 사용하지 않도록 설정](../deployment/how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer.md)|응용 프로그램을 시작 하도록 하는 방법에 설명 된 **시작** 디자이너를 사용 하 여 메뉴입니다.|  
|[방법: ClickOnce 응용 프로그램의 URL 활성화를 사용하지 않도록 설정](../deployment/how-to-disable-url-activation-of-clickonce-applications.md)|응용 프로그램을 시작 하도록 하는 방법에 설명 된 **시작** 메뉴.|  
|[연습: 디자이너를 사용하여 ClickOnce 배포 API에서 요청 시 어셈블리 다운로드](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)|응용 프로그램 어셈블리를 응용 프로그램에서 처음 사용할 때만 디자이너를 사용하여 다운로드하는 방법을 설명합니다.|  
|[연습: ClickOnce 배포 API에서 요청 시 어셈블리 다운로드](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api.md)|응용 프로그램 어셈블리를 응용 프로그램에서 처음 사용할 때만 다운로드하는 방법을 설명합니다.|  
|[연습: ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)|위성 어셈블리를 선택적 항목으로 표시하고 클라이언트 컴퓨터의 현재 문화권 설정에 필요한 어셈블리만 다운로드하는 방법을 설명합니다.|  
|[연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)|.NET Framework 유틸리티를 사용하여 ClickOnce 응용 프로그램을 배포하는 방법을 설명합니다.|  
|[연습: 다시 서명할 필요가 없고 브랜드 정보가 유지되는 ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md)|.NET Framework 유틸리티를 사용하여 매니페스트를 다시 서명하지 않고 ClickOnce 응용 프로그램을 배포하는 방법을 설명합니다.|  
|[방법: 플랫폼을 대상으로 한 프로젝트 구성](../ide/how-to-configure-projects-to-target-platforms.md)|64 비트 프로세서용으로 변경 하 여 게시 하는 방법에 설명 된 **대상 CPU** 또는 **플랫폼 대상** 프로젝트 속성을 합니다.|  
|[연습: 여러.NET Framework 버전에서 실행 하는 ClickOnce 응용 프로그램을 사용 하도록 설정](http://msdn.microsoft.com/en-us/7f4383af-ed87-4853-b4d4-02a3967a5fd9)|ClickOnce 응용 프로그램을 여러 .NET Framework 버전에 설치하고 실행할 수 있도록 설정하는 방법을 설명합니다.|  
|[연습: ClickOnce 응용 프로그램용 사용자 지정 설치 관리자 만들기](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md)|ClickOnce 응용 프로그램을 설치하는 사용자 지정 설치 관리자를 만드는 방법을 설명합니다.|  
|[방법: 비주얼 스타일을 사용하여 WPF 응용 프로그램 게시](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md)|비주얼 스타일을 사용하는 WPF 응용 프로그램을 게시할 때 발생하는 오류를 해결하기 위한 단계별 지침을 제공합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce 참조](../deployment/clickonce-reference.md)