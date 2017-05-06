---
title: "How to: Retrieve the SharePoint Project Service"
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
  - "SharePoint project service"
ms.assetid: 3d8b7adf-2603-4247-9b61-6326a1dd0dec
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# How to: Retrieve the SharePoint Project Service
  다음 솔루션 형식의 SharePoint 프로젝트 서비스에 액세스할 수 있습니다.  
  
-   프로젝트 확장, 프로젝트 항목 확장, 프로젝트 항목 형식 정의 등의 SharePoint 프로젝트 시스템 확장.  이러한 확장 형식에 대한 자세한 내용은 [Extending the SharePoint Project System](../sharepoint/extending-the-sharepoint-project-system.md)을 참조하십시오.  
  
-   **서버 탐색기**에서 **SharePoint 연결** 노드의 확장.  이러한 확장 형식에 대한 자세한 내용은 [Extending the SharePoint Connections Node in Server Explorer](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)을 참조하십시오.  
  
-   추가 기능 또는 VSPackage 같은 Visual Studio 확장의 다른 형식  
  
## 프로젝트 시스템 확장에서 서비스 검색  
 SharePoint 프로젝트 시스템 확장에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 개체의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectService%2A> 속성을 사용하여 프로젝트 서비스에 액세스할 수 있습니다.  
  
 다음 절차에 따라 프로젝트 서비스를 검색할 수도 있습니다.  
  
#### 프로젝트 확장에서 서비스를 검색하려면  
  
1.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> 인터페이스의 구현에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> 메서드를 찾습니다.  
  
