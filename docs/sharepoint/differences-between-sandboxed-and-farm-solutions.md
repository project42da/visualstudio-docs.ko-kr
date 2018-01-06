---
title: "차이점 샌드박스 솔루션과 팜 솔루션 | Microsoft Docs"
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
- SharePoint development in Visual Studio, sandboxed solutions
- sandboxed solutions [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, farm solutions
- farm solutions [SharePoint development in Visual Studio]
ms.assetid: 43beb7e7-0cd9-4a8f-bb72-6b1e0cba5be8
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6c13d27f8c79f1bc638741d8877ac95a0dff4885
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="differences-between-sandboxed-and-farm-solutions"></a>샌드박스 솔루션과 팜 솔루션의 차이점
  SharePoint 솔루션을 컴파일하면, SharePoint 서버에 배포 및 디버깅 하려면 디버거가 연결 합니다. 솔루션을 디버깅 하는 프로세스는 샌드박스 솔루션 속성의 설정에 따라: 샌드박스 솔루션 또는 팜 솔루션입니다.  
  
 자세한 내용은 참조 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)합니다.  
  
## <a name="farm-solutions"></a>팜 솔루션  
 IIS 작업자 프로세스 (W3WP.exe)에서 호스팅되는 팜 솔루션은 전체 팜에 영향을 줄 수 있는 코드를 실행 합니다. 샌드박스 솔루션 속성이 "팜 솔루션"로 설정 되는 SharePoint 프로젝트를 디버깅할 때 SharePoint 제거 하거나 IIS 작업자 프로세스에서 잠근 파일을 해제 하기 위해 기능을 배포 하기 전에 시스템의 IIS 응용 프로그램 풀을 재활용 합니다. SharePoint 프로젝트의 사이트 URL을 서비스 IIS 응용 프로그램 풀이 재활용 됩니다.  
  
## <a name="sandboxed-solutions"></a>샌드박스 솔루션  
 솔루션의 사이트 모음에만 영향을 줄 수 있는 코드를 실행 하는 SharePoint 사용자 코드 솔루션 작업자 프로세스 (SPUCWorkerProcess.exe)에 호스팅되는 샌드 박싱된 솔루션. 샌드박스 솔루션 IIS 작업자 프로세스를 실행 하지 않으면 때문에 IIS 응용 프로그램 풀도 아니고 IIS 서버를 다시 시작 해야 합니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]SharePoint에서 SPUserCodeV4 서비스를 자동으로 트리거합니다 SPUCWorkerProcess 프로세스 및 컨트롤에 디버거를 연결 합니다. 솔루션의 최신 버전을 로드 재활용 SPUCWorkerProcess 프로세스에 대 한 필요는 없습니다.  
  
## <a name="either-type-of-solution"></a>두 종류의 솔루션  
 두 솔루션 형식의 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 또한 클라이언트 쪽 스크립트 디버깅을 사용 하도록 브라우저에 디버거를 연결 합니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]디버깅 엔진이이 목적을 위해 스크립트를 사용 합니다. 스크립트 디버깅을 사용 하려면 메시지가 표시 되는 경우 기본 브라우저 설정을 변경 해야 합니다.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]현재 사이트를 실행 중인 W3WP 또는 SPUCWorkerProcess 프로세스에만 디버거를 연결 합니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]또한 관리 되는 COM + 및 워크플로 디버깅 엔진을 연결 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 디버깅](../sharepoint/debugging-sharepoint-solutions.md)   
 [SharePoint 솔루션 빌드 및 디버깅](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)  
  
  