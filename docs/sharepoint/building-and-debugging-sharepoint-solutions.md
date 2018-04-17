---
title: SharePoint 솔루션 빌드 및 디버깅 | Microsoft Docs
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
- SharePoint development in Visual Studio, building and debugging
- SharePoint development in Visual Studio, debugging
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f797fbf14504e2856616a0709aabba70cd639446
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="building-and-debugging-sharepoint-solutions"></a>SharePoint 솔루션 빌드 및 디버깅
  일반적으로 SharePoint 솔루션 빌드 및 디버깅 같습니다 빌드 및 기타 유형의 프로젝트를 디버깅 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 이 섹션의 항목에서는 차이점에 대해 설명합니다.  
  
## <a name="project-output-for-sharepoint-solutions"></a>SharePoint 솔루션에 대 한 프로젝트 출력  
 SharePoint 솔루션 빌드 어셈블리 및 솔루션 패키지 (.wsp) 파일을 만듭니다. 다음 표에서 빌드하는 동안 이러한 파일의 위치를 보여 줍니다.  
  
|빌드 항목|출력 폴더|  
|----------------|-------------------|  
|어셈블리, 프로그램 데이터베이스 (PDB) 및.wsp 파일입니다.|*ProjectName*\bin\debug 또는 *ProjectName*\bin\release|  
|SharePoint 프로젝트 항목 파일입니다.|*ProjectName*\pkg\debug 또는 *ProjectName*\pkg\release|  
|중간 파일을 빌드하십시오.|*ProjectName*\obj\debug 또는 *ProjectName*\obj\release|  
|패키지 중간 파일입니다.|*ProjectName*\pkgobj\debug 또는 *ProjectName*\pkgobj\release|  
  
## <a name="building-sharepoint-solutions"></a>SharePoint 솔루션 빌드  
 SharePoint 솔루션을 빌드하려면 개발 컴퓨터의 올바른 버전의 SharePoint server 설치 되어 있어야 합니다. 그렇지 않은 경우 SharePoint 솔루션을 빌드하는 다른 유형의 프로젝트를 빌드하는 것과 동일한 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 자세한 내용은 참조 [하는 방법: SharePoint 솔루션 빌드](../sharepoint/how-to-build-sharepoint-solutions.md)합니다.  
  
## <a name="debugging-and-testing-sharepoint-solutions"></a>디버깅 및 SharePoint 솔루션 테스트  
 를 디버깅 하려면 먼저 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] .wsp 패키지가 SharePoint 서버에 복사 하 고, 사이트 및 웹 범위 기능을 활성화 및 일부 경우에는 프로젝트를 시작 합니다. 수동으로 프로젝트를 열어야 하는 경우도 있습니다. 자세한 내용은 참조 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md) 및 [SharePoint 솔루션 디버깅](../sharepoint/debugging-sharepoint-solutions.md)합니다.  
  
## <a name="debugging-and-verifying-sharepoint-solutions-by-using-alm-features"></a>ALM 기능을 사용하여 SharePoint 솔루션 디버깅 및 확인  
 단위 테스트 및 IntelliTrace와 같은 Visual Studio ALM 기능을 사용하면 SharePoint 솔루션에서 보다 정확하게 문제를 찾아낼 수 있습니다. 프로파일링을 통해 SharePoint 솔루션에서 성능 문제 영역을 찾고 식별할 수 있습니다. 자세한 내용은 참조 [여부 확인 하 고 SharePoint 코드 디버깅](../sharepoint/verifying-and-debugging-sharepoint-code.md) 및 [성능의 SharePoint 응용 프로그램을 프로 파일링](../sharepoint/profiling-the-performance-of-sharepoint-applications.md)합니다.  
  
## <a name="security-during-the-build-process"></a>빌드 프로세스 중 보안  
 SharePoint 솔루션을 배포 또는 패키지 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 파일 SharePoint 서버에 복사할 수 있는 권한이 있어야 합니다. 실행 해야 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 권한 상승된 된 프로세스 및 사용자로 계정 SharePoint 서버에 사이트 컬렉션 관리자 여야 합니다. 또한 프로젝트를 샌드박스 솔루션 인지 팜 솔루션 인지 지정 해야 합니다. 자세한 내용은 참조 [차이점 샌드박스 솔루션과 팜 솔루션 간](../sharepoint/differences-between-sandboxed-and-farm-solutions.md)합니다.  
  
## <a name="using-the-clean-command"></a>정리 명령 사용  
 SharePoint 솔루션 디버깅을 위해 SharePoint 서버에 설치 된 경우는 **Clean** 명령 솔루션을 제거 하지 않습니다. 대신, SharePoint 구성을 통해 기능을 비활성화 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)   
 [서버 탐색기를 사용 하 여 SharePoint 연결 찾아보기](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  