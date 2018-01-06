---
title: "SharePoint 솔루션 개발을 위한 요구 사항 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, prerequisites
- SharePoint development in Visual Studio, requirements
ms.assetid: ae8ff69d-4540-4380-ab0b-845f7108e89c
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: a32ceee7609fca96f27388839415ec5ac4d219de
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="requirements-for-developing-sharepoint-solutions"></a>SharePoint 솔루션 개발 요구 사항
  Visual Studio에 포함 된 SharePoint 솔루션 개발 도구를 사용 하려면 먼저 시스템에 다음 필수 구성 요소를 설치 해야 합니다.  
  
-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)]또는 버전의 Visual Studio ALM 응용 프로그램 수명 주기 관리 ()을 지정 합니다.  
  
    -   중 하나는 [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)] 또는 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 기능 중 하나 또는 둘 모두를 설치할 때 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
-   [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]64 비트에 설치 된 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] 또는 64 비트 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] r 2입니다.  
  
     또는  
  
-   [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]64 비트에 설치 된 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] 또는 64 비트 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] r 2입니다.  
  
> [!NOTE]  
>  서버 운영 체제 에서만 공식적으로 SharePoint에서 사용할 수, 하는 동안 두 개의 클라이언트 운영 체제 허용 됩니다: [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 및 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] s p 1입니다. 자세한 내용은 참조 [SharePoint Server 2010 개발자 워크스테이션 설치 가이드](http://go.microsoft.com/fwlink/?LinkID=164557)합니다.  
  
 비즈니스 데이터 BDC (연결) 모델 프로젝트 형식에서는 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 시스템에 설치 합니다.  
  
 Visual Studio에서 SharePoint 솔루션을 개발 하려면 Visual Studio와 동일한 컴퓨터에 SharePoint를 설치 해야 합니다. SharePoint 개발자 도구는 SharePoint 독립 실행형 구성;만 지원 되는 또한 팜 (원격) 구성을 지원 하지 않습니다.  
  
> [!NOTE]  
>  Visual Studio에서 SharePoint 프로젝트만 지원 [!INCLUDE[net_v35_long](../sharepoint/includes/net-v35-long-md.md)]합니다. 선택 하는 경우 [!INCLUDE[net_v40_long](../sharepoint/includes/net-v40-long-md.md)] 를 새 SharePoint 프로젝트에 대 한 대상 여전히 됩니다 [!INCLUDE[net_v35_long](../sharepoint/includes/net-v35-long-md.md)]합니다.  
  
 설치 하는 방법에 대 한 자세한 내용은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 참조 [Visual Studio 설치](../install/install-visual-studio.md)합니다.  
  
## <a name="vista-and-windows-7-user-account-control-uac"></a>Vista 및 Windows 7 사용자 계정 컨트롤 (UAC)  
 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)]및 [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 로 사용자 계정 컨트롤 (UAC) 라고 하는 보안 기능을 통합 합니다. SharePoint 솔루션을 개발 하려면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] 및 [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 시스템 UAC 실행 해야 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 시스템 관리자입니다. 바탕 화면에서 바로 가기 메뉴를 열고 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 선택한 후 **관리자 권한으로 실행**합니다.  
  
 항상 관리자 권한으로 실행 바탕 화면 바로 가기의 구성 하려면 해당 바로 가기 메뉴를 열고 **속성**, 선택는 **고급** 단추를 선택한 다음 선택에서 **관리자 권한으로 실행**  확인란 합니다.  
  
 자세한 내용은 참조 [이해 및 Windows Vista에서 사용자 계정 컨트롤 구성](http://go.microsoft.com/fwlink/?LinkID=156476)합니다. 및 [Windows 7 사용자 계정 컨트롤](http://go.microsoft.com/fwlink/?LinkId=177523)합니다.  
  
## <a name="sharepoint-permissions-considerations"></a>SharePoint 사용 권한 고려 사항  
 SharePoint 솔루션을 개발 하려면 실행 하 고 SharePoint 솔루션을 디버깅할 충분 한 권한이 있어야 합니다. SharePoint 솔루션을 테스트할 수 있습니다, 전에 필요한 권한이 있는지 확인 하려면 다음 단계를 수행 합니다.  
  
1.  시스템에서 관리자 권한으로 사용자 계정을 추가 합니다.  
  
2.  팜 관리자는 SharePoint 서버에 대 한 사용자 계정에 추가 합니다.  
  
    1.  SharePoint 중앙 관리에서 선택 된 **팜 관리자 그룹 관리** 링크 합니다.  
  
    2.  에 **팜 관리자** 페이지를 선택 합니다는 **새로** 단추입니다.  
  
3.  에 사용자 계정을 추가 WSS_ADMIN_WPG 그룹에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작 &#40; Visual Studio &#41;에서 SharePoint 개발](../sharepoint/getting-started-sharepoint-development-in-visual-studio.md)  
  
  