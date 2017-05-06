---
title: "SharePoint 솔루션 빌드 및 디버깅"
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
  - "Visual Studio에서 SharePoint 개발, 빌드 및 디버깅"
  - "Visual Studio에서 SharePoint 개발, 디버깅"
ms.assetid: c9e7c9ab-4eb3-40cd-a9b9-6c2a896f70ae
caps.latest.revision: 14
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# SharePoint 솔루션 빌드 및 디버깅
  일반적으로 SharePoint 솔루션을 빌드하고 디버깅하는 작업은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]의 다른 프로젝트 형식을 빌드하고 디버깅하는 것과 같습니다.  이 단원의 항목에서는 이 둘 사이의 차이점에 대해 설명합니다.  
  
## SharePoint 솔루션의 프로젝트 출력  
 SharePoint 솔루션을 빌드하면 어셈블리와 솔루션 패키지 파일\(.wsp\)이 만들어집니다.  다음 표는 빌드하는 동안 이러한 파일의 위치를 보여 줍니다.  
  
|빌드 항목|출력 폴더|  
|-----------|-----------|  
|어셈블리, 프로그램 데이터베이스\(PDB\) 및 .wsp 파일|*ProjectName*\\bin\\debug 또는 *ProjectName*\\bin\\release|  
|SharePoint 프로젝트 항목 파일|*ProjectName*\\pkg\\debug 또는 *ProjectName*\\pkg\\release|  
|빌드 중간 파일|*ProjectName*\\obj\\debug 또는 *ProjectName*\\obj\\release|  
|패키지 중간 파일|*ProjectName*\\pkgobj\\debug 또는 *ProjectName*\\pkgobj\\release|  
  
## SharePoint 솔루션 빌드  
 SharePoint 솔루션을 빌드하려면 개발 컴퓨터에 올바른 버전의 SharePoint 서버가 설치되어 있어야 합니다.  그렇지 않으면 SharePoint 솔루션을 빌드하는 작업은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]의 다른 프로젝트 형식을 빌드하는 것과 같습니다.  자세한 내용은 [방법: SharePoint 솔루션 빌드](../sharepoint/how-to-build-sharepoint-solutions.md)을 참조하십시오.  
  
## SharePoint 솔루션 디버깅 및 테스트  
 디버깅 전에 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 .wsp 패키지를 SharePoint 서버에 복사하고 사이트 및 웹 범위 기능을 활성화한 다음 경우에 따라 프로젝트를 시작합니다.  그렇지 않으면 수동으로 프로젝트를 열어야 합니다.  자세한 내용은 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md) 및 [SharePoint 솔루션 디버깅](../sharepoint/debugging-sharepoint-solutions.md)를 참조하십시오.  
  
## ALM 기능을 사용하여 SharePoint 솔루션 디버깅 및 확인  
 단위 테스트 및 IntelliTrace와 같은 Visual Studio ALM 기능은 SharePoint 솔루션에서 보다 정확하게 문제를 찾아내도록 해줍니다.  프로 파일링은 SharePoint 솔루션에서 성능 문제 영역을 찾고 식별할 수 있게 합니다.  자세한 내용은 [SharePoint 코드 확인 및 디버깅](../sharepoint/verifying-and-debugging-sharepoint-code.md) 및 [SharePoint 응용 프로그램 성능 프로파일링](../sharepoint/profiling-the-performance-of-sharepoint-applications.md)를 참조하십시오.  
  
## 빌드 프로세스 중의 보안  
 SharePoint 솔루션을 패키지하거나 배포하려면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 파일을 SharePoint 서버에 복사할 권한이 있어야 합니다.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 관리자 권한 프로세스로 실행해야 하고 사용자 계정이 SharePoint 서버에서 사이트 컬렉션 관리자여야 합니다.  또한 프로젝트가 샌드박스 솔루션인지 아니면 팜 솔루션인지를 지정해야 합니다.  자세한 내용은 [샌드박스 솔루션과 팜 솔루션의 차이점](../sharepoint/differences-between-sandboxed-and-farm-solutions.md)을 참조하십시오.  
  
## 정리 명령 사용  
 SharePoint 솔루션이 디버깅을 위해 SharePoint 서버에 설치된 경우 **정리** 명령을 실행하면 솔루션이 제거되지 않습니다.  대신 SharePoint 구성을 통해 기능을 비활성화해야 합니다.  
  
## 참고 항목  
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)   
 [서버 탐색기를 사용하여 SharePoint 연결 찾아보기](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  