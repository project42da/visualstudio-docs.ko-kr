---
title: "SharePoint 프로젝트 시스템 확장 | Microsoft Docs"
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
helpviewer_keywords:
- SharePoint development in Visual Studio, extending projects
- SharePoint development in Visual Studio, extending project items
ms.assetid: 654b2973-a5c9-44be-a3d2-8bc3d15f9624
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 99380078b2fc49bcc5e1efb7a36ac7f28028a0d7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-the-sharepoint-project-system"></a>SharePoint 프로젝트 시스템 확장
  Visual Studio에서의 프로젝트 템플릿과 항목 템플릿 집합을 사용 하 여 SharePoint 솔루션을 만들 수 있습니다. 이러한 템플릿은 많은 개발 시나리오의 요구 사항을 충족 하지만 요구 되는 기능을 제공 하지 않는 경우에 따라 발견할 수 있습니다. 이러한 경우에 SharePoint 프로젝트 시스템을 확장할 수 있습니다.  
  
## <a name="overview-of-the-sharepoint-project-system"></a>SharePoint 프로젝트 시스템의 개요  
 SharePoint 프로젝트 시스템의 기본 구성 요소 기반 *SharePoint 프로젝트 항목*합니다. SharePoint 프로젝트 항목 목록 정의 웹 파트 콘텐츠 형식 등을 단일 SharePoint 사용자 지정을 나타냅니다.  
  
 SharePoint 프로젝트는 하나 이상의 SharePoint 프로젝트 항목을 포함 하는 Visual Studio 프로젝트. 또한 SharePoint 프로젝트 기능 및 배포에 대 한 패키지에 프로젝트 항목이 그룹화 되는 방법을 정의 하는 추가 구성 요소를 포함 합니다.  
  
 SharePoint 프로젝트 항목 및 SharePoint 프로젝트의 내용에 대 한 자세한 내용은 참조 하십시오. [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)합니다.  
  
## <a name="how-to-extend-the-sharepoint-project-system"></a>SharePoint 프로젝트 시스템을 확장 하는 방법  
 다음과 같은 방법으로 SharePoint 프로젝트 시스템을 확장할 수 있습니다.  
  
-   SharePoint 프로젝트 항목 형식을 사용자를 정의 하 고 새 항목 템플릿 또는 Visual Studio에서 프로젝트 템플릿 연결. 예를 들어, 필드 또는 사용자 지정 작업을 만들기 위한 SharePoint 프로젝트 항목 형식을 정의할 수 있습니다. 자세한 내용은 참조 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)합니다.  
  
-   Visual Studio에서 이미 설치 되어 있는 SharePoint 프로젝트 항목 형식 확장 합니다. 프로젝트 항목에 바로 가기 메뉴 항목을 추가할 수는 예를 들어 **솔루션 탐색기** 개발자 메뉴 항목을 선택할 때 프로젝트 항목을 사용자 지정 합니다. 자세한 내용은 참조 [SharePoint 프로젝트 항목 확장](../sharepoint/extending-sharepoint-project-items.md)합니다.  
  
-   SharePoint 프로젝트를 확장 합니다. 예를 들어 항목을 추가 하거나 SharePoint 프로젝트에서 제거할 때 특정 작업을 수행 하는 이벤트 처리기를 추가할 수 있습니다. 자세한 내용은 참조 [SharePoint 프로젝트 확장](../sharepoint/extending-sharepoint-projects.md)합니다.  
  
-   SharePoint 프로젝트 항목 및 SharePoint 프로젝트의 패키징 및 배포 동작을 확장 합니다. 예를 들어 배포 또는 프로젝트를 취소 하거나 Visual Studio는 특정 배포 단계를 실행 하는 경우 추가 사용자 지정 작업을 수행할 수 있습니다 때을 실행 하려면 고유한 배포 단계를 만들 수 있습니다. 자세한 내용은 참조 [확장 SharePoint 패키징 및 배포](../sharepoint/extending-sharepoint-packaging-and-deployment.md)합니다.  
  
## <a name="common-development-tasks"></a>일반적인 개발 작업  
 SharePoint 프로젝트 시스템의 확장에는 다음과 같은 일반적인 작업을 수행할 수 있습니다.  
  
-   프로젝트 항목 및 몇 가지 다른 형식의 프로젝트 파일에서 사용자 지정 문자열 데이터를 저장 합니다. 자세한 내용은 참조 [SharePoint 프로젝트 시스템의 확장에 대 한 데이터 저장](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)합니다.  
  
-   Visual Studio 자동화 개체 모델 또는 통합 개체 모델에서 해당 개체에는 SharePoint 프로젝트 시스템에서 개체를 변환 하거나 그 반대로 합니다. 자세한 내용은 참조 [변환 간의 SharePoint 프로젝트 시스템 형식과 기타 Visual Studio 프로젝트 형식](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [SharePoint 프로젝트 항목 확장](../sharepoint/extending-sharepoint-project-items.md)   
 [SharePoint 프로젝트 확장](../sharepoint/extending-sharepoint-projects.md)   
 [확장 SharePoint 패키징 및 배포](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [SharePoint 프로젝트 시스템의 확장에 데이터 저장](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [SharePoint 프로젝트 시스템 형식과 기타 Visual Studio 프로젝트 형식 간의 변환](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)   
 [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [SharePoint 도구 확장의 프로그래밍 개념 및 기능](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)  
  
  