---
title: "방법: 실행 코드는 경우 배포 단계를 실행할 | Microsoft Docs"
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
helpviewer_keywords: SharePoint development in Visual Studio, extending deployment
ms.assetid: 6b0a52e5-e0ba-41bc-9e8a-1013e51fd3ba
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: a147b9f6def49565334004bda1f8c4c80b0e7bfa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-run-code-when-deployment-steps-are-executed"></a>방법: 배포 단계가 진행될 때 코드 실행
  SharePoint 프로젝트의 배포 단계에 대 한 추가 작업을 수행 하려는 경우 Visual Studio는 각 배포 단계를 실행 한 후 및 하기 전에 SharePoint 프로젝트 항목에 의해 발생 한 이벤트를 처리할 수 있습니다. 자세한 내용은 참조 [확장 SharePoint 패키징 및 배포](../sharepoint/extending-sharepoint-packaging-and-deployment.md)합니다.  
  
### <a name="to-run-code-when-deployment-steps-are-executed"></a>배포 단계를 실행할 때 코드를 실행 하려면  
  
1.  프로젝트 항목 확장, 프로젝트 확장명 또는 새 프로젝트 항목 형식 정의 만듭니다. 자세한 내용은 다음 항목을 참조하세요.  
  
    -   [방법: SharePoint 항목 확장명 만들기](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [방법: SharePoint 프로젝트 확장명 만들기](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [방법: SharePoint 프로젝트 항목 형식 정의](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  확장에서 처리는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> 의 이벤트는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> (프로젝트 항목 확장 또는 프로젝트 확장명)에 개체 또는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> 개체 (새 프로젝트 항목 형식 정의).  
  
3.  이벤트 처리기를 사용 하 여는 <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs> 및 <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepCompletedEventArgs> 배포 단계에 대 한 정보를 얻으려면 매개 변수입니다. 예를 들어 배포 단계를 실행 되 고 솔루션 되 고 있는지 여부를 확인할 수 있습니다 배포 되거나 취소 합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 처리 하는 방법을 보여 줍니다.는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> 및 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> 목록 인스턴스 프로젝트 항목에 대 한 확장에는 이벤트입니다. 이 확장 프로그램에는 추가 메시지에 기록 된 **출력** 배포 및 솔루션을 제거 하는 동안 응용 프로그램 풀을 재생 하는 Visual Studio 창.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#4](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/handledeploymentstepevents.vb#4)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#4](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/handledeploymentstepevents.cs#4)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 어셈블리에 대 한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>확장 배포  
 확장을 배포 하려면 만듭니다는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리 및 확장과 함께 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [확장 SharePoint 패키징 및 배포](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [연습: SharePoint 프로젝트용 사용자 지정 배포 단계 만들기](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)   
 [방법: SharePoint 프로젝트가 배포되거나 취소될 때 코드 실행](../sharepoint/how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted.md)  
  
  