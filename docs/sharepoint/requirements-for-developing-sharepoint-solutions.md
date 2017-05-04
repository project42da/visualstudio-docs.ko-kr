---
title: "SharePoint 솔루션 개발 요구 사항 | Microsoft Docs"
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
  - "Visual Studio에서 SharePoint 개발, 필수 구성 요소"
  - "Visual Studio에서 SharePoint 개발, 요구 사항"
ms.assetid: ae8ff69d-4540-4380-ab0b-845f7108e89c
caps.latest.revision: 40
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 39
---
# SharePoint 솔루션 개발 요구 사항
  Visual Studio에 포함된 SharePoint 솔루션 개발 도구를 사용하려면 먼저 시스템에 다음 필수 구성 요소를 설치해야 합니다.  
  
-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)] 또는 Visual Studio ALM\(Application Lifecycle Management\)의 버전  
  
    -   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 설치할 때 [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)] 또는 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 기능 중 하나 또는 모두를 설치해야 합니다.  
  
-   64비트 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] 또는 64비트 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] R2에 설치된 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]  
  
     또는  
  
-   64비트 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] 또는 64비트 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] R2에 설치된 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]  
  
> [!NOTE]  
>  서버 운영 체제는 SharePoint에서 공식적으로 지원 되지만, 두 개의 클라이언트 운영 체제를 허용합니다. \([!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 와 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] SP1\)  자세한 내용은 [SharePoint Server 2010 개발자 워크스테이션 설치 가이드](http://go.microsoft.com/fwlink/?LinkID=164557) 을 참조하십시오.  
  
 BDC\(비즈니스 데이터 연결\) 모델 프로젝트 형식을 사용하려면 시스템에 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]이 설치되어 있어야 합니다.  
  
 Visual Studio에서 SharePoint 솔루션을 개발하려면 Visual Studio와 동일한 컴퓨터에 SharePoint를 설치해야 합니다.  또한 SharePoint 개발자 도구는 SharePoint 독립 실행형 구성만 지원하고 팜 \(원격\) 구성은 지원하지 않습니다.  
  
> [!NOTE]  
>  Visual Studio SharePoint 프로젝트는 [!INCLUDE[net_v35_long](../sharepoint/includes/net-v35-long-md.md)] 만 지원합니다.  새 SharePoint 프로젝트에 대해 [!INCLUDE[net_v40_long](../sharepoint/includes/net-v40-long-md.md)]를 선택하더라도 [!INCLUDE[net_v35_long](../sharepoint/includes/net-v35-long-md.md)]가 사용됩니다.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 설치하는 방법에 대한 자세한 내용은 [Visual Studio 설치](../Topic/Installing%20Visual%20Studio.md)를 참조하십시오.  
  
## Vista 및 Windows 7 사용자 계정 컨트롤  
 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] 및 [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 에는 사용자 계정 컨트롤\(UAC\)로 알려진 보안 기능이 통합되어 있습니다.  [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] 및 [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 시스템의 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 솔루션을 개발하려면 UAC의 요구 사항에 따라 시스템 관리자로 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 실행해야 합니다.  데스크톱에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 바로 가기 메뉴를 연 다음 **관리자 권한으로 실행** 을 선택합니다.  
  
 바탕 화면 바로 가기가 항상 관리자로 실행되도록 구성하려면 바로 가기 메뉴를 열어서 **속성**, **고급** 를 차례대로 선택한 다음 **관리자 권한으로 실행** 을 선택합니다.  
  
 자세한 내용은 [Windows Vista의 사용자 계정 컨트롤 이해 및 구성](http://go.microsoft.com/fwlink/?LinkID=156476) 및 [Windows 7 사용자 계정 컨트롤](http://go.microsoft.com/fwlink/?LinkId=177523) 을 참조하십시오.  
  
## SharePoint 사용 권한 고려 사항  
 SharePoint 솔루션을 개발하려면 SharePoint 솔루션을 실행 및 디버깅할 수 있는 권한이 있어야 합니다.  SharePoint 솔루션을 테스트하기 전에 먼저 다음 단계를 수행하여 필요한 권한이 있는지 확인합니다.  
  
1.  시스템의 관리자로 사용자 계정을 추가합니다.  
  
2.  SharePoint 서버의 팜 관리자로 사용자 계정을 추가합니다.  
  
    1.  SharePoint 중앙 관리에서 **팜 관리자 그룹 관리** 링크를 클릭합니다.  
  
    2.  **팜 관리자** 페이지에서 **새** 단추를 클릭합니다.  
  
3.  WSS\_ADMIN\_WPG 그룹에 사용자 계정을 추가합니다.  
  
## 참고 항목  
 [Getting Started &#40;SharePoint Development in Visual Studio&#41;](../sharepoint/getting-started-sharepoint-development-in-visual-studio.md)  
  
  