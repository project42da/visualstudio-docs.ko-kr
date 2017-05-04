---
title: "How to: Create a SharePoint Project Item Extension | Microsoft Docs"
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
  - "project items [SharePoint development in Visual Studio], extending"
  - "SharePoint project items, extending"
  - "SharePoint development in Visual Studio, extending project items"
ms.assetid: 163738b9-e25a-49c9-8f33-4b57a2da6b07
caps.latest.revision: 31
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 30
---
# How to: Create a SharePoint Project Item Extension
  Visual Studio에 이미 설치되어 있는 SharePoint 프로젝트 항목에 기능을 추가하려는 경우 프로젝트 항목 확장을 만듭니다.  자세한 내용은 [Extending SharePoint Project Items](../sharepoint/extending-sharepoint-project-items.md)를 참조하십시오.  
  
### 프로젝트 항목 확장을 만들려면  
  
1.  클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 인터페이스를 구현하는 클래스를 만듭니다.  
  
4.  클래스에 다음 특성을 추가합니다.  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>.  이 특성을 사용하면 Visual Studio에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 구현을 찾아 로드할 수 있습니다.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 형식을 특성 생성자에 전달합니다.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>.  프로젝트 항목 확장에서 이 특성은 확장할 프로젝트 항목을 식별합니다.  프로젝트 항목의 ID를 특성 생성자에 전달합니다.  Visual Studio에 포함 된프로젝트항목의 id에 대 한 목록은 [Extending SharePoint Project Items](../sharepoint/extending-sharepoint-project-items.md).  
  
5.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> 메서드 구현에서 *projectItemType* 매개 변수의 멤버를 사용하여 확장의 동작을 정의합니다.  이 매개 변수는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFileEvents> 인터페이스에 정의된 이벤트에 대한 액세스를 제공하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> 개체입니다.  확장할 프로젝트 항목 형식의 특정 인스턴스에 액세스하려면 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemInitialized> 등과 같은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> 이벤트를 처리합니다.  
  
## 예제  
 다음 코드 예제에서는 간단한 이벤트 수신자 프로젝트 항목의 확장을 만드는 방법을 보여 줍니다.  사용자가 SharePoint 프로젝트에서 이벤트 수신자 프로젝트 항목을 추가할 때마다 이 확장에서 **출력** 창과 **오류 목록** 창에 메시지를 씁니다.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/cs/extension/projectitemextension.cs#1)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectsystemextension.general/vb/extension/projectitemextension.vb#1)]  
  
 이 예제에서는 SharePoint 프로젝트 서비스를 사용하여 **출력** 창과 **오류 목록** 창에 메시지를 씁니다.  자세한 내용은 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)을 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## 확장 배포  
 확장을 배포하려면 어셈블리 및 확장과 함께 배포할 다른 모든 파일에 대한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지를 만듭니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [Extending SharePoint Project Items](../sharepoint/extending-sharepoint-project-items.md)   
 [Walkthrough: Extending a SharePoint Project Item Type](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
  