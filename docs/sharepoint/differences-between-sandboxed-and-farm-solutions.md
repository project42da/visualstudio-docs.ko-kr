---
title: "샌드박스 솔루션과 팜 솔루션의 차이점"
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
  - "팜 솔루션[Visual Studio에서 SharePoint 개발]"
  - "샌드박싱된 솔루션[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 팜 솔루션"
  - "Visual Studio에서 SharePoint 개발, 샌드박싱된 솔루션"
ms.assetid: 43beb7e7-0cd9-4a8f-bb72-6b1e0cba5be8
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 샌드박스 솔루션과 팜 솔루션의 차이점
  SharePoint 솔루션을 컴파일하면 솔루션이 서버에 배포되고 솔루션을 디버깅하기 위해 디버거가 연결됩니다.  솔루션을 디버깅하는 데 사용되는 프로세스는 샌드박스가 적용된 솔루션 속성의 설정\(샌드박스가 적용된 솔루션 또는 팜 솔루션\)에 따라 다릅니다.  
  
 자세한 내용은 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)을 참조하십시오.  
  
## 팜 솔루션  
 IIS 작업자 프로세스\(W3WP.exe\)에서 호스팅되는 팜 솔루션은 전체 팜에 영향을 줄 수 있는 코드를 실행합니다.  샌드박스가 적용된 솔루션 속성이 "팜 솔루션"으로 설정된 SharePoint 프로젝트를 디버깅하면 IIS 작업자 프로세스에서 잠근 파일을 해제하기 위해 SharePoint가 기능을 제거하거나 배포하기 전에 시스템의 IIS 응용 프로그램 풀이 재생됩니다.  이 경우 SharePoint 프로젝트의 사이트 URL에 서비스를 제공하는 IIS 응용 프로그램 풀만 재생됩니다.  
  
## 샌드박스가 적용된 솔루션  
 SharePoint 사용자 코드 솔루션 작업자 프로세스\(SPUCWorkerProcess.exe\)에서 호스팅되는 샌드박스가 적용된 솔루션은 해당 솔루션의 사이트 컬렉션에만 영향을 줄 수 있는 코드를 실행합니다.  샌드박스가 적용된 솔루션은 IIS 작업자 프로세스에서 실행되지 않기 때문에 IIS 응용 프로그램 풀 또는 IIS 서버를 다시 시작하면 안 됩니다.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 SharePoint의 SPUserCodeV4 서비스에서 자동으로 트리거하고 제어하는 SPUCWorkerProcess 프로세스에 디버거를 연결합니다.  솔루션의 최신 버전을 로드하기 위해 SPUCWorkerProcess 프로세스를 재생할 필요는 없습니다.  
  
## 두 가지 솔루션 형식  
 또한 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 두 가지 솔루션 형식에 대해 클라이언트 쪽 스크립트 디버깅을 사용할 수 있도록 디버거를 브라우저에 연결합니다.  이를 위해 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 스크립트 디버깅 엔진을 사용합니다.  스크립트 디버깅을 사용하려면 메시지가 표시될 때 기본 브라우저 설정을 변경해야 합니다.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 현재 사이트를 실행 중인 W3WP 또는 SPUCWorkerProcess 프로세스에만 디버거를 연결합니다.  또한 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서는 관리되는 COM Plus와 워크플로 디버깅 엔진을 연결합니다.  
  
## 참고 항목  
 [SharePoint 솔루션 디버깅](../sharepoint/debugging-sharepoint-solutions.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)  
  
  