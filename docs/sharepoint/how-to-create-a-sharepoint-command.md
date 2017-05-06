---
title: "How to: Create a SharePoint Command"
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
  - "SharePoint commands [SharePoint development in Visual Studio], creating"
ms.assetid: e1fda8f0-eae1-4278-91c1-19a5e1fc327f
caps.latest.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 21
---
# How to: Create a SharePoint Command
  SharePoint 도구 확장에서 서버 개체 모델을 사용하려면 API를 호출하는 사용자 지정 *SharePoint 명령*을 만들어야 합니다.  어셈블리에 서버 개체 모델을 직접 호출할 수 있는 SharePoint 명령을 정의합니다.  
  
 SharePoint 명령의 용도에 대한 자세한 내용은 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)을 참조하십시오.  
  
### SharePoint 명령을 만들려면  
  
1.  다음과 같이 구성되는 클래스 라이브러리 프로젝트를 만듭니다.  
  
    -   .NET Framework 버전 3.5를 대상으로 합니다.  대상 프레임워크를 선택하는 방법에 대한 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](~/ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하십시오.  
  
    -   AnyCPU 또는 x64 플랫폼을 대상으로 합니다.  기본적으로 클래스 라이브러리 프로젝트의 대상 플랫폼은 AnyCPU입니다.  대상 플랫폼을 선택하는 방법에 대한 자세한 내용은 [NIB: How to: Optimize an Application for a Specific CPU Type](http://msdn.microsoft.com/ko-kr/294a75d2-4279-4b72-8298-2bea05be907a)를 참조하십시오.  
  
    > [!NOTE]  
    >  SharePoint 명령은 .NET Framework 3.5를 대상으로 하고 SharePoint 도구 확장은 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]을 대상으로 하기 때문에 SharePoint 도구 확장을 정의하는 동일한 프로젝트에서 SharePoint 명령을 구현할 수 없습니다.  확장에서 사용하는 모든 SharePoint 명령은 별도 프로젝트에서 정의해야 합니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
    -   Microsoft.SharePoint  
  
3.  해당 프로젝트의 클래스에서 SharePoint 명령을 정의하는 메서드를 만듭니다.  이 메서드는 다음 지침을 따라야 합니다.  
  
    -   매개 변수는 하나 또는 두 개 있을 수 있습니다.  
  
         첫 번째 매개 변수는 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> 개체여야 합니다.  이 개체는 해당 명령이 실행되는 Microsoft.SharePoint.SPSite 또는 Microsoft.SharePoint.SPWeb을 제공합니다.  또한 Visual Studio의 **출력** 창 또는 **오류 목록** 창에 메시지를 작성하는 데 사용할 수 있는 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandLogger> 개체도 제공합니다.  
  
         두 번째 매개 변수는 선택적이고 그 형식은 사용자가 선택할 수 있습니다.  SharePoint 도구 확장의 데이터를 명령으로 전달해야 하는 경우 이 매개 변수를 SharePoint 명령에 추가할 수 있습니다.  
  
    -   선택 사항으로, 반환 값을 사용할 수 있습니다.  
  
    -   두 번째 매개 변수와 반환 값은 WCF\(Windows Communication Foundation\)에서 serialize할 수 있는 형식이어야 합니다.  자세한 내용은 [데이터 계약 Serializer에서 지원하는 형식](http://msdn.microsoft.com/library/7381b200-437a-4506-9556-d77bf1bc3f34) 및 [XmlSerializer 클래스 사용](http://msdn.microsoft.com/library/c680602d-39d3-44f1-bf22-8e6654ad5069)을 참조하십시오.  
  
    -   메서드의 표시 유형은 **public**, **internal** 또는 **private** 중 하나일 수 있고, 메서드는 정적이거나 그렇지 않을 수 있습니다.  
  
4.  메서드에 <xref:Microsoft.VisualStudio.SharePoint.Commands.SharePointCommandAttribute>를 적용합니다.  이 특성은 명령의 고유 식별자를 지정합니다. 이 식별자는 메서드 이름과 일치하지 않아도 됩니다.  
  
     SharePoint 도구 확장에서 명령을 호출하는 경우 동일한 고유 식별자를 지정해야 합니다.  자세한 내용은 [How to: Execute a SharePoint Command](../sharepoint/how-to-execute-a-sharepoint-command.md)을 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 식별자가 `Contoso.Commands.UpgradeSolution`인 SharePoint 명령을 보여 줍니다.  이 명령에서는 배포된 솔루션으로 업그레이드하기 위해 서버 개체 모델의 API를 사용합니다.  
  
 [!code-csharp[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#5](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectextension.upgradedeploymentstep/CS/SharePointCommands/Commands.cs#5)]
 [!code-vb[SPExtensibility.ProjectExtension.UpgradeDeploymentStep#5](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectextension.upgradedeploymentstep/vb/sharepointcommands/commands.vb#5)]  
  
 이 명령에는 암시적인 첫 번째 <xref:Microsoft.VisualStudio.SharePoint.Commands.ISharePointCommandContext> 매개 변수 외에 SharePoint 사이트로 업그레이드되는 .wsp 파일의 전체 경로를 포함하는 사용자 지정 문자열 매개 변수도 있습니다.  보다 큰 예제의 컨텍스트에서 이 코드를 보려면 [Walkthrough: Creating a Custom Deployment Step for SharePoint Projects](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)를 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 다음 어셈블리에 대한 참조가 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint.Commands  
  
-   Microsoft.SharePoint  
  
## 명령 배포  
 명령을 배포하려면 명령 어셈블리를 해당 명령을 사용하는 확장 어셈블리와 함께 동일한 VSIX\([!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Extension\) 패키지에 포함합니다.  또한 extension.vsixmanifest 파일에 해당 명령 어셈블리에 대한 항목도 추가해야 합니다.  자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
## 참고 항목  
 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [How to: Execute a SharePoint Command](../sharepoint/how-to-execute-a-sharepoint-command.md)   
 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)  
  
  