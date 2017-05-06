---
title: "Office 솔루션의 응용 프로그램 및 배포 매니페스트"
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
helpviewer_keywords: 
  - "매니페스트[Visual Studio에서 Office 개발]"
  - "배포 매니페스트[Visual Studio에서 Office 개발]"
  - "응용 프로그램 매니페스트[Visual Studio에서 Office 개발]"
  - "어셈블리[Visual Studio에서 Office 개발], 업데이트"
ms.assetid: 4e9abc7c-ef9f-4cb2-a7a9-c95c5f4a1fb7
caps.latest.revision: 45
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 44
---
# Office 솔루션의 응용 프로그램 및 배포 매니페스트
  응용 프로그램 매니페스트는 Office 솔루션에서 어셈블리를 찾고 업데이트하는 데 사용되는 정보를 제공하는 XML 파일입니다. 응용 프로그램 매니페스트는 배포 매니페스트와 함께 사용할 수 있습니다. 배포 매니페스트는 서버에 저장된 XML 파일로, 최신 버전의 응용 프로그램 매니페스트 및 어셈블리를 찾는 데 필요한 정보를 제공합니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## Office 솔루션의 매니페스트 구조  
 Visual Studio에서 Office 개발 도구를 사용하여 만든 Microsoft Office 솔루션의 경우 모든 매니페스트는 표준 ClickOnce 스키마를 기반으로 합니다. Office 솔루션을 배포할 때 문서 수준 및 VSTO 추가 기능 프로젝트의 응용 프로그램 매니페스트는 ClickOnce 캐시에 있습니다. 배포 매니페스트는 클라이언트 컴퓨터에 복사되지 않습니다.  
  
 Office 프로젝트에 대한 배포 매니페스트 및 응용 프로그램의 내용에 대한 자세한 내용은 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md) 및 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)를 참조하세요.  
  
## 응용 프로그램 및 배포 매니페스트 만들기  
 응용 프로그램 매니페스트는 빌드 프로세스의 일부로 자동으로 생성됩니다. 문서 수준 프로젝트를 빌드할 때마다 배포 매니페스트의 위치가 사용자 지정 문서 속성으로 문서에 포함됩니다. VSTO 추가 기능의 경우 배포 매니페스트의 위치는 레지스트리에 저장됩니다.  
  
 **게시 마법사**에 대한 자세한 내용은 [ClickOnce를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)를 참조하세요.  
  
 매니페스트가 Office 솔루션과 작동하는 방식에 대한 자세한 내용은 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)를 참조하세요.  
  
## 참고 항목  
 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)   
 [VSTO 추가 기능의 아키텍처](../vsto/architecture-of-vsto-add-ins.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Office 솔루션의 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)   
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)  
  
  