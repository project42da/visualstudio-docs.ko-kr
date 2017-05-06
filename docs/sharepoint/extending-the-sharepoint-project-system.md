---
title: "Extending the SharePoint Project System"
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
  - "SharePoint development in Visual Studio, extending projects"
  - "SharePoint development in Visual Studio, extending project items"
ms.assetid: 654b2973-a5c9-44be-a3d2-8bc3d15f9624
caps.latest.revision: 38
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 38
---
# Extending the SharePoint Project System
  Visual Studio 프로젝트 템플릿과 항목 템플릿 집합을 사용 하 여 SharePoint 솔루션을 만들 수 있습니다.  이러한 템플릿은 많은 개발 시나리오의 요구 사항을 충족 하지만 사용자 들은 필요한 기능을 제공 하지 않는 경우도 있을 수 있습니다.  이 경우 SharePoint 프로젝트 시스템을 확장할 수 있습니다.  
  
## SharePoint 프로젝트 시스템 개요  
 SharePoint 프로젝트 시스템은 *SharePoint 프로젝트 항목*이라는 기본 구성 요소를 기반으로 합니다.  SharePoint 프로젝트 항목은 목록 정의, 웹 파트, 콘텐츠 형식 등과 같은 단일 SharePoint 사용자 지정을 나타냅니다.  
  
 SharePoint 프로젝트는 하나 이상의 SharePoint 프로젝트 항목을 포함하는 Visual Studio 프로젝트입니다.  SharePoint 프로젝트에는 배포를 위한 기능 및 패키지로 프로젝트 항목을 그룹화하는 방식을 정의하는 추가 구성 요소도 포함됩니다.  
  
 SharePoint 프로젝트 항목과 SharePoint 프로젝트의 콘텐츠에 대한 자세한 내용은 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)를 참조하십시오.  
  
## SharePoint 프로젝트 시스템 확장 방법  
 다음과 같은 방법으로 SharePoint 프로젝트 시스템을 확장할 수 있습니다.  
  
-   고유한 SharePoint 프로젝트 항목 형식을 정의하고 Visual Studio에서 이를 새 항목 템플릿 또는 프로젝트 템플릿에 연결합니다.  예를 들어 사용자 지정 작업 또는 필드를 만들기 위한 SharePoint 프로젝트 항목 형식을 정의할 수 있습니다.  자세한 내용은 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)을 참조하십시오.  
  
-   Visual Studio에 이미 설치되어 있는 SharePoint 프로젝트 항목 형식을 확장합니다.  프로젝트 항목에 바로 가기 메뉴 항목을 추가할 수 있습니다 예를 들어,  **솔루션 탐색기** 하 고 개발자가 메뉴 항목을 선택할 때 프로젝트 항목을 사용자 지정 합니다.  자세한 내용은 [Extending SharePoint Project Items](../sharepoint/extending-sharepoint-project-items.md)을 참조하십시오.  
  
-   SharePoint 프로젝트 확장  예를 들어 SharePoint 프로젝트에서 항목을 추가하거나 제거할 때 특정 작업을 수행하는 이벤트 처리기를 추가할 수 있습니다.  자세한 내용은 [Extending SharePoint Projects](../sharepoint/extending-sharepoint-projects.md)을 참조하십시오.  
  
-   SharePoint 프로젝트 항목과 SharePoint 프로젝트의 패키징 및 배포 동작을 확장합니다.  예를 들어 프로젝트를 배포하거나 제거할 때 실행할 고유한 배포 단계를 만들거나, Visual Studio에서 특정 배포 단계를 실행할 때 추가 사용자 지정 작업을 수행할 수 있습니다.  자세한 내용은 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)을 참조하십시오.  
  
## 일반적인 개발 작업  
 SharePoint 프로젝트 시스템의 확장에서는 다음과 같은 일반적인 작업을 수행할 수 있습니다.  
  
-   프로젝트 항목과 몇 가지 형식의 프로젝트 파일에 사용자 지정 문자열 데이터를 저장합니다.  자세한 내용은 [Saving Data in Extensions of the SharePoint Project System](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)을 참조하십시오.  
  
-   SharePoint 프로젝트 시스템의 개체를 Visual Studio 자동화 개체 모델이나 통합 개체 모델의 해당 개체로 변환하거나 그 반대로 변환합니다.  자세한 내용은 [Converting Between SharePoint Project System Types and Other Visual Studio Project Types](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)을 참조하십시오.  
  
## 참고 항목  
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Extending SharePoint Project Items](../sharepoint/extending-sharepoint-project-items.md)   
 [Extending SharePoint Projects](../sharepoint/extending-sharepoint-projects.md)   
 [Extending SharePoint Packaging and Deployment](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Saving Data in Extensions of the SharePoint Project System](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [Converting Between SharePoint Project System Types and Other Visual Studio Project Types](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)   
 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Programming Concepts and Features for SharePoint Tools Extensions](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)  
  
  