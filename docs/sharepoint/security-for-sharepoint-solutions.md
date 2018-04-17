---
title: SharePoint 솔루션에 대 한 보안 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- security [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, security
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 471de3ab69a969f5153723658c628d659038c3a0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="security-for-sharepoint-solutions"></a>SharePoint 솔루션 보안
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 응용 프로그램의 보안을 향상 시키려면 다음과 같은 기능을 통합 합니다.  
  
## <a name="safe-control-entries"></a>안전 컨트롤 항목  
 모든 SharePoint 프로젝트 항목에서 만든 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에 **안전 컨트롤 항목** 안전 하 게 나타내는 속성 컬렉션을 제어 합니다. 해당 **안전** 하위 속성을 사용 하면 보안을 고려 하는 컨트롤을 지정할 수 있습니다. 자세한 내용은 참조 [패키징 및 배포 프로젝트 항목에는 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) 및 [안전한 웹 파트를 지정 하](http://go.microsoft.com/fwlink/?LinkId=177521)합니다.  
  
## <a name="allowpartiallytrustedcallers-attribute"></a>AllowPartiallyTrustedCallers 특성  
 기본적으로 런타임 코드 액세스 보안 (CA) 시스템에서 완전히 신뢰 하는 응용 프로그램만 공유 관리 코드 어셈블리에 액세스할 수 있습니다. AllowPartiallyTrustedCallers 특성으로 완전 신뢰 어셈블리 표시 부분적으로 신뢰할 수 있는 어셈블리를 액세스할 수 있습니다.  
  
 AllowPartiallyTrustedCallers 특성이 시스템 전역 어셈블리 캐시에 배포 되지 않은 모든 SharePoint 솔루션에 추가 됩니다 ([!INCLUDE[TLA2#tla_gac](../sharepoint/includes/tla2sharptla-gac-md.md)]). 샌드박스 솔루션 또는 SharePoint 응용 프로그램의 Bin 디렉터리에 배포 된 솔루션이 포함 됩니다. 자세한 내용은 참조 [버전 1은 Microsoft.NET Framework에 대 한 변경 내용을 보안](http://go.microsoft.com/fwlink/?LinkId=177515) 및 [SharePoint Foundation의 웹 파트 배포](http://go.microsoft.com/fwlink/?LinkId=177509)합니다.  
  
## <a name="safe-against-script-property"></a>스크립트 속성에 대해 안전  
 *삽입 스크립트* 컨트롤이 나 웹 페이지에 잠재적으로 악의적인 코드가 삽입 됩니다. 스크립트 삽입에 대해 SharePoint 2010 사이트를 보호 하려면 참가자 보거나 기본적으로 웹 파트 또는 해당 속성을 편집할 수 없습니다. 이 동작은 SafeAgainstScript 라고 하는 SafeControl 특성으로 제어 됩니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 프로젝트 항목의에이 특성을 설정 **안전 컨트롤 항목** 하위 속성 **스크립트에 대해 안전**합니다. 자세한 내용은 참조 [패키징 및 배포 프로젝트 항목에는 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) 및 [하는 방법: 안전 컨트롤로 표시 컨트롤](../sharepoint/how-to-mark-controls-as-safe-controls.md)합니다.  
  
## <a name="vista-and-windows-7-user-account-control"></a>Vista 및 Windows 7 사용자 계정 컨트롤  
 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] 및 [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 사용자 계정 컨트롤 (UAC)으로 보안 기능이 통합 되어 있습니다. SharePoint 솔루션을 개발 하려면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] 및 [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 시스템 UAC 실행 해야 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 시스템 관리자입니다. **시작** 메뉴에 대 한 바로 가기 메뉴를 열고 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 선택한 후 **관리자 권한으로 실행**합니다.  
  
 구성 하는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 항상 관리자 권한으로 실행 하 고, 해당 바로 가기 메뉴를 열고,을 선택 하려면 바로 가기 **속성**, 선택는 **고급** 단추는 **속성**대화 상자를 닫은 다음 선택에서 **관리자 권한으로 실행** 확인란 합니다.  
  
 자세한 내용은 참조 [이해 및 Windows Vista에서 사용자 계정 컨트롤 구성](http://go.microsoft.com/fwlink/?LinkID=156476)합니다. 및 [Windows 7 사용자 계정 컨트롤](http://go.microsoft.com/fwlink/?LinkId=177523)합니다.  
  
## <a name="sharepoint-permissions-considerations"></a>SharePoint 사용 권한 고려 사항  
 SharePoint 솔루션을 개발 하려면 실행 하 고 SharePoint 솔루션을 디버깅할 충분 한 권한이 있어야 합니다. SharePoint 솔루션을 테스트할 수 있습니다, 전에 필요한 권한이 있는지 확인 하려면 다음 단계를 수행 합니다.  
  
1.  시스템에서 관리자 권한으로 사용자 계정을 추가 합니다.  
  
2.  팜 관리자는 SharePoint 서버에 대 한 사용자 계정에 추가 합니다.  
  
    1.  SharePoint 2010 중앙 관리에서 선택 된 **팜 관리자 그룹 관리** 링크 합니다.  
  
    2.  에 **팜 관리자** 페이지에서 선택 된 **새로** 메뉴 옵션  
  
3.  에 사용자 계정을 추가 WSS_ADMIN_WPG 그룹에 있습니다.  
  
## <a name="additional-security-resources"></a>추가 보안 리소스  
 보안 문제에 대 한 자세한 내용은 다음 항목을 참조 합니다.  
  
### <a name="visual-studio-security"></a>Visual Studio 보안  
  
-   [보안 및 사용자 권한](http://go.microsoft.com/fwlink/?LinkId=177503)  
  
-   [네이티브 및.NET Framework 코드에서 보안](http://go.microsoft.com/fwlink/?LinkId=177504)  
  
-   [.NET framework 보안](http://go.microsoft.com/fwlink/?LinkId=177502)  
  
### <a name="sharepoint-security"></a>SharePoint 보안  
  
-   [SharePoint Foundation 관리 및 보안](http://go.microsoft.com/fwlink/?LinkId=177501)  
  
-   [SharePoint 보안 리소스 센터](http://go.microsoft.com/fwlink/?LinkId=177498)  
  
-   [SharePoint Foundation의 웹 파트를 보안 설정](http://go.microsoft.com/fwlink/?LinkId=177511)  
  
-   [웹 응용 프로그램 보안 개선: 위협 및 대책](http://go.microsoft.com/fwlink/?LinkID=140080)  
  
### <a name="general-security"></a>일반 보안  
  
-   [MSDN 보안 개발 수명 주기](http://go.microsoft.com/fwlink/?LinkID=147149)  
  
-   [보안 ASP.NET 응용 프로그램 빌드: 인증, 권한 부여 및 보안 통신](http://go.microsoft.com/fwlink/?LinkId=177494)  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)  
  
  