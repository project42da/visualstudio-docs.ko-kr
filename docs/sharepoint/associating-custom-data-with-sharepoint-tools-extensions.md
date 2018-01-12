---
title: "SharePoint와 함께 사용자 지정 데이터 연결 도구 확장 | Microsoft Docs"
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
- projects [SharePoint development in Visual Studio], associating custom data
- project items [SharePoint development in Visual Studio], associating custom data
- SharePoint project items, associating custom data
- SharePoint projects, associating custom data
- SharePoint development in Visual Studio, extensibility features
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8868300375d34664ba267b473f24d2c6a91ddd55
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="associating-custom-data-with-sharepoint-tools-extensions"></a>SharePoint 도구 확장과 사용자 지정 데이터 연결
  SharePoint 도구 확장에서 특정 개체를 사용자 지정 데이터를 추가할 수 있습니다. 데이터 확장 프로그램의 다른 코드에서 나중에 액세스 하려면 확장 프로그램의 한 부분에 있는 경우에 유용 합니다. 데이터 저장 및 액세스 하는 사용자 지정 방법을 구현 하는 대신 확장에 데이터 개체와 연결할 수 있으며 나중에 동일한 개체에서 데이터를 한 다음 검색할 수 있습니다.  
  
 Visual Studio에서 특정 항목에 관련 된 데이터를 보존 하려는 경우 사용자 지정 데이터 개체에 추가 유용 합니다. SharePoint 도구 확장은 Visual Studio에서 하므로 확장 작업할 수도 있습니다 여러 다른 항목 번만 로드 됩니다 (프로젝트 같은 프로젝트 항목 또는 **서버 탐색기** 노드) 언제 든 지 합니다. 특정 항목에만 관련 된 사용자 지정 데이터를 설정한 경우 해당 항목을 나타내는 개체에 데이터를 추가할 수 있습니다.  
  
 SharePoint 도구 확장의 개체에 사용자 지정 데이터를 추가 하면 데이터는 유지 되지 않습니다. 데이터를 개체의 수명 동안에 사용할 수 있습니다. 개체를 가비지 수집에 의해 회수, 데이터 손실 됩니다.  
  
 SharePoint 프로젝트 시스템의 확장을 확장이 로드 된 후에 유지 하는 문자열 데이터를 저장할 수 있습니다. 자세한 내용은 참조 [SharePoint 프로젝트 시스템의 확장에 대 한 데이터 저장](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)합니다.  
  
## <a name="objects-that-can-contain-custom-data"></a>사용자 지정 데이터를 포함할 수 있는 개체  
 사용자 지정 데이터를 구현 하는 SharePoint 도구 개체 모델의 모든 개체를 추가할 수는 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject> 인터페이스입니다. 이 인터페이스의 속성을 하나 정의 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A>, 사용자 지정 데이터 개체의 컬렉션입니다. 다음 형식은 구현 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject>:  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IMappedFolder>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IMenuItem>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeature>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeatureResourceFile>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFile>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectMember>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectPackage>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentContext>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeDefinition>  
  
## <a name="adding-and-retrieving-custom-data"></a>추가 및 사용자 지정 데이터를 검색 합니다.  
 SharePoint 도구 확장의 개체에 사용자 지정 데이터를 추가 하려면는 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 데이터를 추가 하 고 다음 사용 하려는 개체의 속성에서 <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.Add%2A> 데이터 개체를 추가 하는 메서드.  
  
 에서 SharePoint 도구 확장의 개체를 사용자 지정 데이터를 검색 하려면 가져오기는 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 개체 및 다음 방법 중 하나를 사용 하는 속성:  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.TryGetValue%2A>. 이 메서드가 반환 **true** 데이터 개체가 있는 경우 또는 **false** 존재 하지 않는 경우. 값 형식 또는 참조 형식의 인스턴스를 검색 하려면이 메서드를 사용할 수 있습니다.  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.GetValue%2A>. 이 메서드는 데이터를 반환 합니다.이 종료 될 경우 개체 또는 **null** 존재 하지 않는 경우. 이 메서드는 참조 형식의 인스턴스를 검색에 사용할 수 있습니다.  
  
 다음 코드 예제에서는 특정 데이터 개체는 이미 프로젝트 항목과 연결 된 있는지 여부를 결정 합니다. 데이터 개체는 이미 프로젝트 항목과 연결 된 경우 개체를 추가 하는 코드는 <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> 프로젝트 항목의 속성입니다. 이 예를 보려면이 컨텍스트에서 보다 큰 예제의 참조 하세요. [하는 방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 속성 추가](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)합니다.  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#13](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#13)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#13](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#13)]  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 도구 확장의 프로그래밍 개념 및 기능](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)   
 [연습: 항목 템플릿, 1 부와 사용자 지정 작업 프로젝트 항목 만들기](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [연습: 웹 파트를 표시 하는 서버 탐색기 확장](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [방법: SharePoint 프로젝트에 속성 추가](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 속성 추가] (.. /sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md   
  