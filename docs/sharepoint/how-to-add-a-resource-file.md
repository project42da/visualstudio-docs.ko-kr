---
title: "방법: 리소스 파일 추가 | Microsoft Docs"
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
  - "리소스 파일[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 리소스 파일"
ms.assetid: 2b4ac232-992e-4070-8e98-6f11eb88e1a8
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# 방법: 리소스 파일 추가
  리소스 파일을 추가하는 데 사용되는 명령은 솔루션 탐색기에 있는 솔루션 노드와 기능 노드의 바로 가기 메뉴에 있습니다.  자세한 내용은 [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)을 참조하십시오.  
  
### SharePoint 솔루션에 전역 리소스 파일을 추가하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 SharePoint 솔루션을 엽니다.  
  
2.  **솔루션 탐색기** 에서 프로젝트 노드를 클릭한 다음 **프로젝트** 메뉴에서 **새 항목 추가** 를 선택합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **전역 리소스 파일** 템플릿을 선택한 후 **추가** 버튼을 선택합니다.  
  
    > [!NOTE]  
    >  전역 리소스 파일 프로젝트 항목 템플릿은 SharePoint 프로젝트 항목을 선택한 경우에만 나타납니다.  
  
4.  **리소스 추가** 대화 상자에서 리소스 파일의 문화권을 선택합니다\(예: 영어\(미국\)\).  
  
     이 단계에서는 전역 리소스 파일이 Resource*x**culture*resx 형식으로 솔루션에 추가됩니다\(예: Resource1.en\-US.resx\).  
  
5.  **리소스 편집기** 가 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 열리는 경우, 리소스 파일에 리소스를 추가 합니다.  
  
### SharePoint 기능에 기능 리소스 파일을 추가하려면  
  
1.  SharePoint 솔루션이 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에 열려 있지 않은 경우, 솔루션을 엽니다.  
  
2.  **솔루션 탐색기** 에서 **기능** 노드 아래의 기능 이름에 대한 바로 가기 메뉴를 연 다음 **기능 리소스 추가** 를 선택합니다.  
  
     이 단계에서 Feature1.en US.resx 와 같은 *ResourceFileName***.***culture***.**resx 형식의 기능에 리소스 파일을 추가합니다.  
  
3.  **리소스 편집기** 가 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 열리는 경우, 리소스 파일에 리소스를 추가 합니다.  
  
## 참고 항목  
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  