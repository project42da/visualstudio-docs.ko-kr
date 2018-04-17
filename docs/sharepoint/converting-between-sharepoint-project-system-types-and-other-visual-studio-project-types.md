---
title: SharePoint 프로젝트 시스템 형식과 기타 Visual Studio 프로젝트 형식 간의 변환 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project service
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6cf039f3d5330b2f4869ae323ac358a1220c2fbf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types"></a>SharePoint 프로젝트 시스템 형식과 기타 Visual Studio 프로젝트 형식 간의 변환
  일부 경우에는 SharePoint 프로젝트 시스템에서 개체를 할 수 있고 Visual Studio 자동화 개체 모델 또는 통합 개체 모델에 있는 해당 개체의 기능을 사용 하려는 또는 그 반대의 경우도 마찬가지입니다. 이러한 경우에 사용할 수 있습니다는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> 다른 개체 모델에는 개체를 변환 하 여 SharePoint 프로젝트 서비스의 메서드.  
  
 예를 들어 있을 수 있습니다는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 개체 남기려는에서 사용할 수 있는 메서드를 사용 하는 <xref:EnvDTE.Project> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> 개체입니다. 이 경우 사용할 수 있습니다는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> 변환 하는 메서드는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 에 <xref:EnvDTE.Project> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject>합니다.  
  
 Visual Studio 자동화 개체 모델 및 Visual Studio 통합 개체 모델에 대 한 자세한 내용은 참조 [프로그래밍 모델의 SharePoint 도구 확장의 개요](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)합니다.  
  
## <a name="types-of-conversions"></a>형식 변환  
 다음 표에서이 메서드는 SharePoint 프로젝트 시스템 및 다른 Visual Studio 개체 모델을 서로 변환할 수 있는 형식을 나열 합니다.  
  
|SharePoint 프로젝트 시스템 형식|자동화 및 통합 개체 모델의 해당 형식|  
|------------------------------------|-------------------------------------------------------------------------|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>|<xref:EnvDTE.Project><br /><br /> 또는<br /><br /> 프로젝트에 대 한 기본 COM 개체에서 구현 되는 Visual Studio 통합 개체 모델에서 모든 인터페이스입니다. 이러한 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> (또는 파생 된 인터페이스) 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>합니다. 목록이 프로젝트에서 구현 되는 주요 인터페이스에 대 한 참조 [프로젝트 모델에 대 한 핵심 구성 요소](/visualstudio/extensibility/internals/project-model-core-components)합니다.|  
|<xref:Microsoft.VisualStudio.SharePoint.IMappedFolder><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeature><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeatureResourceFile><br /><br /> <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectPackage>|<xref:EnvDTE.ProjectItem><br /><br /> 또는<br /><br /> A<xref:System.UInt32> 프로젝트 멤버를 식별 하는 값 (한 VSITEMID 라고도 함)는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 해당 항목을 포함 합니다. 이 값에 전달할 수는 *itemid* 일부 매개 변수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 메서드.|  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 사용 하는 방법을 보여 줍니다.는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.Convert%2A> 변환 하는 메서드는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 개체는 <xref:EnvDTE.Project>합니다.  
  
 [!code-csharp[SPExtensibility.ProjectService.FromDTE#2](../sharepoint/codesnippet/CSharp/spprojectserviceaddin/connect.cs#2)]
 [!code-vb[SPExtensibility.ProjectService.FromDTE#2](../sharepoint/codesnippet/VisualBasic/spprojectserviceaddin/connect.vb#2)]  
  
 이 예제에는 다음 사항이 필요합니다.  
  
-   EnvDTE.dll 어셈블리에 대 한 참조가 있는 SharePoint 프로젝트 시스템의 확장입니다. 자세한 내용은 참조 [SharePoint 프로젝트 시스템 확장](../sharepoint/extending-the-sharepoint-project-system.md)합니다.  
  
-   등록 하는 코드는 `projectService_ProjectAdded` 처리 하는 메서드는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded> 의 이벤트는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService> 개체입니다. 예를 들어 참조 [하는 방법: SharePoint 프로젝트 확장 만들기](../sharepoint/how-to-create-a-sharepoint-project-extension.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 서비스 사용](../sharepoint/using-the-sharepoint-project-service.md)   
 [방법: SharePoint 프로젝트 서비스 검색](../sharepoint/how-to-retrieve-the-sharepoint-project-service.md)   
 [SharePoint 도구 확장의 프로그래밍 모델 개요](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)  
  
  