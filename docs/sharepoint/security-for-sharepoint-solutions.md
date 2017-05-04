---
title: "SharePoint 솔루션 보안 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "보안[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 보안"
ms.assetid: 5ab33141-ba82-4960-8b29-3c907127fea6
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# SharePoint 솔루션 보안
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에는 SharePoint 응용 프로그램의 보안을 강화하기 위해 다음 기능이 통합되어 있습니다.  
  
## 안전 컨트롤 항목  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 만들어진 모든 SharePoint 프로젝트 항목에는 안전 컨트롤 컬렉션을 나타내는 **안전 컨트롤 항목** 속성이 있습니다.  이 속성의 **안전** 하위 속성을 사용하여 안전하다고 간주하는 컨트롤을 지정할 수 있습니다.  자세한 내용은 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) 및 [안전 웹 파트 지정](http://go.microsoft.com/fwlink/?LinkId=177521) 을 참조하십시오.  
  
## AllowPartiallyTrustedCallers 특성  
 기본적으로 런타임 CAS\(코드 액세스 보안\) 시스템에서 완전히 신뢰할 수 있는 응용 프로그램만 공유 관리 코드 어셈블리에 액세스할 수 있습니다.  완전히 신뢰할 수 있는 어셈블리를 AllowPartiallyTrustedCallers 특성으로 표시하면 부분적으로 신뢰할 수 있는 어셈블리가 이 어셈블리에 액세스할 수 있습니다.  
  
 AllowPartiallyTrustedCallers 특성은 시스템 [!INCLUDE[TLA2#tla_gac](../sharepoint/includes/tla2sharptla-gac-md.md)]\(전역 어셈블리 캐시\)에 배포되지 않은 모든 SharePoint 솔루션에 추가됩니다.  여기에는 샌드박스 솔루션이나 SharePoint 응용 프로그램 Bin 디렉터리에 배포된 솔루션이 포함됩니다.  자세한 내용은 [Microsoft.NET Framework의 버전 1 보안 변경](http://go.microsoft.com/fwlink/?LinkId=177515) 및 [SharePoint 기반 웹 파트 배포](http://go.microsoft.com/fwlink/?LinkId=177509) 를 참조하십시오.  
  
## 스크립트에 대해 안전 속성  
 *스크립트 삽입*은 잠재적인 악성 코드가 컨트롤이나 웹 페이지에 삽입되는 것입니다.  스크립트 삽입으로부터 SharePoint 2010 사이트를 보호하기 위해 참가자는 기본적으로 웹 파트나 해당 속성을 보거나 편집할 수 없습니다.  이 동작은 SafeAgainstScript라는 SafeControl 특성으로 제어됩니다.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 프로젝트 항목의 **안전 컨트롤 항목** 하위 속성에 있는 이 특성을 **스크립트에 대해 안전**으로 설정합니다.  자세한 내용은 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) 및 [방법: 컨트롤을 안전 컨트롤로 표시](../sharepoint/how-to-mark-controls-as-safe-controls.md)를 참조하십시오.  
  
## Vista 및 Windows 7 사용자 계정 컨트롤  
 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] 및 [!INCLUDE[win7](../sharepoint/includes/win7-md.md)]에는 UAC\(사용자 계정 컨트롤\)라는 보안 기능이 통합되어 있습니다.  [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] 및 [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 시스템의 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 솔루션을 개발하려면 UAC에서 시스템 관리자로 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 실행하도록 요구합니다.  **시작** 메뉴에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에 대한 바로 가기 메뉴를 연 다음 **관리자로 실행** 을 선택합니다.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 바로 가기를 설정하여 항상 관리자로 실행하려면, 바로 가기 메뉴를 열고, **속성** 을 선택하고, **속성** 대화 상자에서 **고급** 버튼을 선택한 다음, **관리자 권한으로 실행** 확인란을 선택합니다.  
  
 자세한 내용은 [Windows Vista의 사용자 계정 컨트롤 이해 및 구성](http://go.microsoft.com/fwlink/?LinkID=156476) 및 [Windows 7 사용자 계정 컨트롤](http://go.microsoft.com/fwlink/?LinkId=177523) 을 참조하십시오.  
  
## SharePoint 사용 권한 고려 사항  
 SharePoint 솔루션을 개발하려면 SharePoint 솔루션을 실행 및 디버깅할 수 있는 권한이 있어야 합니다.  SharePoint 솔루션을 테스트하기 전에 먼저 다음 단계를 수행하여 필요한 권한이 있는지 확인합니다.  
  
1.  시스템의 관리자로 사용자 계정을 추가합니다.  
  
2.  SharePoint 서버의 팜 관리자로 사용자 계정을 추가합니다.  
  
    1.  SharePoint 2010 중앙 관리에서 **팜 관리자 그룹 관리** 링크를 클릭합니다.  
  
    2.  **팜 관리자** 페이지에서 **New** 메뉴 옵션을 선택합니다.  
  
3.  WSS\_ADMIN\_WPG 그룹에 사용자 계정을 추가합니다.  
  
## 추가 보안 리소스  
 보안 문제에 대한 자세한 내용은 다음을 참조하십시오.  
  
### Visual Studio 보안  
  
-   [보안과 사용자 권한](http://go.microsoft.com/fwlink/?LinkId=177503)  
  
-   [네이티브 및 .NET Framework 코드의 보안](http://go.microsoft.com/fwlink/?LinkId=177504)  
  
-   [.NET Framework의 보안](http://go.microsoft.com/fwlink/?LinkId=177502)  
  
### SharePoint 보안  
  
-   [SharePoint Foundation 관리 및 보안](http://go.microsoft.com/fwlink/?LinkId=177501)  
  
-   [SharePoint 보안 리소스 센터](http://go.microsoft.com/fwlink/?LinkId=177498)  
  
-   [SharePoint 기초에서 웹 파트 보안](http://go.microsoft.com/fwlink/?LinkId=177511)  
  
-   [웹 응용 프로그램 보안 개선: 위협 및 대책](http://go.microsoft.com/fwlink/?LinkID=140080)  
  
### 일반 보안  
  
-   [MSDN Security Development Lifecycle](http://go.microsoft.com/fwlink/?LinkID=147149)  
  
-   [보안된 ASP.NET 응용 프로그램 빌드: 인증, 권한 부여 및 보안 통신](http://go.microsoft.com/fwlink/?LinkId=177494)  
  
## 참고 항목  
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)  
  
  