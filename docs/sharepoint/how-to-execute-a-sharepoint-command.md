---
title: '방법: SharePoint 명령 실행 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint commands [SharePoint development in Visual Studio], executing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 824a747d9253817e1f188730996dac707b3e5ee5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-execute-a-sharepoint-command"></a>방법: SharePoint 명령 실행
  사용자 지정 SharePoint 도구 확장에서 서버 개체 모델을 사용 하려는 경우 만들어야 *SharePoint 명령* API를 호출 합니다. 명령을 정의 하 고 SharePoint 도구 확장으로 배포한 후 확장 프로그램에 SharePoint 서버 개체 모델을 호출 하는 명령을 실행할 수 있습니다. 이 명령은 실행 하려면의 ExecuteCommand 메서드 중 하나를 사용는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> 개체입니다.  
  
 SharePoint 명령의 용도 대 한 자세한 내용은 참조 [SharePoint 개체 모델 호출](../sharepoint/calling-into-the-sharepoint-object-models.md)합니다.  
  
### <a name="to-execute-a-sharepoint-command"></a>SharePoint 명령을 실행 하려면  
  
1.  SharePoint 도구 확장에 전달 되는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> 개체입니다. 가져오는 방법은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> 개체 만들면 확장의 형식에 따라 달라 집니다.  
  
    -   SharePoint 프로젝트 시스템의 확장을 사용 하 여는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.SharePointConnection%2A> 속성입니다.  
  
         프로젝트 시스템 확장에 대 한 자세한 내용은 참조 [SharePoint 프로젝트 시스템 확장](../sharepoint/extending-the-sharepoint-project-system.md)합니다.  
  
    -   확장에는 **SharePoint 연결** 노드에서 **서버 탐색기**를 사용 하 여는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeContext.SharePointConnection%2A> 속성입니다. 가져오려는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeContext> 개체를 가져오려면는 <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode.Context%2A> 속성입니다.  
  
         에 대 한 자세한 내용은 **서버 탐색기** 확장 참조 [서버 탐색기에서 SharePoint 연결 노드 확장](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)합니다.  
  
    -   프로젝트 템플릿 마법사와 같은 SharePoint 도구의 확장에 포함 하지 않은 코드를 사용 하 여는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectService.SharePointConnection%2A> 속성입니다.  
  
         프로젝트 서비스 검색 하는 방법에 대 한 자세한 내용은 참조 [SharePoint 프로젝트 서비스를 사용 하 여](../sharepoint/using-the-sharepoint-project-service.md)합니다.  
  
2.  ExecuteCommand 메서드 중 하나를 호출 하는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> 개체입니다. ExecuteCommand 메서드의 첫 번째 인수에 실행 하려는 명령의 이름을 전달 합니다. 명령에는 사용자 지정 매개 변수를 ExecuteCommand 메서드의 두 번째 인수를 해당 매개 변수를 전달 합니다.  
  
     각 지원 되는 명령 서명에 대 한 다른 ExecuteCommand 오버 로드가 있습니다. 다음 표에서 지원 되는 서명 및 오버 로드 각 서명에 사용할를 나열 합니다.  
  
    |명령 시그니처|사용 하도록 ExecuteCommand 오버 로드|  
    |-----------------------|------------------------------------|  
    |명령에 기본 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> 매개 변수 및 반환 값이 없습니다.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|  
    |명령에 기본 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> 매개 변수 및 반환 값입니다.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|  
    |명령에 두 개의 매개 변수 (기본 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> 매개 변수 및 사용자 지정 매개 변수) 및 반환 값이 없습니다.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|  
    |이 명령은 두 개의 매개 변수 및 반환 값에 있습니다.|<xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A>|  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 사용 하는 방법을 보여 줍니다.는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A> 오버 로드를 호출 하는 `Contoso.Commands.UpgradeSolution` 명령에 설명 된 [하는 방법: SharePoint 명령 만들기](../sharepoint/how-to-create-a-sharepoint-command.md)합니다.  
  
 [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#6](../sharepoint/codesnippet/CSharp/UpgradeDeploymentStep/deploymentstepextension/upgradestep.cs#6)]
 [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#6](../sharepoint/codesnippet/VisualBasic/upgradedeploymentstep/deploymentstepextension/upgradestep.vb#6)]  
  
 `Execute` 이 예제에 표시 된 메서드는의 구현은 <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep.Execute%2A> 의 메서드는 <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep> 사용자 지정 배포 단계에 대 한 인터페이스입니다. 보다 큰 예제의의 컨텍스트에서이 코드를 보려면 [연습: SharePoint 프로젝트용 사용자 지정 배포 단계 만들기](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)합니다.  
  
 에 대 한 호출에 대 한 다음 세부 정보를 참고는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection.ExecuteCommand%2A> 메서드:  
  
-   첫 번째 매개 변수를 호출 하는 명령을 식별 합니다. 이 문자열에 전달 하는 값과 일치는 <xref:Microsoft.VisualStudio.SharePoint.Commands.SharePointCommandAttribute> 명령 정의 합니다.  
  
-   두 번째 명령의 두 번째 사용자 지정 매개 변수에 전달 하려는 값입니다. 이 경우,이 SharePoint 사이트에는 업그레이드 중인.wsp 파일의 전체 경로입니다.  
  
-   코드는 암시적 통과 하지 못하면 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> 명령에 매개 변수입니다. 이 매개 변수는 명령에 자동 전달 SharePoint 프로젝트 시스템의 확장 또는의 확장에서 명령을 호출 하는 경우는 **SharePoint 연결** 노드에서 **서버 탐색기**. 다른 유형의 솔루션을 구현 하는 프로젝트 템플릿 마법사와 같이 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스는이 매개 변수는 **null**합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에서는 Microsoft.VisualStudio.SharePoint 어셈블리에 대 한 참조가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 개체 모델 호출](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [방법: SharePoint 명령 만들기](../sharepoint/how-to-create-a-sharepoint-command.md)   
 [연습: 서버 탐색기를 확장하여 웹 파트 표시](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)  
  
  