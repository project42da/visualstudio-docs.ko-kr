---
title: "Extending the SharePoint Tools in Visual Studio | Microsoft Docs"
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
  - "Visual Studio, extending tools"
  - "extensibility [SharePoint development in Visual Studio]"
  - "SharePoint development in Visual Studio, extending tools"
ms.assetid: 084cf4bf-aaba-4277-8032-448f2cb2a124
caps.latest.revision: 39
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 38
---
# Extending the SharePoint Tools in Visual Studio
  SharePoint 도구Visual Studio에서 대부분의응용 프로그램개발 시나리오의 요구 사항을 충족합니다.  사용자나 다른 개발자에게 필요한 기능을 제공하지 않는 경우도 있을 수 있습니다.  이 경우 SharePoint 도구를 확장하여 필요한 기능을 만들 수 있습니다.  
  
## SharePoint 도구를 확장하는 방법  
 **서버 탐색기** 창에서 SharePoint 프로젝트 시스템 및 **SharePoint 연결** 노드를 확장할 수 있습니다.  
  
### SharePoint 프로젝트 시스템 확장  
 Visual Studio프로젝트템플릿 및항목템플릿을만들다SharePoint 솔루션을 사용할 수 있습니다 집합이 포함 되어 있습니다.  예를 들어 이벤트 수신자, 목록 정의, 워크플로 및 웹 파트에 대한 템플릿이 있습니다.  그러나 필드 또는 사용자 지정 작업 같은 SharePoint 구성 요소를 만들기 위해 고유한 SharePoint 프로젝트 항목 형식을 직접 정의할 수도 있습니다.  또한 Visual Studio에 이미 설치되어 있는 SharePoint 프로젝트 항목 형식을 위한 확장을 만들 수 있고, SharePoint 프로젝트를 위한 확장도 만들 수 있습니다.  
  
 자세한 내용은 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)을 참조하십시오.  
  
### 서버 탐색기에서 SharePoint 연결 노드 확장  
 Visual Studio사용할 수 있습니다의  **SharePoint 연결** 에서 노드는**서버 탐색기** 많은 구성 요소 중 하나 이상의 로컬 SharePoint 사이트는 계층트리보기에서창. 또한 확장할 수 있습니다에서  **SharePoint 연결** 노드를 사용할 수 있습니다.  
  
-   고유한 노드 추가.  이 방법은 기본적으로 표시되지 않는 SharePoint 사이트의 구성 요소를 표시하려는 경우에 유용합니다.  
  
-   기존 노드 확장.  예를 들어 기존 노드에 새 자식 노드를 추가할 수도 있고, 노드에 바로 가기 메뉴 항목을 추가하고 개발자가 메뉴 항목을 클릭할 때 작업을 수행할 수 있습니다.  
  
 자세한 내용은 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)을 참조하십시오.  
  
## 개발 컴퓨터 요구 사항  
 SharePoint 도구를만들다확장을 개발 컴퓨터 같은Visual Studio에서 SharePoint 솔루션을 만들기 위한 요구 사항을 충족 해야 합니다.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
 가능하면 [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]도 설치하는 것이 좋습니다.  SDK에는 Visual Studio를 확장하는 데 사용할 수 있는 프로젝트 템플릿과 도구가 포함되어 있습니다.  특히 SDK에는 VSIX\(Visual Studio Extension\) 패키지를 쉽게 만드는 데 사용할 수 있는 프로젝트 템플릿이 들어 있습니다.  VSIX 패키지Visual StudioVisual Studio확장을배포하다하는 기본 방법입니다.   모든 SharePoint 도구 확장은 VSIX 패키지를 사용하여 배포해야 합니다.  이 문서의 모든 연습에서는 [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]가 설치되어 있다고 가정합니다.  
  
 SDK는 [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=164562](http://go.microsoft.com/fwlink/?LinkId=164562)에서 다운로드할 수 있습니다.  Visual Studio 확장에 대한 자세한 내용은 [Visual Studio 확장 개발](../Topic/Developing%20Visual%20Studio%20Extensions.md)을 참조하십시오.  
  
## 참고 항목  
 [Overview of the Programming Model of SharePoint Tools Extensions](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)   
 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [Programming Concepts and Features for SharePoint Tools Extensions](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)   
 [Reference &#40;SharePoint Tools Extensibility&#41;](../sharepoint/reference-sharepoint-tools-extensibility.md)   
 [Debugging Extensions for the SharePoint Tools in Visual Studio](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)   
 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  