2.  *projectService* 속성을 사용하여 서비스에 액세스합니다.  
  
     다음 코드 예제에서는 간단한 프로젝트 확장에서 프로젝트 서비스를 사용하여 **출력** 창 및 **오류 목록** 창에 메시지를 작성하는 방법을 보여 줍니다.  
  
     [!code-csharp[SPExtensibility.ProjectService.FromProjectSystemExtensions#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectservice.fromprojectsystemextensions/cs/extension/extension.cs#1)]
     [!code-vb[SPExtensibility.ProjectService.FromProjectSystemExtensions#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectservice.fromprojectsystemextensions/vb/extension/extension.vb#1)]  
  
     프로젝트 확장 만들기에 대한 자세한 내용은 [How to: Create a SharePoint Project Extension](../sharepoint/how-to-create-a-sharepoint-project-extension.md)를 참조하십시오.  
  
#### 프로젝트 항목 확장에서 서비스를 검색하려면  
  
1.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> 인터페이스의 구현에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> 메서드를 찾습니다.  
  
2.  *projectItemType* 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType.ProjectService%2A> 속성을 사용하여 서비스를 검색합니다.  
  
     다음 코드 예제에서는 **목록 정의** 프로젝트 항목의 간단한 확장에서 프로젝트 서비스를 사용하여 **출력** 창 및 **오류 목록** 창에 메시지를 작성하는 방법을 보여 줍니다.  
  
     [!code-csharp[SPExtensibility.ProjectService.FromProjectSystemExtensions#2](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectservice.fromprojectsystemextensions/cs/extension/extension.cs#2)]
     [!code-vb[SPExtensibility.ProjectService.FromProjectSystemExtensions#2](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectservice.fromprojectsystemextensions/vb/extension/extension.vb#2)]  
  
     프로젝트 항목 확장 만들기에 대한 자세한 내용은 [How to: Create a SharePoint Project Item Extension](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)를 참조하십시오.  
  
#### 프로젝트 항목 형식 정의에서 서비스를 검색하려면  
  
1.  <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 인터페이스의 구현에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 메서드를 찾습니다.  
  
2.  *typeDefinition* 매개 변수의 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.ProjectService%2A> 속성을 사용하여 서비스를 검색합니다.  
  
     다음 코드 예제에서는 간단한 프로젝트 항목 형식 정의에서 프로젝트 서비스를 사용하여 **출력** 창 및 **오류 목록** 창에 메시지를 작성하는 방법을 보여 줍니다.  
  
     [!code-csharp[SPExtensibility.ProjectService.FromProjectSystemExtensions#3](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectservice.fromprojectsystemextensions/cs/extension/extension.cs#3)]
     [!code-vb[SPExtensibility.ProjectService.FromProjectSystemExtensions#3](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectservice.fromprojectsystemextensions/vb/extension/extension.vb#3)]  
  
     프로젝트 항목 형식 정의에 대한 자세한 내용은 [How to: Define a SharePoint Project Item Type](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)를 참조하십시오.  
  
## 서버 탐색기 확장에서 서비스 검색  
 **서버 탐색기**에 있는 **SharePoint 연결** 노드의 확장에서 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode> 개체의 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode.ServiceProvider%2A> 속성을 사용하여 프로젝트 서비스에 액세스할 수 있습니다.  
  
#### 서버 탐색기 확장에서 서비스를 검색하려면  
  
1.  확장에 있는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode> 개체의 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode.ServiceProvider%2A> 속성에서 <xref:System.IServiceProvider> 개체를 가져옵니다.  
  
2.  <xref:System.IServiceProvider.GetService%2A> 메서드를 사용하여 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> 개체를 요청합니다.  
  
     다음 코드 예제에서는 **서버 탐색기**의 노드를 나열하기 위해 확장을 통해 추가된 바로 가기 메뉴에서 프로젝트 서비스를 사용하여 **출력** 창 및 **오류 목록** 창에 메시지를 작성하는 방법을 보여 줍니다.  
  
     [!code-csharp[SPExtensibility.ProjectService.FromSPExplorerExtensions#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectservice.fromspexplorerextensions/cs/extension/extension.cs#1)]
     [!code-vb[SPExtensibility.ProjectService.FromSPExplorerExtensions#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectservice.fromspexplorerextensions/vb/extension/extension.vb#1)]  
  
     **서버 탐색기**에서 **SharePoint 연결** 노드를 확장하는 방법에 대한 자세한 내용은 [How to: Extend a SharePoint Node in Server Explorer](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)을 참조하십시오.  
  
## 기타 Visual Studio 확장에서 서비스 검색  
 VSPackage에서 프로젝트 서비스를 검색하거나, 자동화 개체 모델의 <xref:EnvDTE80.DTE2> 개체에 액세스하는 Visual Studio 확장\(예: <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하는 추가 기능 또는 프로젝트 템플릿 마법사\)에서 서비스를 검색할 수 있습니다.  
  
 VSPackage에서는 다음 메서드 중 하나를 사용하여 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> 개체를 요청할 수 있습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Package> 클래스에서 파생되는 관리되는 VSPackage의 <xref:System.IServiceProvider.GetService%2A> 메서드.  자세한 내용은 [방법: 서비스 가져오기](~/extensibility/how-to-get-a-service.md)을 참조하십시오.  
  
-   <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 정적 메서드.  자세한 내용은 [방법: GetGlobalService 사용](~/misc/how-to-use-getglobalservice.md)을 참조하십시오.  
  
 <xref:EnvDTE80.DTE2> 개체에 액세스하는 Visual Studio 확장에서 <xref:Microsoft.VisualStudio.Shell.ServiceProvider> 개체의 <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> 메서드를 사용하여 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> 개체를 요청할 수 있습니다.  자세한 내용은 [방법: DTE 개체에서 서비스 가져오기](~/misc/how-to-get-a-service-from-the-dte-object.md)를 참조하십시오.  
  
### 예제  
 다음 코드 예제에서는 Visual Studio 추가 기능에서 프로젝트 서비스를 검색하는 방법을 보여 줍니다.  이 코드를 사용하려면 추가 기능 프로젝트의 `Connect` 클래스에서 이 코드를 실행하십시오.  추가 기능 프로젝트에서 `_applicationObject` 개체는 자동으로 생성되며, 이 개체는 <xref:EnvDTE80.DTE2> 인터페이스의 인스턴스입니다.  
  
 [!code-csharp[SPExtensibility.ProjectService.FromDTE#1](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectservice.fromdte/cs/connect.cs#1)]
 [!code-vb[SPExtensibility.ProjectService.FromDTE#1](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectservice.fromdte/vb/connect.vb#1)]  
  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Visual Studio 추가 기능 프로젝트.  자세한 내용은 [How to: Create an Add-In](http://msdn.microsoft.com/library/50be56d2-e3a5-4cd2-8569-2a0666b268ce)를 참조하십시오.  
  
-   Microsoft.VisualStudio.OLE.Interop, Microsoft.VisualStudio.Shell 및 Microsoft.VisualStudio.SharePoint 어셈블리에 대한 참조  
  
## 참고 항목  
 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)   
 [How to: Create an Add-In](http://msdn.microsoft.com/library/50be56d2-e3a5-4cd2-8569-2a0666b268ce)   
 [방법: 서비스 가져오기](~/extensibility/how-to-get-a-service.md)   
 [방법: DTE 개체에서 서비스 가져오기](~/misc/how-to-get-a-service-from-the-dte-object.md)   
 [방법: 프로젝트 템플릿에 마법사 사용](~/extensibility/how-to-use-wizards-with-project-templates.md)  
  
  